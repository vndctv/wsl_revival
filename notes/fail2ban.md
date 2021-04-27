# fail2ban
`fail2ban` will automatically add `iptables` rules to block
IP addresses that have too many failed `ssh` logins.

## Installation & Configuration
`fail2ban` is installed through `apt`: `sudo apt install fail2ban`

Configuration is kept in `/etc/fail2ban/jail.conf`.