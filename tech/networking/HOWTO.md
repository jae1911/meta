# AS HOWTO

Greetings, this file describes what is an AS, how to get one and also how to configure the Bird BGP daemon and how to get clients connected with Wireguard.

## General

### Considerations

Before proceeding further, please knowledge that **the internet is not a game**, please do further research before requesting an AS.

## BGP Daemons

### Existing BGP daemons

| Name | Language |
| ---- | -------- |
| [Bird](https://bird.network.cz/) | C |
| [Quagga](https://www.quagga.net/) | C |
| [FRRouting](https://frrouting.org/) | C |

## Client config

> Note: as Wireguard is encrypted, it has been noted it can put strain on some servers and therefore limit the bandwidth. Another solution using [GENEVE](https://www.redhat.com/en/blog/what-geneve) is in the works.

> Note: it is also recommended to get an IP management software to track which subnets and IPs you distribute to whom. A good way to do that is to deploy [phpIPAM](https://phpipam.net/).

### Wireguard router configuration

Here is a sample config for the Wireguard router:
```wireguard
[Interface]
Address = 2001:67c:2724:e000:1::/80
PrivateKey = privatekey=
ListenPort = 88230

# Own PC
[Peer]
PublicKey = pubkey=
AllowedIPs = 2001:67c:2724:e001:a::1/128
```

> Note: you will obviously have to replace the prefix, IPs and keys with your own.

### Wireguard client configuration

Here is a sample config for the Wireguard client:
```wireguard
[Interface]
Address = 2001:67c:2724:e001:a::1/128
PrivateKey = privkey=

[Peer]
PublicKey = pubkey=
AllowedIps = ::/0
Endpoint = hello-world.tld:88230
PersistentKeepalive = 30
```

> Note: this config works perfectly on Linux hosts but for Windows and MacOS hosts, you will have to set `AllowedIps` to `::/1, 8000::/1` in order to avoid the *kill switch* that will kill every traffic not going through Wireguard on the machine.
