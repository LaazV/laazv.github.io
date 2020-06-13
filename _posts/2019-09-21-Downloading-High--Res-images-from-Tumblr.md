---
layout: post
title:  Quick JS bookmarklet
categories: [JS,Code]
---
I had to download a bunch of high-res images from tumblr and I was getting a lot of low-res links (400p,800p, etc) so I wrote a small script to reload the page with the higher res image url.
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

You can add this script as a booklet by draggins <a href="javascript:!function(){var i=window.location.href.match(/(.+\d)_(\d.+)(.jpg|.gif)/);if(i&&i[0]){var o=i[1],a=i[3];if(o&&''!==o){var f=o+'_1280'+a;window.location.href=f}else;}}();">this link</a> to your bookmarks.
