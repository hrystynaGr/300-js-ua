### What is a cookie?
**Cookie** is a text file stored on a user's machine by a web browser, which can contain information about authorization, visited pages, theme preferences, etc. Cookies can be session-long or permanent. Session-long cookies disappear when the user closes the browser, while permanent cookies can be stored for hours, days, weeks, or even years, but they always have an expiration date (max age for Chrome as for now is 400 days).

**Cookie vs. SessionStorage** - cookies are stored on a user's machine and are sent to the server with every HTTP request, while session storage files are stored on users' machine as well but they are not sent with each request. Cookie could be up to 4kb, while session storage can store 5-10mb per domain.

**Where to find cookies?**
*DevTools-Application-Cookies* (for the Chrome browser).

Cookies can be used for malware:
> Zombie cookies - cookies that restore themselves after being deleted.
> Third-party cookies. For example, I am browsing jeans.com, looking for new jeans, but at the same time, cookies from adwebsite.com I have visited earlier are tracking my actions on jeans.com. This is the main reason why you need to review the cookie policy of the website before accepting it.
