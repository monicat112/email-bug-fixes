# Email Bug Fixes for iOS

* [Stop auto-highlihgting of addresses and phone links](#stop-auto-highlihgting-of-addresses-and-phone-links)

## Stop auto-highlihgting of addresses and phone links

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