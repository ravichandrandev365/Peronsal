# Remove all videos from Watch Later

Source Link: https://gist.github.com/astamicu/eb351ce10451f1a51b71a1287d36880f

```js
setInterval(function () {
    video = document.getElementsByTagName('ytd-playlist-video-renderer')[0];

    video.querySelector('#primary button[aria-label="Action menu"]').click();

    var things = document.evaluate(
        '//span[contains(text(),"Remove from")]',
        document,
        null,
        XPathResult.ORDERED_NODE_SNAPSHOT_TYPE,
        null
    );

    for (var i = 0; i < things.snapshotLength; i++) 
    {
        things.snapshotItem(i).click();
    }
}, 500);
```

