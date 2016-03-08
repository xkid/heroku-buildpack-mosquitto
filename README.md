This buildpack will build the mosquitto MQTT client and broker program to a
Heroku container.

This is intended to be used alongside ``heroku-buildpack-apt`` and, optionally,
``heroku-buildpack-multi`` (although you can use the "official" approach to
multiple build packs as well).

The Aptfile I used is shown below:

```
pkg-config
cmake
openssl
libc-ares-dev
```

The ``.buildpacks`` file I used (since I used ``heroku-buildpack-apt``) is
shown below:

```
https://github.com/ddollar/heroku-buildpack-apt.git
https://github.com/swails/heroku-buildpack-mosquitto.git
https://github.com/heroku/heroku-buildpack-python.git
```

Of course, if your project is not Python-based, switch the final buildpack
with the one appropriate for your language of choice.
