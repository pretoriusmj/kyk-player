# kyk-player

A single static page used by **Kyk**, a personal YouTube front-end for a Samsung TV.

YouTube's embedded player refuses to play inside an installed TV app, because the app has no
web address to send as the embedding page (error 153). Kyk therefore loads `player.html` from
here: it embeds the standard YouTube player like any website does, and passes the IFrame
API's `postMessage` traffic between Kyk and the player.

No keys, accounts or data live here. The page only accepts a video id (`?v=`) and an optional
start time (`&start=`).

## remote.html — phone remote

`remote.html` is Kyk's phone remote (Android and iPhone; add it to the home screen). The TV's QR
code opens it with a pairing secret in the URL fragment (`#k=…`). The page keeps the secret in the
phone's storage and removes it from the address bar. Phone and TV exchange small JSON messages
through two private ntfy.sh topics derived from that secret, published with `cache=no`.
