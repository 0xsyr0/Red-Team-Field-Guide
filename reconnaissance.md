# Reconnaissance

- [Resources](https://github.com/0xsyr0/Red-Team-Field-Guide/blob/main/reconnaissance.md#Resources)

## Table of Contents

- [Amass](https://github.com/0xsyr0/Red-Team-Field-Guide/blob/main/reconnaissance.md#Amass)
- [DMARC](https://github.com/0xsyr0/Red-Team-Field-Guide/blob/main/reconnaissance.md#DMARC)
- [Naabu](https://github.com/0xsyr0/Red-Team-Field-Guide/blob/main/reconnaissance.md#Naabu)
- [Nmap](https://github.com/0xsyr0/Red-Team-Field-Guide/blob/main/reconnaissance.md#Nmap)
- [SPF](https://github.com/0xsyr0/Red-Team-Field-Guide/blob/main/reconnaissance.md#SPF)
- [sslscan](https://github.com/0xsyr0/Red-Team-Field-Guide/blob/main/reconnaissance.md#sslscan)
- [sslyze](https://github.com/0xsyr0/Red-Team-Field-Guide/blob/main/reconnaissance.md#sslyze)
- [subfinder](https://github.com/0xsyr0/Red-Team-Field-Guide/blob/main/reconnaissance.md#subfinder)

## Resources

| Name | URL |
| --- | --- |
| Amass | https://github.com/OWASP/Amass |
| crt.sh | https://crt.sh |
| Censys | https://search.censys.io |
| DNSdumpster | https://dnsdumpster.com |
| IPinfo | https://ipinfo.io |
| naabu | https://github.com/projectdiscovery/naabu |
| Nmap | https://github.com/nmap/nmap |
| spiderfoot | https://github.com/smicallef/spiderfoot |
| subfinder | https://github.com/projectdiscovery/subfinder |

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
