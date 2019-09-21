---
layout: post
title:  Quick JS bookmarklet
categories: [JS,Code]
---


I was downloading a huge amount of Concept Art from Tumblr and it was super annoying that most of the links were referencing the low resolution images (400p, 800p, etc).. So I wrote a this small bookmarklet to load the high resolution images
```
(function() {
 var baseUrl = window.location.href;
 var TumblrLink = baseUrl.match(/(.+\d)_(\d.+)(.jpg|.gif)/);
  if (!TumblrLink || !TumblrLink[0]) {
    return;
  }
  var baseLink = TumblrLink[1];
  var extension = TumblrLink[3];
  if (baseLink && baseLink !== "") {
  var targetUrl = baseLink + "_1280" + extension;
  window.location.href = targetUrl;
  return;
  }
})();
```

Add <a href="javascript:!function(){var i=window.location.href.match(/(.+\d)_(\d.+)(.jpg|.gif)/);if(i&&i[0]){var o=i[1],a=i[3];if(o&&''!==o){var f=o+'_1280'+a;window.location.href=f}else;}}();">this link</a> to your bookmarklets.
