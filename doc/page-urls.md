To override the URL in the `gtag()` function, use the `page_location` parameter. This parameter allows you to set a custom URL instead of the one automatically detected by Google Analytics.
https://developers.google.com/analytics/devguides/collection/ga4/reference/config#page_referrer

### Example:

```javascript
gtag('config', 'STREM_ID', {
    'page?referrer': 'https://www-02.zkb.ch/test-referrer-path',
    'page_location': 'https://www-02.zkb.ch/test-path',
    'page_title': 'test-page-title',
    'page_path': '/test-path',
})
```

If you need to override the user agent, you would need to use a server-side solution like the Google Analytics Measurement Protocol. This is because the user agent string is part of the HTTP request headers, which the browser handles automatically.

### Workaround Options:
1. Measurement Protocol (Server-side): You can send data from your server directly to Google Analytics, and in that request, you can specify a custom user agent using the ua parameter.
2. Proxy the Request: Another method is to proxy requests through a server, where you can modify headers (including the user agent) before forwarding the data to Google Analytics.

### Example unmodified
```javascript
fetch("https://9388422.fls.doubleclick.net/activityi;src=9388422;type=test_type0;cat=test_cat;ord=4737966129511;npa=1;auiddc=552227943.1725950227;ps=1;pcor=976106515;uaa=x86;uab=64;uafvl=Chromium%3B128.0.6613.120%7CNot%253BA%253DBrand%3B24.0.0.0%7CGoogle%2520Chrome%3B128.0.6613.120;uamb=0;uam=;uap=Windows;uapv=15.0.0;uaw=0;pscdl=noapi;frm=0;gtm=45fe45f0za200;gcs=G110;gcd=13r3p3r3p5;dma=0;epver=2;~oref=https%3A%2F%2Fwww.zkb.ch%2F?", {
  "headers": {
    "accept": "text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7",
    "accept-language": "en-US,en;q=0.9,de;q=0.8,fr;q=0.7",
    "cache-control": "no-cache",
    "pragma": "no-cache",
    "priority": "u=0, i",
    "sec-ch-ua": "\"Chromium\";v=\"128\", \"Not;A=Brand\";v=\"24\", \"Google Chrome\";v=\"128\"",
    "sec-ch-ua-mobile": "?0",
    "sec-ch-ua-platform": "\"Windows\"",
    "sec-fetch-dest": "iframe",
    "sec-fetch-mode": "navigate",
    "sec-fetch-site": "cross-site",
    "sec-fetch-user": "?1",
    "upgrade-insecure-requests": "1",
    "x-client-data": "CK21yQEIibbJAQiltskBCKmdygEIiOTKAQiVocsBCOWYzQEIhaDNAQ=="
  },
  "referrer": "https://www.zkb.ch/",
  "referrerPolicy": "strict-origin-when-cross-origin",
  "body": null,
  "method": "GET",
  "mode": "cors",
  "credentials": "include"
});
```



### Example modified
**Nevertheless no change was found in the fetch.**

```javascript
fetch("https://9388422.fls.doubleclick.net/activityi;src=9388422;type=test_type0;cat=test_cat;ord=6398778055660;npa=1;auiddc=552227943.1725950227;ps=1;pcor=626053637;uaa=x86;uab=64;uafvl=Chromium%3B128.0.6613.120%7CNot%253BA%253DBrand%3B24.0.0.0%7CGoogle%2520Chrome%3B128.0.6613.120;uamb=0;uam=;uap=Windows;uapv=15.0.0;uaw=0;pscdl=noapi;frm=0;gtm=45fe45f0za200;gcs=G110;gcd=13r3p3r3p5;dma=0;epver=2;~oref=https%3A%2F%2Fwww.zkb.ch%2F?", {
	"headers": {
		"accept": "text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7",
		"accept-language": "en-US,en;q=0.9,de;q=0.8,fr;q=0.7",
		"cache-control": "no-cache",
		"pragma": "no-cache",
		"priority": "u=0, i",
		"sec-ch-ua": "\"Chromium\";v=\"128\", \"Not;A=Brand\";v=\"24\", \"Google Chrome\";v=\"128\"",
		"sec-ch-ua-mobile": "?0",
		"sec-ch-ua-platform": "\"Windows\"",
		"sec-fetch-dest": "iframe",
		"sec-fetch-mode": "navigate",
		"sec-fetch-site": "cross-site",
		"sec-fetch-user": "?1",
		"upgrade-insecure-requests": "1",
		"x-client-data": "CK21yQEIibbJAQiltskBCKmdygEIiOTKAQiVocsBCOWYzQEIhaDNAQ=="
	},
	"referrer": "https://www.zkb.ch/",
	"referrerPolicy": "strict-origin-when-cross-origin",
	"body": null,
	"method": "GET",
	"mode": "cors",
	"credentials": "include"
});
```
