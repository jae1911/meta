# Tor Support

Greetings everyone, today a post on the Tor support that just shipped on my services.

As you may have seen on my Mastodon, all major services now have a Tor address, which are:

    Jae.fi http://yrotq4focci5usml65pb6iqxfkhoer6y5rx2ldnlm3m7g56wyb4fvnid.onion/
    blog.jae.fi http://zra5rukmfdg4cavftt2btll6nws2xdbt4qnhhx66zlm7ntf4s4v37xyd.onion/
    Jae.li http://v5grxpif5sefmek5jhua6i2xlcybjtqzs2qenxd6tqm3yzojsnp7qiyd.onion/
    Furries.tech http://l7jbeg4peaifgg5omujpywnj545rqlswfyrb67x5noxtyqgmk37qzaqd.onion/
    as211696.net http://nxtov4ippcxqz2f2s545xah26xrovwua7wsj5jdimklq7rdea3vxbaqd.onion/
    tube.as211696.net http://u3aha6t742jszn7ticayn6qfxuve574o3eysesvjpy7gpiv4ljb3ipyd.onion/

All services were migrated without a hiccup except for the blog which runs on Ghost. The software doesn't support multiple hosts and this was causing problems as it was trying to upgrade the Tor URL to an HTTPS one. The solution was pretty easy: create a mirror blog which uses the same database as the first one that only serves on the ONION address.

I will never block Tor, and having onion addresses is now the default on my host.

I'll see you next time!
