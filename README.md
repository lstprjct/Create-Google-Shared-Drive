<div align="center">
  <h2>Create Google Shared Drive</h2><br />


[![Create-Google-Shared-Drive](https://cdn.jsdelivr.net/gh/ParveenBhadooOfficial/Create-Google-Shared-Drive@master/screen-shot.png)](https://github.com/ParveenBhadooOfficial/Create-Google-Shared-Drive)


</div>


## Get Required Data from 

Note: `You must have permissions to create shared drive in your account. This doesn't work with GMAIL Accounts, Required Gsuite Business+ Accounts. To check Open Google Drive and try to create Shared Drive first.`

### Easy and Automatic Way

* Open https://generator.driveindex.ga
* Authenticate
* Generate Code
* Copy values from `client_id: '', client_secret: '', refresh_token: ''`.
* Paste them in Line 4,5 and 6 at [workers.js](https://github.com/ParveenBhadooOfficial/Create-Google-Shared-Drive/blob/master/workers.js).
* Copy the Code and paste it into https://workers.cloudflare.com Site.

### Manual and Difficult

* Open [Google Cloud Console](https://console.developers.google.com/apis/credentials)
* After creating project or if you already have one.
* Enable Drive API from [Here](https://console.developers.google.com/apis/library/drive.googleapis.com?q=drive)
* Click create credentials.
* Select OAuth client ID.
* Select Web application.
* Give it a name. (anything for your own reference)
* In Authorized JavaScript origins add `https://developers.google.com`
* In Authorized redirect URIs add `https://developers.google.com/oauthplayground`
* Save and note down your Client ID and Secret
* Open [Developers Playground](https://developers.google.com/oauthplayground)
* On Right Top Side click on Setting Icon ![Settings](https://developers.google.com/oauthplayground/assets/images/settings.png)
* Click on Use your own OAuth credentials.
* Enter OAuth Client ID: and OAuth Client secret:
* Now back to same page [Developers Playground](https://developers.google.com/oauthplayground) left side Step 1 i.e. Select & authorize APIs
* Find Drive API v3
* Select First Option i.e. https://www.googleapis.com/auth/drive (Required)
* Click on Authorize API. and give permissions using your google account.
* It will turn to Step 2 Exchange authorization code for tokens at the end of authentication.
* Click on Exchange authorization code for tokens, if it goes to step 3, click on Step 2 yourself.
* Select the option Auto-refresh the token before it expires.
* Copy the refresh token and paste in Line 6 of [workers.js](https://github.com/ParveenBhadooOfficial/Create-Google-Shared-Drive/blob/master/workers.js) along with your own Client ID and Secret at Line 4 and Line 5.
* Copy the Code and paste it into https://workers.cloudflare.com Site.

## For new users (What to do at Cloudflare exactly)

* Create an account at [Cloudflare.com](https://www.cloudflare.com)
* Click on `Workers` and Select `Free Plan`. (Right side of main Dashboard)
* Setup an username if you're new, i.e. `<username>.workers.dev`
* While `<username>.workers.dev` won't display anything when accessed using a browsers you can create `*.<username>.workers.dev` where * can be anything without using dots.
* Click on create a worker and paste your code in it. rename the worker as you like, it can be anything.
* Click on Deploy. (Your work is done, next steps are if you're linking `custom domain`.
* Add a domain or open `dns` if already added.

<div align="center">

[![DNS and Workers](https://cdn.jsdelivr.net/gh/ParveenBhadooOfficial/Create-Google-Shared-Drive@master/dns-workers.png)](https://github.com/ParveenBhadooOfficial/Create-Google-Shared-Drive)

</div>

* Add an `A` Record with your desired name (for `example.com` it is `@` and for `mysite.example.com` it is `mysite`) with IP Address `192.2.0.1` make sure Proxy is on i.e. the Cloud color should be `Orange`.
* Now click on `Workers` in Menu.
* Click on `Add Route`.

<div align="center">

[![Route](https://cdn.jsdelivr.net/gh/ParveenBhadooOfficial/Create-Google-Shared-Drive@master/route.png)](https://github.com/ParveenBhadooOfficial/Create-Google-Shared-Drive)

</div>

* Enter your custom website you selected above, for us here it will be `example.com/*` or `mysite.example.com/*`, don't forget to add `/*` or pages like `mysite.example.com/anything` will not work.
* Select the worker you just deployed.
* Click on Save.

Note: Replace `example.com` here with your own domain name.

## Credits

* Theme from [Colorlib](https://colorlib.com)
* Source: [yyuueexxiinngg](https://github.com/yyuueexxiinngg/some-scripts/blob/master/workers/google/drive/create-share-teamdrive.js)
* Special Thanks: [donwa](https://github.com/donwa/goindex)
* Another Thanks: [Sumit Bot](https://t.me/isumitbot)
* CDN used: [jsDelivr](https://jsdelivr.com)
