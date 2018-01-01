# Internet

## Websites on the Internet

How do they work? 

https://projects.propublica.org/graphics/images/data-institute/presentations/how-websites-work.pdf

## Internet Basics

https://developer.mozilla.org/en-US/docs/Learn/Common_questions/How_does_the_Internet_work

* Internet - a network of networks
* "World Wide Web" - a service built on top of the internet's infrastructure (other services include e-mail and IRC chat, neither of which use HTTP)
	* HTML - Hypertext Markup Language
	* HTTP - Hypertext Transfer Protocol

## DNS Lookup

![](https://mdn.mozillademos.org/files/8961/2014-10-dns-request2.png)
Source: [Mozilla Developer Network](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_domain_name)

#### ![#c5f015](https://placehold.it/15/c5f015/000000?text=+) Example

There are lots of programs that can resolve a domain name for you, one of those is [`dig` (domain information groper)](https://www.tecmint.com/10-linux-dig-domain-information-groper-commands-to-query-dns/).

```
dig google.com +short
```

## The Internet has Layers
![](https://upload.wikimedia.org/wikipedia/commons/thumb/4/47/Osi-model-jb.svg/415px-Osi-model-jb.svg.png)

Source: [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Osi-model-jb.svg)

If you're really interested:

* https://www.lifewire.com/open-systems-interconnection-model-816290
* https://www.lifewire.com/layers-of-the-osi-model-illustrated-818017

And if you're not:

* ![](https://lh3.googleusercontent.com/rEUe8A2Dzw7Kbkhkv3Zzp7VOl8mi0NteVfbvWtppi04eiL3jKVrgUa2pUblfRGdYPkrW=w50) [Networks have layers!](https://www.youtube.com/watch?v=NxwNcgEjWBo)

## Routing

Data travels on the internet in "packets". 

While we're on the subject of strange videos:

* [Animated Packets](https://www.youtube.com/watch?v=L8VpthhRaEg)

How packets Travel:
https://en.wikibooks.org/wiki/A-level_Computing/AQA/Computer_Components,_The_Stored_Program_Concept_and_the_Internet/Structure_of_the_Internet/Packet_switching


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
