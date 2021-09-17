# Local Storage

## [THE PAST, PRESENT & FUTURE OF LOCAL STORAGE FOR WEB APPLICATIONS](http://diveinto.html5doctor.com/storage.html)

Parts of this one definitely went over my head.

Some of the backstory of the web that I learned:
There has always been a battle between native client applications and web applications. I'm assuming this means things like Microsoft Word, Photoshop, etc - things designed to be run on a local machine.

Web applications can't use the same storage solutions that a local machine can. The article states "Cookies were invented early in the web's history, and indeed they can be used for persistent local storage of small amounts of data"  then lists some problems with cookies.

1. Cookies are in every HTTP request and are transmitted constantly, with duplicate data every time.
2. Cookies send unencrypted data
3. Limited to 4KB of data.

Apparently, HTML5 helps with some of this.

> "So what is HTML5 Storage? Simply put it's a way for web pages to store named key/value pairs locally, within the client browser"

Right now I am taking key/value pairing for granted, but obviously it is the foundation for most objects in Javascript, and I am assuming many other programming languages as well.

HTML5 Storage then stores key/value pairs with data. Both the key and value are stored as a string, even though it can hold different data types.

It seems that this storage can also store 5mb, but cannot request more storage space of a user. The article is a bit dated though so maybe this has changed since then.

Next part is a bit confusing, but it seems like instead of having to do a complete refresh of data, it can save progress using a specific function, that use another to start off from that save point.

I love the call out about SQL - as I've learned about SQL I too have found that there are many different flavors. I only do a bit in Mode, but luckily they share similar syntax.

Ultimately I need to do more research as I'm sure local storage has come a long way, but I'm assuming the reason we were assigned this is that HTML 5 has been the standard for a while.