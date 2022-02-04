# Going IPv6 only

Good evening all of you, in today's post, we're gonna talk about going IPv6 only.

First, let's remind ourselves what is IPv6. Wikipedia describes it as such:

    Internet Protocol version 6 (IPv6) is the most recent version of the Internet Protocol (IP) […] IPv6 was developed by the Internet Engineering Task Force (IETF) to deal with the long-anticipated problem of IPv4 address exhaustion. IPv6 is intended to replace IPv4. In December 1998, IPv6 became a Draft Standard for the IETF, who subsequently ratified it as an Internet Standard on 14 July 2017.

So, the main points are:

    IPv6 is intended to replace IPv4

But also other, other points not shown in that short introduction:

    Say goodbye to NAT
    2^128 addresses instead of 2^32

One big advantage of IPv6 is that you could give every living creature on this planet (Earth) billions of addresses and still have millions left to play with. This means that every device, that is phones, tablets, computers, servers and so on can have their own unique address.

Going IPv6 only is easy with MikroTik, just go into WinBox, IP → DHCP Client and delete everything there.

Now, first thing: configuring DNS servers.

I use DNSCrypt-proxy on my main machine, you can see the documentation for it on the ArchWiki. I use the `cloudflare-ipv6` servers.

Only problem: lazy websites that never bothered to use IPv6 (hello Slack and others, blaming their hosting platforms, that support IPv6 BTW, instead of moving their arses).

For that, during business hours (as my current work relies on Slack), I use the Trex.fi DNS64 server, which does its job wonderfully.

At the end, I don't feel I'm missing out on anything by turning off IPv4, only badly made software and websites break.

For the ones that are doing it correctly, that we use often is:

    YouTube (Google has it natively enabled since 2012)
    Cloudflare (even though they have far too many captchas for me)
    Wikipedia
    GitHub (some domains such as `usercontent`, docs domain, GitHub.io)
    Plex

As for the bad students:

    Slack, is lacking IPv6 and blaming it on others (screams for “won't do it, too lazy”)
    GitHub (main domain still has no AAAA records but hopes in the future for it to be supported as subdomains have that feature)
    The Steam store (not even a reply to the support ticket or any other issue opened on their GitHub)
    Anyone that says, “IPv4 is fine”
    Anyone that actively disables IPv6

Overall, it is a fun and interesting experiment, but also a sad one when seeing how many providers actually use it.

That's the end for today, and I'll see you next time!
