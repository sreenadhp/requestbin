# We have discontinued the publicly hosted version of RequestBin due to ongoing abuse that made it very difficult to keep the site up reliably. Please see instructions below for setting up your own self-hosted instance.

Originally Created by [Jeff Lindsay](http://progrium.com)

License
-------
MIT


Looking to self-host?
=====================

[![Deploy](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy)

## Deploy your own instance using Heroku
Create a Heroku account if you haven't, then grab the RequestBin source using git:

`$ git clone git://github.com/Runscope/requestbin.git`

From the project directory, create a Heroku application:

`$ heroku create`

Add Heroku's redis addon:

`$ heroku addons:add heroku-redis`

Set an environment variable to indicate production:

`$ heroku config:set REALM=prod`

Now just deploy via git:

`$ git push heroku master`

It will push to Heroku and give you a URL that your own private RequestBin will be running.


## Deploy your own instance using Docker

On the server/machine you want to host this, you'll first need a machine with
docker and docker-compose installed, then grab the RequestBin source using git:

`$ git clone git://github.com/Runscope/requestbin.git`

Go into the project directory and then build and start the containers

```
$ sudo docker-compose build
$ sudo docker-compose up -d
```

Your own private RequestBin will be running on this server.


Contributors
------------
 * Barry Carlyon <barry@barrycarlyon.co.uk>
 * Jeff Lindsay <progrium@gmail.com>
++++++++++++++++++++++++++++++++++++


Source: https://blog.polydojo.com/2018/03/webdev-bye-requestbin-hello-alternatives.html
> One could still self-host RequestBin; and that is pretty sweet. But when you're tasked with setting up webhooks, do you really also want to be in-charge of provisioning the webhook-testing infrastructure?
Alternatives
* Webhook Inbox is created by the folks at Fanout.io.   Includes live reloads and a beautiful UI. We've found the tool to be very reliable.
* Hookbin, by the creators of Kraken.io.
  Seems to include live uploads, but we were often unable to inspect requests.
* Webhook Tester by @fredsted.
  UI could be improved, but UX is awesome. Live reloads, pretty-JSON option, header-hiding etc.

Other Helpful Links
* UltraHook, created by the folks behind Enchant.
  A tool for testing incoming webhooks on localhost. Involves a ruby gem and an API key.
* MockBin by Mashape/Kong.
  Tool for setting endpoints that spit-out a fixed response. (We were unable to try it out.)
* HTTPBin.org.
  Neat set of utility endpoints that'll prove useful while developing your next project.
