# Reconnaissance

| Name | URL |
| --- | --- |
| Nmap | https://github.com/nmap/nmap |
| Amass | https://github.com/OWASP/Amass |
| naabu | https://github.com/projectdiscovery/naabu |
| subfinder | https://github.com/projectdiscovery/subfinder |
| IPinfo | https://ipinfo.io |
| crt.sh | https://crt.sh |
| Censys | https://search.censys.io |
| DNSdumpster | https://dnsdumpster.com |

## Amass

```c
URL: https://github.com/OWASP/Amass

$ amass intel --asn <ASN>
$ amass intel --asn <ASN> -list
$ amass enum -active -d <TARGET_DOMAIN> -p 80,443,8080
```

## DMARC

```c
$ dig txt _dmarc.<DOMAIN> | grep dmarc
```

## Naabu

```c
$ sudo naabu -p - -l /PATH/TO/FILE/<FILE> -o /PATH/TO/FILE/<FILE>
```

## Nmap

```c
$ sudo nmap -sC -sV -sS -p- -oN initial --script discovery <RHOST>
$ sudo nmap -sV -sU <RHOST>
```

## SPF

```c
$ dig txt <DOMAIN> | grep spf
```

## sslscan

```c
$ sslscan <RHOST>
```

## sslyze

```c
$ sslyze <RHOST>
```

## subfinder

```c
$ subfinder -dL /PATH/TO/FILE/<FILE>
$ subfinder -dL /PATH/TO/FILE/<FILE> -nW -ip -p /PATH/TO/FILE/<FILE>
```

### Scan for Top Routinely Exploited Vulnerabilities according to CISA

```c
$ subfinder -d <DOMAIN> -all -silent | httpx -silent | nuclei -rl 50 -c 15 -timeout 10 -tags cisa -vv 
```
