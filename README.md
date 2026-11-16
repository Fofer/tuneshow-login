# TuneShow login page

A single static page that hands a Spotify login back to [TuneShow](https://github.com/Fofer/tuneshow)
running on an Apple TV.

Spotify only sends a login to an HTTPS address, but TuneShow runs at a home-network address.
Spotify redirects to this page (`https://fofer.github.io/tuneshow-login/`), and the page forwards the
browser to the Apple TV, whose address TuneShow puts in the OAuth `state` parameter.

- No data is stored or sent anywhere else, and there are no external scripts.
- It only forwards to private network addresses (10.x, 172.16–31.x, 192.168.x).
- The login code is useless without the PKCE verifier, which never leaves the Apple TV.

The source of truth is `login-page/index.html` in the TuneShow repo; this repo only publishes it.
