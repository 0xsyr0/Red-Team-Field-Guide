# 1 Reconnaissance

- [Resources](https://github.com/0xsyr0/Red-Team-Field-Guide/blob/main/reconnaissance.md#Resources)

## Table of Contents

- [Amass](https://github.com/0xsyr0/Red-Team-Field-Guide/blob/main/1-reconnaissance.md#Amass)
- [DMARC](https://github.com/0xsyr0/Red-Team-Field-Guide/blob/main/1-reconnaissance.md#DMARC)
- [Naabu](https://github.com/0xsyr0/Red-Team-Field-Guide/blob/main/1-reconnaissance.md#Naabu)
- [Nmap](https://github.com/0xsyr0/Red-Team-Field-Guide/blob/main/1-reconnaissance.md#Nmap)
- [Shodan](https://github.com/0xsyr0/Red-Team-Field-Guide/blob/main/1-reconnaissance.md#Shodan)
- [SPF](https://github.com/0xsyr0/Red-Team-Field-Guide/blob/main/1-reconnaissance.md#SPF)
- [sslscan](https://github.com/0xsyr0/Red-Team-Field-Guide/blob/main/1-reconnaissance.md#sslscan)
- [sslyze](https://github.com/0xsyr0/Red-Team-Field-Guide/blob/main/1-reconnaissance.md#sslyze)
- [subfinder](https://github.com/0xsyr0/Red-Team-Field-Guide/blob/main/1-reconnaissance.md#subfinder)

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

```console
$ amass intel --asn <ASN>
$ amass intel --asn <ASN> -list
$ amass enum -active -d <TARGET_DOMAIN> -p 80,443,8080
```

## DMARC

```console
$ dig txt _dmarc.<DOMAIN> | grep dmarc
```

## Naabu

```console
$ sudo naabu -p - -l /PATH/TO/FILE/<FILE> -o /PATH/TO/FILE/<FILE>
```

## Nmap

```console
$ sudo nmap -sC -sV -sS -p- -oN initial --script discovery <RHOST>
$ sudo nmap -sV -sU <RHOST>
```

## Shodan

```console
Ssl.cert.subject.CN:"<DOMAIN>" -http.title:"Invalid URL" 200
```

## SPF

```console
$ dig txt <DOMAIN> | grep spf
```

## sslscan

```console
$ sslscan <RHOST>
```

## sslyze

```console
$ sslyze <RHOST>
```

## subfinder

```console
$ subfinder -dL /PATH/TO/FILE/<FILE>
$ subfinder -dL /PATH/TO/FILE/<FILE> -nW -ip -p /PATH/TO/FILE/<FILE>
```

### Scan for Top Routinely Exploited Vulnerabilities according to CISA

```console
$ subfinder -d <DOMAIN> -all -silent | httpx -silent | nuclei -rl 50 -c 15 -timeout 10 -tags cisa -vv 
```
