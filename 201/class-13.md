# Local Storage and How To Use It On Websites

#### Reference Links
https://www.smashingmagazine.com/2010/10/local-storage-and-how-to-use-it/

http://diveinto.html5doctor.com/storage.html

Local storage is how we store information locally on a user’s computer.

### Adding State To The Web: The “Why” Of Local Storage

The main problem with HTTP as the main transport layer of the Web is that it is stateless. This means that when you use an application and then
close it, its state will be reset the next time you open it. If you close an application on your desktop and re-open it, its most recent state is 
restored.

This is why, as a developer, you need to store the state of your interface somewhere. Normally, this is done server-side, and you would check the 
user name to know which state to revert to. But what if you don’t want to force people to sign up?

Local storage allows you to keep a key on the user’s computer and read it out when the user returns.

### C Is For Cookie. Is That Good Enough For Me?

A cookie is a text file hosted on the user’s computer and connected to the domain that your website runs on. You can store information in them, 
read them out and delete them. Cookies have a few limitations though:

1) They add to the load of every document accessed on the domain.
2) They allow up to only 4 KB of data storage.
3) Because cookies have been used to spy on people’s surfing behavior, security-conscious people and companies turn them off or request to be 
   asked every time whether a cookie should be set.
   
To work around the issue of local storage — with cookies being a rather dated solution to the problem — the WHATWG and W3C came up with a few 
local storage specs, which were originally a part of HTML5 but then put aside because HTML5 was already big enough.

#### Local storage specs link
https://html.spec.whatwg.org/multipage/webstorage.html
Intro, The API, Privacy, Security.

### Using Local Storage In HTML5-Capable Browsers

Using local storage in modern browsers is ridiculously easy. All you have to do is modify the localStorage object in JavaScript. You can do that directly or (and this is probably cleaner) use the setItem() and getItem() method:

```
localStorage.setItem('favoriteflavor','vanilla');
```
If you read out the favoriteflavor key, you will get back “vanilla”:
,,,
var taste = localStorage.getItem('favoriteflavor');
// -> "vanilla"
,,,

To remove the item, you can use — can you guess? — the removeItem() method:

```
localStorage.removeItem('favoriteflavor');
var taste = localStorage.getItem('favoriteflavor');
// -> null
```


#### Questions

1) Why would a developer use local storage for a web application?
LocalStorage is a property that allows JavaScript sites and apps to save key-value pairs in a web browser with no expiration date. This means the data stored in the browser will persist even after the browser window is closed.

2) What information should not be stored in local storage?
Do not store passwords or personal information in local storage as it is not secure.

3) Local storage can store what type of data? How would you convert it to that type before storing?
Local storage can only store data as a string. You can convert data to a string using JSON.stringify and convert it back when called using JSON.parse.



