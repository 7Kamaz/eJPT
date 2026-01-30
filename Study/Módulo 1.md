
---


```bash
whatis host

host hackersploit.org


whatweb hackersploit.org

sudo apt-get install webhttprack

whois hackersploit.org

dnsrecon -d hackersploit.org

wafw00f hackersploit.org -a

sudo apt-get install sublist3r
sublist3r -d haclersploit.org -e google,yahoo

theHarvester -d INE -b duckduckgo,baidu,bing,yahoo

dig axfr @10.10.10.5 teste.com

dnsrecon -d [dominio.com] -t axfr

fierce --domain [dominio.com]

sudo nmap -sn 10.10.10.10

sudo apt-get install netdiscover -y
netdiscover -i eth0 -r 192.168.0.1/24

---

 





```

---

URLs interessantes para testar

```http
https://hackesploit.org/robots.txt
https://hackesploit.org/sitemap_index.xml
https://whois.org
https://netcraft.com
https://dnsdumpster.com
https://archive.org


* Gold
https://www.exploit-db.com/google-hacking-database 






```

---

## Google Dorks

```url
# Na barra de pesquisa do google

site:ine.com
site:ine.com inurl:forum|admin|etc
site:*.ine.com
site:*.ine.com inurl:forum|admin|etc
site:*.ine.com intitle:admin
site:*.ine.com filetype:pdf|doc|docx|xlsx|zip|

intitle:index of
cache:ine.com

inurl:auth_user_file.txt
inurl:passwd.txt


* Gold
site:gov.* intitle:"index of" *.csv passwords
intitle:"index of" credentials




```

---

# Primeiro Lab

```bash
┌──(root㉿INE)-[~/target.ine.local]
└─# history                                                                                                                                                          
    1  ifconfig
    2  cat /etc/hosts
    3  ng -c 4 192.249.119.3
    4  ping -c 4 192.249.119.3
    5  nmap target.ine.local
    6  nmap -Pn target.ine.local
    7  curl -l http://target.ine.local
    8  curl -l http://target.ine.local/robots.txt
    9  whatweb target.ine.local
   10  dirb target.ine.local
   11  dirb http://target.ine.local
   12  curl -l http://target.ine.local/wp-content/index.php
   13  curl http://target.ine.local/wp-content/index.php
   14  curl -l http://target.ine.local/wp-content/uploads/flag.txt
   15  wget -m http://target.ine.local/wp-content/uploads/flag.txt
   16  la
   17  file target.ine.local/
   18  la target.ine.local/
   19  cd target.ine.local/wp-content/uploads/
   20  la
   21  ls -la
   22  cat flag.txt 
   23  dirb http://target.ine.local | grep backup
   24  dirb http://target.ine.local/wp-content
   25  dirb -w http://target.ine.local/wp-content
   26  dirb -w http://target.ine.local/wp-content/iploads
   27  dirb -w http://target.ine.local/wp-content/uploads
   28  curl -l http://target.ine.local/wp-content/index.php 
   29  curl -l http://target.ine.local/wp-content/plugins
   30  curl -l http://target.ine.local/wp-content/plugins/index.php
   31  la
   32  wget -m http://target.ine.local/wp-content/plugins/index.php
   33  la
   34  cd target.ine.local/
   35  la
   36  cd wp-content/
   37  cd plugins/
   38  la
   39  cat index.php 
   40  wpscan --url http://192.215.221.3 --enumerate vp,u
   41  wpscan --url http://target.ine.local --enumerate vp,u
   42  ls
   43  dirb http://target.ine.local -X .bak,.old,.zip,.sql,.txt
   44  curl -l http://target.ine.local/wp-config.bak
   45  cd
   46  la
   47  ls -la
   48  mv target.ine.local/ target.ine.local.old
   49  ls -la
   50* wget http://target.ine.localls ta
   51  ls -la
   52  ls -la target.ine.local.old/
   53  rm -rf target.ine.local.old/
   54  la
   55  wget -m http://target.ine.local
   56  ls -la
   57  cd target.ine.local/
   58  ls -la
   59  tree
   60  tree | grep flag
   61  tree | grep fl@g
   62  tree | grep vendor
   63  grep -rnE "FLAG|FL@G"
   64  find . -type f -name ".*"
   65  find -type f -name ".*"
   66  find /target.ine.local -type f -name ".*"
   67  curl http://target.ine.local/wp-config.php.bak
   68  curl http://target.ine.local/wp-config.php.old
   69  curl http://target.ine.local/wp-config.php.save
   70  curl http://target.ine.local/wp-config
   71  curl http://target.ine.local/config
   72  curl http://target.ine.local/wp-content/uploads
   73  dirb http://target.ine.local/wp-content/uploads/
   74  grep -ri "FLAG" ~/target.ine.local/ 
   75  grep -ri "FL@G" ~/target.ine.local/ 
   76  grep -ri "FLAG5" ~/target.ine.local/ 
   77  history

```
