# naked-redirect

## Description

A Sinatra app that redirects requests for a naked domains to their www-equivalents.

For example, a request for `http://some-domain.com` would be redirected to `http://www.some-domain.com`.

## Motivation

While I am a proponent of [No-WWW](http://no-www.org) (ditching pointless www subdomain usage), there are times when I have to utilize the www subdomain instead of the naked domain.  This can happen when I'm running SSL on Heroku, locked into using Go Daddy's DNS servers, or otherwise not in a position to adhere to a www-less practice.

## Behavior

The protocol, host and query string are preserved during redirections.  However, the app only responds to GET requests.

## Deployment

This app is easily deployable to Heroku, but you can run it anywhere you can run a Rack app.

The app will redirect any domain pointed to it, so you'll just need to create an A record pointing to the IP where the app is hosted for each domain you want it to handle redirection for.

## License

* Freely distributable and licensed under the [MIT license](http://kjohnston.mit-license.org/license.html).
* Copyright (c) 2012 Kenny Johnston [![endorse](http://api.coderwall.com/kjohnston/endorsecount.png)](http://coderwall.com/kjohnston)
