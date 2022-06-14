<p align=center>
<br>
<a href="http://makeapullrequest.com"><img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg"></a>
<img src="https://img.shields.io/badge/os-linux-brightgreen">
<img src="https://img.shields.io/badge/os-mac-brightgreen">
<img src="https://img.shields.io/badge/os-windows-brightgreen">
<img src="https://img.shields.io/badge/os-android-brightgreen">
<br>
<h1 align="center">
<a href="https://matrix.to/#/#ani-cli:matrix.org"><img src="https://element.io/blog/content/images/2020/07/Logomark---white-on-green.png" width="80"></a>
<a href="https://discord.gg/aqu7GpqVmR"><img src="https://pnggrid.com/wp-content/uploads/2021/05/Discord-Logo-Square-1024x1024.png" width="80"></a>
<a href="https://nightly.revolt.chat/invite/4FKHbs78"><img src="https://developers.revolt.chat/img/logo.png" width="80"></a>
<br>
<a href="https://github.com/port19x"><img src="https://img.shields.io/badge/lead-port19x-lightblue"></a>
<a href="https://github.com/CoolnsX"><img src="https://img.shields.io/badge/maintainer-CoolnsX-blue"></a>
<a href="https://github.com/RaynardGerraldo"><img src="https://img.shields.io/badge/maintainer-RayGL-blue"></a>
<br>
<a href="https://github.com/71zenith"><img src="https://img.shields.io/badge/maintainer-71zenith-blue"></a>
<a href="https://github.com/iamchokerman"><img src="https://img.shields.io/badge/maintainer-iamchokerman-blue"></a>
<a href="https://github.com/Derisis13"><img src="https://img.shields.io/badge/maintainer-Derisis13-blue"></a>

</p>

<h3 align="center">
A cli to browse and watch anime (alone AND with friends). This tool scrapes the site <a href="https://gogoplay5.com">gogoplay.</a>
</h3>
<h1 align="center">
	with auto-install scripts
</h1>
	
<h1 align="center">
	Showcase
</h1>

https://user-images.githubusercontent.com/44473782/160729779-41fe207c-b5aa-4fed-87db-313c83caf6bb.mp4

## Table of Contents

- [Fixing errors](#Fixing-errors)
- [Install](#Installation)
  - [Linux](#Linux)
  - [MacOs](#MacOS)
  - [Windows](#Windows)
  - [Android](#Android)
- [Uninstall](#Uninstall)
- [Dependencies](#Dependencies)
- [Homies](#Homies)
- [Contribution Guidelines](./CONTRIBUTING.md)
- [Disclaimer](./disclaimer.md)

## Fixing errors

If you encounter "Video url not found" or any breaking issue, then make sure you are on latest version by typing
`sudo ani-cli -U` to update on Linux, Mac and Android. On Windows, run gitbash as administrator then there type `ani-cli -U`.
If after this the issue persists then open an issue.
<br>
If you see sed warnings or your history entries have disappeared after updating, then update your history file with the history transition script. 
```sh
curl -s "https://raw.githubusercontent.com/dabigblob/ani-cli/master/hist_transition.sh" | sh
```
It doesn't work for all anime, but the ones it can't find will print out alongside their episode numbers. In the end clean up: `rm -rf ./ani-cli`

## Install

### Linux

Install dependencies [(See below)](#Dependencies)

```sh
curl -s "https://raw.githubusercontent.com/dabigblob/ani-cli/master/install" | sudo sh
```

*Note that mpv installed through flatpak is not compatible*

### MacOS

Install dependencies [(See below)](#Dependencies)

Install [HomeBrew](https://docs.brew.sh/Installation) if not installed.

```sh
curl -s "https://raw.githubusercontent.com/dabigblob/ani-cli/master/install" | sh
```

*To install (with Homebrew) the dependencies required on Mac OS, you can run:*

```sh
brew install curl grep aria2 iina openssl@1.1 ffmpeg git
``` 
*Why iina and not mpv? Drop-in replacement for mpv for MacOS. Integrates well with OSX UI. Excellent support for M1. Open Source.*  

### Windows

*Note that the installation instruction below must be done inside 
Powershell as **administrator**, not in Command Prompt*

```sh
curl -s "https://raw.githubusercontent.com/dabigblob/ani-cli/master/install" | sh
```

*Make sure git bash is installed [(Install)](https://git-scm.com/download/win)*

*Run ani-cli in Git Bash (Running it in cmd or powershell may or may not work)*

### Android

Install termux [(Guide)](https://termux.com/)

```sh
curl -s "https://raw.githubusercontent.com/dabigblob/ani-cli/master/android-install" | sh
```
Make sure to add the referrer in mpv by opening mpv [(playstore version)](https://play.google.com/store/apps/details?id=is.xyz.mpv), going into Settings -> Advanced -> Edit mpv.conf and adding:

```
referrer="https://gogoanime.fi/"
```

In the case mpv only plays audio, you can try running this command:
```sh
echo 'am start --user 0 -a android.intent.action.VIEW -d "$1" -n is.xyz.mpv/.MPVActivity' > $PREFIX/bin/mpv
```


## Uninstall

* Linux:  
```sh
curl -s "https://raw.githubusercontent.com/dabigblob/ani-cli/master/uninstall" | sudo sh
```
* Mac:  
```sh
curl -s "https://raw.githubusercontent.com/dabigblob/ani-cli/master/uninstall" | sh
```
* Windows:  
```sh
curl -s "https://raw.githubusercontent.com/dabigblob/ani-cli/master/uninstall" | sh
```
* Android:  
```sh
curl -s "https://raw.githubusercontent.com/dabigblob/ani-cli/master/android-uninstall" | sh
```

## Dependencies

- grep
- sed
- awk
- curl
- openssl
- mpv - Video Player
- iina - mpv replacement for MacOS
- aria2 - Download manager
- ffmpeg - m3u8 Downloader

## Homies 

* [animdl](https://github.com/justfoolingaround/animdl): Ridiculously efficient, fast and light-weight (supports most sources: animixplay, 9anime...) (Python)
* [anime-helper-shell](https://github.com/Atreyagaurav/anime-helper-shell): A python shell for searching, watching, and downloading anime (Python)
* [anipy-cli](https://github.com/sdaqo/anipy-cli): ani-cli rewritten in python (Python)
* [dra-cla](https://github.com/CoolnsX/dra-cla): ani-cli equivalent for korean dramas (Shell)
* [kaa.si-cli](https://github.com/Soviena/kaa.si-cli): Stream anime from kaa.si and sync with anilist (Python)
* [manga-cli](https://github.com/7USTIN/manga-cli): Read manga in the cli (Shell)
* [mov-cli](https://github.com/mov-cli/mov-cli): Watch movies/tv shows in the cli (work in progress) (Python/Shell)
* [saikou](https://github.com/saikou-app/saikou): Best android app for anime/manga with anilist integration (Kotlin)
