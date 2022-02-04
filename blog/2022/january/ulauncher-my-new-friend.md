# uLauncher, my new friend

Greetings peeps, first, happy new year, I hope 2022 will be a good year for you!

Now, let's go on with today's subject: uLauncher which is in my mind the best application launcher around.

For the little backstory, I was trying to find OBS Studio in the horrendous default XFCE start menu (yes and as much as I love XFCE, I cannot use that damned menu). I then remembered that on macOS, we have that Spotlight search bar (that you trigger using CMD+SPACE) that has to be one of the most useful things.

I then started to search a bit around the web, only to find what I looked for: uLauncher.

    Note: thanks to Cadence for mentioning the existence of Krunner and Kupfer that can fill out the exact same purpose.

Installing is effortless (at least on Arch) if you have an AUR package manager like Paru and is simply `paru -S ulauncher` (or `ulauncher-git` if you prefer to live on the edge).

After installation, a last `systemctl --user enable --now ulauncher.service` and you're all set, you can now try CTRL+SPACE to reveal the launcher and start typing.
Main window of uLauncher showing a search query for "OBS" and the results are (from top to bottom), OBS Studio, Tor Browser, Avahi Zeroconf Browser.
Sample uLauncher search.

But wait, there's more!

You can actually extend uLauncher with countless extensions which can do anything from calculating currencies to copying emojis. It is very random, but some of those are really useful.
uLauncher window showing a search for "pypi Flask-Limiter" and showing the results (from top to bottom): Flask-Limiter, limiter, Flask-Limiter-graphQL-support, wix-protos-limiter-limiter, rate-limiter, proc-limiter, sanic-limiter, requests-limiter, falcon-limiter, fps-limiter.
The 'PyPi' keyword can be used to search PyPi for packages, pressing enter will open the package page.

My current setup uses those extensions:

    Weather – Shows weather using the OpenWeatherMap API
    PyPi – Allows you to search PyPi for packages
    Calculate Anything – One of the most powerful extension that allows you to literally calculate anything from currency conversions to surface or pressure (will require you to run `pip3 install pytz pint simpleeval --user` before installing)
    NPMJs – Same thing that PyPi but with NPM
    Folder Search – Title
    Emoji – Allows you to search and copy emojis
    Symbol Search – Allows you to search and copy ASCII and Unicode symbols

In the configuration window, you will also find the search engine tab, which you can customize by bringing your own to it.
Search engine configuration tab where you can see Stack Overflow, Wikipedia, Kagi and DuckDuckGo.
The default search engines are Google, Stack Overflow and Wikipedia.

Well, I think that's enough for today, if you liked this article, you can subscribe to this blog via RSS.

Again, let me reiterate all my wishes of good health and happiness for this new year that is 2022.

I'll see you next time!
