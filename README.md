# nonocache-sw.js

A service worker to develop sites that rely on files from a CDN, and DevTools with Disable Cache enabled.

## How to use

Copy `nonocache-sw.js` to your app root folder. Add this code to your app. Ideally can be run as early as possible.

```
if ("serviceWorker" in navigator) {
  navigator.serviceWorker.register("./nonocache-sw.js", { scope: "./" });
}
```

If you want to change the location or scope of your service worker, make sure they match.

In `nonocache-sw.js` there's a list of domains that will be matched in the fetch requests. It can be the start of the domains you'd like cached, or paths in your app:

`http://www.domain.com/files` will match `http://www.domain.com/files/foo.js` and `http://www.domain.com/files/bar.css`
`libs/` will match `localhost:8080/libs/foo.js`
