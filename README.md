# kyk-player

A single static page used by **Kyk**, a personal YouTube front-end for a Samsung TV.

YouTube's embedded player refuses to play inside an installed TV app, because the app has no
web address to send as the embedding page (error 153). Kyk therefore loads `player.html` from
here: it embeds the standard YouTube player like any website does, and passes the IFrame
API's `postMessage` traffic between Kyk and the player.

No keys, accounts or data live here. The page only accepts a video id (`?v=`) and an optional
start time (`&start=`).
