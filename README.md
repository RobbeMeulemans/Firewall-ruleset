# Firewall-ruleset
iptables -A OUTPUT -m state --state RELATED,ESTABLISHED -j ACCEPT

iptables -A INPUT -p tcp -m tcp --dport 80 -j ACCEPT

iptables -A OUTPUT -p tcp -m tcp --dport 80 -j ACCEPT

iptables -A INPUT -p tcp -m tcp --dport 443 -j ACCEPT

iptables -A OUTPUT -p tcp -m tcp --dport 443 -j ACCEPT

iptables -A INPUT -p tcp -m tcp --dport 21 -j ACCEPT

iptables -A OUTPUT -p tcp -m tcp --dport 21 -j ACCEPT

iptables -A INPUT -p udp --dport 53 -j ACCEPT

iptables -A OUTPUT -p udp --dport 53 -j ACCEPT

iptables -t filter -A INPUT -p icmp --icmp-type echo-request -m limit --limit 5/minute -j ACCEPT

iptables -A INPUT -j DROP

