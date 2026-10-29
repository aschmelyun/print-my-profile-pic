# print-my-profile-pic

Star this repo to have your GitHub profile picture framed, printed out on my receipt printer, and stuck to my wall. 

That's it!

> [!TIP]
> If you give a one-time [sponsorship](https://github.com/sponsors/aschmelyun?frequency=one-time&sponsor=aschmelyun) of any amount beforehand, your profile picture will be printed in a **special frame**.

<img width="480" height="270" alt="Holding up a photo of me printed on a receipt" src="https://github.com/user-attachments/assets/5a0cf6d9-b619-4a01-bf2f-5fe0a7f9dd24" />

## How's it work?

GitHub allows you to create webhooks for specific events on your repos, I've set one up for [starring](https://docs.github.com/en/webhooks/webhook-events-and-payloads#star) this project.

When that happens, a payload is POSTed to a [Cloudflare tunnel](https://developers.cloudflare.com/tunnel/) domain, which leads to a PHP script running on a Raspberry Pi that's sitting on my desk.

From the inbound request, you can gleen info about the person who starred the repo, like their display name and avatar URL. The script takes their profile picture, renders it behind a cut-out of a photo frame, and then adds some other info I thought should be included in each receipt.

The RPi is connected to an Epson TM-T88IV thermal receipt printer via USB, and the PHP script uses my go-to [escpos-php](https://github.com/mike42/escpos-php) library to format the receipt data and send it off to the printer.

## But why?

It sounded fun when my friend [Sam](https://x.com/samwhoo) mentioned it. That's pretty much it!

## What now?

I'll periodically update this README with a picture of the pinboard I've dubbed the "Hall of Frame" as pictures get added to it. 

Want to add a new frame? Send in a PR! 
