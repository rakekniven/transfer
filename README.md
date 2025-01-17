# Nextcloud "Transfer" app

This app allows you to have a file from the Internet transferred directly into
your Nextcloud, without first having to download it to your personal device in
order to upload it. You simply enter the download link and the transfer happens
on the server side, making it possible to leave downloads running in the
background even when your personal computer is switched off.

## Usage instructions

To start a download, select "Transfer file from URL" from the new file menu.

![This button can be found at the top of the file list.](img/instructions/menu.png)

A prompt will appear for you to paste the download link.

You may also choose a custom name to save the transferred file as.
If you leave this blank, a name will be generated based on the link.

![The prompt appears in the middle of the screen.](img/instructions/prompt.png)

Finally, click "Transfer".

The download will happen in a background job, which should start within five minutes
if your server is set up correctly. If you want transfers to start sooner, you will
need to configure your server so that `cron.php` is triggered more often.

## Development information

### Building the app

The app can be built using the provided Makefile by running `make`.
This requires the following programs to be installed:

* `make`
* `which`
* `tar`: for building the archive
* `npm`: for building the JavaScript bundle

### Publishing to the App Store

First get an account for the [App Store](http://apps.nextcloud.com/) then run
`make appstore`. The built archive will be located in `build/artifacts/appstore`
and can then be uploaded to GitHub releases, signed, and uploaded to the App Store.
