# AS

As you may know, I am operating my own ISP which is Noiseless Systems ([AS211696](https://bgp.he.net/AS211696)) since roughly April 2021.

I currently operate with three IPv6 prefixes:
 - 2001:67c:2724::/48 PI
 - 2a0e:8f02:f01f::/48 PA
 - 2a12:4946:9900::/40 PA

And one IPv4:
 - 89.46.97.0/24

---

Currently, I only have a peering router in Frankfurt, Germany.  
Here are the current peering exchanges:

##### EvIX

```
neighbor 2602:fed2:fff:ffff:6::6f as 211696
```

##### KleyReX (FRA)

```
neighbor 2001:7f8:33::a121:1696:1 as 211696
neighbor 193.189.83.146 as 211696
```

##### LocIX (FRA)

```
neighbor 2001:7f8:f2:e1:0:21:1696:1 as 211696
neighbor 185.1.167.33 as 211696
```

##### iFogIX (FRA)

```
neighbor 2001:7f8:ca:1::24 as 211696
neighbor 185.1.147.24 as 211696
```
