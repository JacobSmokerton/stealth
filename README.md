
# Stealth - Secure, Peer-to-Peer, Private and Automatable Web Browser/Scraper/Proxy

Tholian&reg; Stealth is the automateable Web Browser for the Web of Knowledge.

Its design goals are increased Privacy, increased Automation, adaptive Semantic Understanding
and efficient bandwidth usage, no matter the cost.

It is built by a former contributor to both Chromium and Firefox, and is built out of personal
opinion on how Web Browsers should try to understand the Semantic Web.

Stealth empowers its Users, not Website Developers that could (,will ,and did) abuse technologies
to compromise the freedom and rights of Web Browser End-Users.


## Implemented Features

Stealth is both a Web Scraper, Web Service and Web Proxy that can serve its own
User Interface ("Browser UI") that is implemented using Web Technologies.

- It is secure by default, without compromise. It only supports `DNS via HTTPS`,
  and uses explicitely `https://` first, and fallsback to `http://` only when
  necessary and only when the website was not MITM-ed.

- It is peer-to-peer and always uses the most efficient way to share resources
  and to reduce bandwidth, which means that once websites are downloaded they
  can be shared with other Peers and continue to be readable, even when being
  completely offline.

- It uses `Blockers` that is on feature-parity with AdBlock Plus, AdGuard, Pi-Hole,
  uBlock Origin and uMatrix (in the sense of "all of the above").

- It uses `Optimizers` to render only the good parts of HTML and CSS. These Optimizers
  make sure that no Client or Peer ever receives any malicious or unwanted content.
  All Optimizers are applied across all `Site Modes`, and the `Site Modes` decide what
  content or media is included.

- It uses `Site Modes` that decide what to load, with incrementally allowed features
  (or media types). By default, Stealth will load nothing. The Site Mode next to the
  address bar decides what is loaded.

- It uses `Site Beacons` that label data on a Site for automated extraction purposes
  which in return help to train Stealth to understand similar Sites on the Web more easily.
  This is similar to the "Reader Mode" in other Browsers, but allows integrations with
  third-party databases and/or software in an automated manner.

- It never requests anything unnecessary. The cache is persistent until the user tells
  it to `refresh` the Site manually (or a scheduled download task runs for that URL).

- It uses trust-based `Peers` to share the local cache. Peers can receive, interchange,
  and synchronize their downloaded media. This is especially helpful in rural areas,
  where internet bandwidth is sparse; and redundant downloads can be saved.

- It can as a Content-Auditing and Content-Filtering Web Proxy for other Web Browsers,
  which allows corporate-like setups with a shared peer-to-peer Cache and a local Archive
  of the Web.

- It tries to achieve intelligent handling of Errors. In case a Site is not available anymore,
  the `stealth:fix-request` error page allows to download websites automagically from trusted
  Peers or from the [Web Archive](https://web.archive.org).

- This ain't your Mama's Web Browser. It completely disables ECMAScript in order to improve
  Privacy. Stealth also does not support any Web API that could potentially send data to
  malicious Sites.

- Stealth can be scripted as a Web Scraper inside `node.js`. The [Browser](./browser/source)
  is completely headless, so every single interaction that the [Browser UI](./browser/design)
  reflects can be implemented in a programmable manner, even remotely through trusted Peers
  using Stealth's peer-to-peer network services.


## Upcoming Features

- Stealth in combination with a connected Radar instance will allow to discover Peers, and
  to share and reuse `Beacons` and `Echoes` that help to automate even more on the Web.

- Stealth will allow Peer-to-Peer TLS encryption by using intermediary certificates that are
  shipped with each release and allow to sign Content that was downloaded via another Peer
  in a trustless manner.


## Quickstart

If you don't wanna deal with the native build toolchain, this
is how to get started as quickly as possible:

- Install [node.js](https://nodejs.org/en/download) version `12+`.
- Install [Ungoogled Chromium](https://github.com/Eloston/ungoogled-chromium/releases) version `70+`.
- (Only MacOS) Alternatively Install `Safari` version `12+`.
- (Only Linux) Alternatively Install `electron` version `8+`.
- (Only Linux) Alternatively Install `gjs` and `WebKit2 GTK` version `4+`.

```bash
git clone https://github.com/tholian-network/stealth.git;
cd ./stealth;

# Make everything
node ./make.mjs;

# Start Stealth Service (optional debug flag)
node ./stealth/stealth.mjs --debug=true;

# Open as Progressive Web App
node ./browser/browser.mjs;

# Alternatively open Stealth's Browser UI in a Web Browser
# gio open "http://localhost:65432"
```

**IMPORTANT**: On Android, Stealth can be used by visiting the URL and bookmarking it as
a Web App. The Stealth Icon will appear on your home screen, and it will behave like a
native offline-ready mobile app.


## Releases

At this point in Development, Stealth is implemented as a headless node.js Browser/Scraper/Proxy
which serves its own HTML5-based User Interface. At a later point in time, there will be native
builds available that will most likely include a custom fork of another Browser Engine with
a reduced featureset (such as without WebRTC, WebUSB etc.); but currently Stealth's Browser
uses a Webview that is preinstalled on your target Operating System.

It is heavily recommended to use [Ungoogled Chromium](https://ungoogled-software.github.io)
as a Webview if you want to run Stealth via [browser/browser.mjs](/browser/browser.mjs).

(Links will be inserted here once the Stealth releases are ready for the public)


## Stealth Guide (for Hackers?)

The [Guide](/guide/README.md) is currently meant for Developers that are new to the Project.
It explains all necessary topics to quickly get started to hack around with Stealth and modify
it to fit your needs.

A User's Guide probably will arrive at a later point in time, as Stealth currently has no
public release yet.


## Community

There's a Telegram Chat available where most technical discussions happen.
You can join it via [t.me/tholian_beta](https://t.me/tholian_beta) or search for `Tholian Beta`.


## Roadmap

The current roadmap is reflected by unimplemented [/issues](./issues) in this
GitHub repository.

A high-level roadmap is available at our Website's [Roadmap](https://tholian.network/roadmap.html),
which also lists other projects that will be built in order to integrate Stealth
with larger featuresets.

As this project in its current form is highly experimental software, those features
can change very rapidly; and lead to at least partial refactors of the codebase as
well.

If you have Problems, Suggestions or Ideas that would fit into Stealth, please open
up an Issue and we'll be happy to talk about it :)


## License

Usage of [Stealth](/stealth), including its [Browser](/browser/source) and
[Browser UI](/browser/design) is licensed under [GNU GPL 3](./LICENSE_GPL3.txt).

`(c) 2019-2020 Tholian(r) Network`

