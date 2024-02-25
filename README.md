<br/>
<p align="center">
  <a href="https://github.com/zfcsoftware/puppeteer-real-browser">
    <img src="https://github.com/zfcsoftware/puppeteer-real-browser/assets/123484092/cc8b5fb9-504a-4fd3-97f6-a51990bb4303" alt="Logo" width="80" height="80">
  </a>

  <h3 align="center">Puppeteer Real Browser</h3>

  <p align="center">
    This package prevents Puppeteer from being detected as a bot in services like Cloudflare and allows you to pass captchas without any problems. It behaves like a real browser.
    <br/>
    <br/>
    
  </p>
</p>

https://github.com/zfcsoftware/puppeteer-real-browser/assets/123484092/bd8ca2b0-a661-4248-9bf5-3ef12e3f5801

 ![Contributors](https://img.shields.io/github/contributors/zfcsoftware/puppeteer-real-browser?color=dark-green) ![Forks](https://img.shields.io/github/forks/zfcsoftware/puppeteer-real-browser?style=social) ![Stargazers](https://img.shields.io/github/stars/zfcsoftware/puppeteer-real-browser?style=social) ![Issues](https://img.shields.io/github/issues/zfcsoftware/puppeteer-real-browser) ![License](https://img.shields.io/github/license/zfcsoftware/puppeteer-real-browser) 



## Installation

If you are using a Linux operating system, xvfb must be installed for the library to work correctly.


```bash
npm i puppeteer-real-browser
```

if you are using linux:

```bash
sudo apt-get install xvfb
```



## Include

### Commanjs

```js

const start = async () => {
    var { puppeteerRealBrowser } = await import('puppeteer-real-browser')
    const { page, browser } = await puppeteerRealBrowser({})
}

```
### Module

```js

import {puppeteerRealBrowser} from 'puppeteer-real-browser'

const { page, browser } = await puppeteerRealBrowser({})

```

## Usage


```js
import { connect } from 'puppeteer-real-browser'

connect({

    headless: 'auto',

    args: []

    customConfig: {}

    skipTarget: [],

    fingerprint: true,

    turnstile: true,

    connectOption: {}

    // proxy:{
    //     host:'<proxy-host>',
    //     port:'<proxy-port>',
    //     username:'<proxy-username>',
    //     password:'<proxy-password>'
    // }

})
.then(async response => {
    const {browser, page} = response
    await page.goto('<url>')
    
})
.catch(error=>{
    console.log(error.message)
})

```

**headless**: auto can take the values true and false. If auto is set, it uses the option that is stable on the operating system in use.

**args:** Chromium başlatılırken eklemek istediğiniz ek bir flag varsa bu diziyle gönderebilirsiniz.

**customConfig:** When launch is executed, the variables you send in be onje are added. For example, you can specify the browser path with executablePath.

**skipTarget:** It uses target filter to avoid detection. You can send the targets you want to allow. This feature is in beta. Its use is not recommended.

**fingerprint:** If set to true, it injects a unique fingerprint ID into the page every time the browser is launched and prevents you from being caught.

**turnstile:** Cloudflare Turnstile automatically clicks on Captchas if set to true

**connectOption:** The variables you send when connecting to chromium created with puppeteer.connect are added



## License

Distributed under the MIT License. See [LICENSE](https://github.com/zfcsoftware/puppeteer-real-browser/blob/main/LICENSE.md) for more information.

## Thank You

* **Jimmy Laurent** - [Jimmy Laurent](https://github.com/JimmyLaurent) - *inspired by cloudflare-scraper library*
* **CrispyyBaconx** - [CrispyyBaconx](https://github.com/CrispyyBaconx) - *Contributed to converting this library to Typescript*
* **Pavle Aleksic** - [pavlealeksic](https://github.com/pavlealeksic) - *We change the fingerprint with the puppeteer-afp library.*
