# Email Bug Fixes for iOS

* [Stop auto-highlihgting of addresses and phone links](#stop-auto-highlihgting-of-addresses-and-phone-links)
* [Fix scaling issues](#fix-scaling-issues)

## Stop auto-highlighting of addresses and phone links

https://litmus.com/blog/update-banning-blue-links-on-ios-devices

Apple injects a link that has a `x-apple-data-detector` attribute, so we can target that.

```css
a[x-apple-data-detectors] {
        color: inherit !important;
        text-decoration: none !important;
        font-size: inherit !important;
        font-family: inherit !important;
        font-weight: inherit !important;
        line-height: inherit !important;
      }
```

## Fix scaling issues

https://litmus.com/blog/what-email-marketers-need-to-know-about-ios-11-and-the-new-iphones

On iOS 11, emails appear off center and don't fit the full width of the screen. This should fix it.

```html
<meta name="x-apple-disable-message-reformatting">
```

You may also need to set `width: 100%` to some html tags.
