# Basics

## Client vs Server

Basic Network
![](https://mdn.mozillademos.org/files/8973/Client-server.jpg)
Source: [Mozilla Developer Network](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/How_the_Web_works)

* **Client** - you using your web browser on your computer, phone, smartwatch,etc...
* **Server** - computers that store and serve up webpages, sites, apps etc...

## Lets Zoom In

Part of the beauty of the web is that any node can be a server. You don't need special hardware. Your computer, your watch, your raspberry pi, your fridge - with the right programming, any one of them can be a server.

The term "server" can sometimes be used ambiguously, it can refer the **software** that is serving the data or the **hardware** (the actual device) that is running that software.

### Static Web Server
![](https://mdn.mozillademos.org/files/8659/web-server.svg)
Source: [Mozilla Developer Network](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_web_server)

#### ![#c5f015](https://placehold.it/15/c5f015/000000?text=+) Example

Setting up a local server:

```
cd ~/Development/Harvard/simple-website
python2 -m SimpleHTTPServer 8000
```

Navigate to `http://localhost:8000/` in your web browser

#### Localhost

* `127.0.0.1` or `localhost` resolves to *This Computer*
* `0.0.0.0` will also work. It means something slightly different, but we won't get into that. If you want to know, do some googling! There are some decent explanations on stackoverflow.

#### Ports

Notice the example above navigates to the IP address `0.0.0.0` and port `8000`. A **port** is like an extention to a telephone number. Once you've hit the IP address of the correct server, it may be serving different traffic through different ports. The default port for HTTP traffic is port `80`, however you can serve a website through any port you'd like.

Here is a [list of common port numbers](https://en.wikipedia.org/wiki/Port_(computer_networking)#Common_port_numbers), it would be best to avoid serving a website through any of these.

* https://en.wikipedia.org/wiki/Port_(computer_networking)#Common_port_numbers

If you're just testing a website, its a good idea to use a higher number (like `8000` or `8080`, at FiveThirtyEight we use port `5380`) so that it doesn't conflict with other kinds of traffic. Most websites in production will be served on port `80` (that's where browsers look for it by default).

#### ![#c5f015](https://placehold.it/15/c5f015/000000?text=+) Example

Get the IP address for a website.

```
dig google.com
```

Then you can plug that IP into the browser with a port. `XXX.XXX.XXX.XXX:80` will take you to that website's homepage, but another port `XXX.XXX.XXX.XXX:9100` for example, will error out.

## How Websites Work

https://projects.propublica.org/graphics/images/data-institute/presentations/how-websites-work.pdf

## DNS Lookup

![](https://mdn.mozillademos.org/files/8961/2014-10-dns-request2.png)
Source: [Mozilla Developer Network](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_domain_name)


arp
dig
resolveip
nslookup
nc

## The Internet vs "The Web"

Network
https://developer.mozilla.org/en-US/docs/Learn/Common_questions/How_does_the_Internet_work

* Router
* Modem

Packet Switched Network
traceroute

## Client vs Server - no real difference

NGROK HTML PAGE (and or flask app)
https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_web_server

## Static vs Dynamic

### Static Web Server
![](https://mdn.mozillademos.org/files/13841/Basic%20Static%20App%20Server.png)
Source: [Mozilla Developer Network](https://developer.mozilla.org/en-US/docs/Learn/Server-side/First_steps/Introduction)

A static web server simply serves files.

### Dynamic Web Server
![](https://mdn.mozillademos.org/files/13839/Web%20Application%20with%20HTML%20and%20Steps.png)

Source: [Mozilla Developer Network](https://developer.mozilla.org/en-US/docs/Learn/Server-side/First_steps/Introduction)

A dynamic web server might do a lot of things. Check to see if you're logged in, get personalized information, communicate with a database, communicate with other web applications etc.

#### Web Frameworks

* **Ruby**: Ruby on Rails, Sinatra
* **Python**: Django, Flask
* **JavaScript (nodeJS)**: Angular, React, Backbone, Ember ...
* Others you may have heard of (like ASP.NET) https://en.wikipedia.org/wiki/Comparison_of_web_frameworks

#### ![#c5f015](https://placehold.it/15/c5f015/000000?text=+) Example

 * https://projects.fivethirtyeight.com/trump-approval-ratings/
 * Polls Backend [URL Redacted]

## OSI Stack

## Routing

## HTTP
[http://slides.com/dhrumilmehta/how-to-tell-a-story-with-data-tools-of-the-trade#/6/4](http://slides.com/dhrumilmehta/how-to-tell-a-story-with-data-tools-of-the-trade#/6/4)

[http://slides.com/dhrumilmehta/how-to-tell-a-story-with-data-tools-of-the-trade#/6/5](http://slides.com/dhrumilmehta/how-to-tell-a-story-with-data-tools-of-the-trade#/6/5)

## Examples

[http://money.cnn.com/2015/01/21/technology/security/obamacare-website-advertisers/](http://money.cnn.com/2015/01/21/technology/security/obamacare-website-advertisers/)

[https://www.eff.org/deeplinks/2015/01/healthcare.gov-sends-personal-data](https://www.eff.org/deeplinks/2015/01/healthcare.gov-sends-personal-data)

[https://fivethirtyeight.com/features/fandango-movies-ratings/](https://fivethirtyeight.com/features/fandango-movies-ratings/)

### Hanging out in the Network Tab

Simple request to your simple website.
[https://dmil.github.io/dhrumil-simple-website/](https://dmil.github.io/dhrumil-simple-website/)

Modifying a facebook profile picture.

Making the Ad Go Away on Kami

```
$("html #outerContainer.adsVisible > #mainContainer").css("right", 0);
```
Modifying CSS

Modifying JavaScript


### Cookies

Types of Cookies

[https://en.wikipedia.org/wiki/HTTP_cookie#Terminology](https://en.wikipedia.org/wiki/HTTP_cookie#Terminology)

Check out the cookies on a website.

https://www.dccourts.gov/cco/maincase.jsf

### Poll
intercom.io

### Not a cookie, but interesting
https://www.propublica.org/about/pixelping

## Try It

Tell me everything you can find out about a website from the network tab.

- cookies
- technologies the website uses
- what takes a long time to load / large elements on page
- local storage

## Quote

![](https://www.evernote.com/shard/s150/sh/ea7383a1-438d-4fba-8706-cd21af484ac6/56e394f2b6f72325/res/300ce791-5f8f-4ec9-b0ad-44b5f4957365/skitch.png?resizeSmall&width=832)

Free to Make: How the Maker Movement is Changing Our Schools, Our Jobs, and Our Minds - by Dale Dougherty
