<img align="right" src="https://visitor-badge.laobi.icu/badge?page_id=noetovar5.LInux-commands-to-use-in-shell-scripting"/>
# LInux-commands-to-use-in-shell-scripting
LInux commands to use in shell scripting

File & Directory Automation 

$ find /var/log -type f -name "*.log" -mtime +7 -delete
$ tar -czf logs_$(date +%F).tar.gz /var/log/*.log
$ rsync -avz /local/path/ user@remote:/backup/
$ for f in *.txt; do mv "$f" "${f%.txt}.bak"; done

System & Process Automation 

$ systemctl is-active nginx || systemctl restart nginx
$ sudo apt update -y && sudo apt upgrade -y
$ free -m | awk '/Mem:/ {if ($4 < 100) system("sudo reboot")}'

Networking Automation 

$ for h in host1 host2 host3; do ping -c1 $h && echo "$h OK" || echo " DOWN"; done
$ curl -Is https:// example dot com | head -1
$ ping -c2 8 dot 8 dot 8 dot 8 || systemctl restart network

Security & Credential Automation 

$ ssh-keygen -t rsa -b 4096 -f ~/.ssh/id_rsa -N ""
$ ssh-copy-id user@host 
$ grep "Failed password" /var/log/auth.log | awk '{print $11}' | sort | uniq -c | sort -nr

DevOps & CI/CD Automation 

$ git clone https://repo.git && cd repo && . build dot sh
$ docker system prune -af
$ kubectl get pods -A | grep -v Running
$ kubectl rollout restart deployment myapp -n prod

Monitoring & Alerts 

$ df -h | awk 'NR>1 && $5+0>90 {print $6 " is full"}' | mail -s "Disk Alert" 
$ pgrep nginx > /dev/null || systemctl restart nginxadmin at example dot com
$ echo "$(date): $(uptime)" >> /var/log/health.log

Reference image
https://media.licdn.com/dms/image/v2/D5622AQFNwXWCszqwFw/feedshare-shrink_1280/B56ZpHsq59HkAs-/0/1762139484672?e=1763596800&v=beta&t=MZRymZCQ25Tk7pV3sbqJ3FVYkRpguCc5QJ9hAEYEzRE
