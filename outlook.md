# Email Bug Fixes for Outlook

* [Custom fonts and fallbacks in Outlook](#custom-fonts-and-fallbacks-in-outlook)
* [Stop link underlining in Outlook](#stop-link-underlining-in-outlook)
* [Remove extra space around Outlook tables](#remove-extra-space-around-outlook-tables)
* [Customize an Outlook signature's code](#customize-an-outlook-signatures-code)

## Custom fonts and fallbacks in Outlook

https://litmus.com/blog/the-ultimate-guide-to-web-fonts

If you have an inliner task running, make sure it isn't deleting link tags. To do this for gulp-inline-css, add `"removeLinkTags": false`

Then add this:

```html
<head>
<!--[if !mso]><!-->
<link href="https://fonts.googleapis.com/css?family=Open+Sans:400,700" rel="stylesheet">
<!--<![endif]-->
<!--[if mso]>
<style type="text/css">body, table, td, p, li, a, span, h1, h2, h3, h4, h5, h6 {font-family: Arial, Helvetica, sans-serif !important;}</style>
<![endif]-->
</head>
```

And to really bulletproof the font, go to the webfont url in-browser and copy/paste the font face delcaration into the head as well:

```html
<head>
    <style>
        @font-face {
            font-family: 'Open Sans';
            font-style: normal;
            font-weight: 400;
            src: local('Open Sans Regular'), local('OpenSans-Regular'), url(https://fonts.gstatic.com/s/opensans/v15/mem8YaGs126MiZpBA-UFWJ0bbck.woff2) format('woff2');
            }
    </style>
</head>
```
Use .woff files if possible.

## Stop link underlining in Outlook

```html
<head>
    <!--[if (mso)|(mso 16)]>
    <style type="text/css">
        a {text-decoration: none !important;}
    </style>
    <![endif]-->
</head>
```

## Remove extra space around Outlook tables

https://litmus.com/community/discussions/371-outlook-gaps-around-tables

```html
<table style="border-collapse:collapse; mso-table-lspace:0pt; mso-table-rspace:0pt;" cellspacing="0" cellpadding="0" border="0" align="left">
<td style="border-collapse: collapse;">
```  

[Ghost tables](http://labs.actionrocket.co/make_mobile_email_work_in_outlook) are supposed to be a good fix too.

## Customize an Outlook signature's code

Edit the .txt, .rtf, and .htm files in `C:\Users\USERNAME\AppData\Roaming\Microsoft\Signatures` (in Windows)

Resources:  
1. https://www.msoutlook.info/question/backup-and-restore-signatures
2. https://www.msoutlook.info/question/signature-images-not-sending-or-visible-for-receiver 