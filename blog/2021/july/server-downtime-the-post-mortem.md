# Server downtime, the post mortem

Hey everyone, as you may have seen yesterday, all services were offline for several hours after a maintenance concerning the disks of the current server.

I decided to replace one of the 300Gb disks for a newer 2Tb one from Seagate, which I bought brand new from Verkkokauppa. Near 13:00 UTC+3, I installed the disk onto the physical host and performed a clean installation of VMware ESXi.

Quickly, I realized something was wrong, the fans were louder than usual and the server was not shutting up after some time like it usually does. I then jumped into iLO and saw, the temperature reading of the disk which was at around 50C which was causing the fans to go as fast as possible (79% according to ESXi's sensors readings).

By security, I decided to shut down the server until the disk problem is resolved (and mainly because I couldn't sleep with all the noise it was doing).

Turns out... HP hardware doesn't like unapproved hardware to be attached to it. After some research, it turns out only a bunch of disk have sensors that register correctly with iLO. Luckily, one of those is a Western Digital Blue that was sold at Verkkokauppa, so I got one this morning, 2Tb as the disk before.

The new disk installed, the server is as quiet as before. All services are restored and back to normal as of now.

So, if you own an HP server and want to upgrade the disks, stay away from the Seagate ST2000LM015 and pick a WD Blue WD20SPZX instead (at least for my ProLiant DL360 G7).

I'll see you next time!
