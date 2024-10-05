# SDL
<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#supported-sites">Supported Sites</a></li>
        <li><a href="#supported-extractors">Supported extractors</a></li>
      </ul>
    </li>
    <li><a href="#installation">Installation</a></li>
    <li><a href="#usage">Usage</a></li>
    <ul>
       <li><a href="#downloading-a-single-episode">Downloading a single episode</a></li>
       <li><a href="#downloading-an-entire-season">Downloading an entire season</a></li>
       <li><a href="#downloading-multiple-episodes">Downloading multiple episodes</a></li>
       <li><a href="#downloading-multiple-seasons">Downloading multiple seasons</a></li>
       <li><a href="#downloading-all-seasons">Downloading all seasons</a></li>
       <li><a href="#downloading-in-other-languages">Downloading in other languages</a></li>
       <li><a href="#full-examples">Full Examples</a></li>
       <li><a href="#downloading-with-extractor-directly">Downloading with extractor directly</a></li>
    </ul>
    <li><a href="#help-output">Help output</a></li>
    <li><a href="#notes">Notes</a></li>
    <li><a href="#build-from-source">Build from source</a></li>
    <li><a href="#thanks">Thanks</a></li>
    <li><a href="#legal-notice">Legal Notice</a></li>
  </ol>
</details>

**Warning: This project is generally not well tested.**

> [!NOTE]
> This is a fork of https://github.com/Funami580/sdl.
> I’m developing this independently from the original repo.
> All credit for creating this command-line utility goes to [Funami580](https://github.com/Funami580).

<!-- ABOUT THE PROJECT -->
### About the Project
Download various anime and series from Aniwave.se, Aniworld.to, and S.to.

This project is [licensed](https://github.com/Jettcodey/sdl/blob/Master/LICENSE.txt) under the terms of the [MIT license](https://opensource.org/license/mit).

<!-- Supported sites -->
## Supported sites
### English
* [Aniwave.se](https://aniwave.se) <-- Most likely Not Working right now.

### German
* [AniWorld.to](https://aniworld.to)
* [S.to](https://s.to)
<p align="right"><a href="#sdl">Back to top</a></p>

<!-- Supported extractors -->
## Supported extractors
* Filemoon
* Streamtape
* Vidoza
* Voe
<p align="right"><a href="#sdl">Back to top</a></p>

<!-- Installation -->
## Installation
#### Windows Only
* To install SDL, download the latest setup or `sdl-x.x.x-windows-x64.zip` file from [Releases](https://github.com/Jettcodey/sdl/releases/latest) (the setup is recommended).
> [!NOTE]  
> The setup will place `sdl.exe` at `C:\Program Files(x86)\SDL\` Folder and add `sdl` to your System Environment `PATH`.
* After the installation is finished, simply open a terminal/cmd window. To begin downloading, take a look at these <a href="#full-examples">examples</a>.

#### Linux and MacOS
* Download the Latest `sdl-x.x.x-(linux|macos)-(ARCH).gz` file for your System from [Releases](https://github.com/Jettcodey/sdl/releases/latest).
* After Downloading, Extract and Save the Content in a Safe Location where you want to save your Downloads and start a Terminal window where you put the contents.To begin downloading, take a look at these <a href="#full-examples">examples</a>.
<!-- Usage -->
## Usage
<!-- Downloading a single episode -->
### Downloading a single episode
By URL:
```bash
sdl 'https://aniwave.se/anime-watch/yuruyuri/ep-11'
```
By specifying it explicitly
```bash
sdl -s 2 -e 5 'https://aniworld.to/anime/stream/rent-a-girlfriend'
```
(Aniwave ONLY):
```bash
sdl -e 11 'https://aniwave.se/anime-watch/yuruyuri'
```
<p align="right"><a href="#sdl">Back to top</a></p>

<!-- Downloading an entire season -->
### Downloading an entire season
By URL:
```bash
sdl 'https://aniwave.se/anime-watch/yuruyuri'
sdl 'https://aniworld.to/anime/stream/yuruyuri-happy-go-lily/staffel-2'
sdl 'https://aniworld.to/anime/stream/yuruyuri-happy-go-lily/filme'
```
By specifying it explicitly:
```bash
sdl -s 2 'https://aniworld.to/anime/stream/yuruyuri-happy-go-lily'
sdl -s 0 'https://aniworld.to/anime/stream/yuruyuri-happy-go-lily'
```
<p align="right"><a href="#sdl">Back to top</a></p>

<!-- Downloading multiple episodes -->
### Downloading multiple episodes
```bash
sdl -e 1,2-6,9 'https://aniwave.se/anime-watch/yuruyuri'
```
<p align="right"><a href="#sdl">Back to top</a></p>

<!-- Downloading multiple seasons -->
### Downloading multiple seasons
```bash
sdl -s 1-2,4 'https://aniworld.to/anime/stream/yuruyuri-happy-go-lily'
```
<p align="right"><a href="#sdl">Back to top</a></p>

<!-- Downloading all seasons -->
### Downloading all seasons
```bash
sdl 'https://aniworld.to/anime/stream/yuruyuri-happy-go-lily'
```
<p align="right"><a href="#sdl">Back to top</a></p>

<!-- Downloading in other languages -->
### Downloading in other languages
```bash
sdl -t gersub 'https://s.to/serie/stream/higurashi-no-naku-koro-ni/staffel-1/episode-1'
sdl -t engdub 'https://aniwave.se/anime-watch/detective-conan/ep-1'
```
Either dub or sub:
```bash
sdl -t ger 'https://s.to/serie/stream/higurashi-no-naku-koro-ni/staffel-1/episode-1'
sdl -t german 'https://s.to/serie/stream/higurashi-no-naku-koro-ni/staffel-1/episode-1'
```
<p align="right"><a href="#sdl">Back to top</a></p>

<!-- Full Examples -->
### Full Examples
Download Season 2 Ep 3 in German Audio(GerDub):
```bash
sdl -s 2 -e 3 -t gerdub 'https://aniworld.to/anime/stream/rent-a-girlfriend'
```
Download Full Season 3 in Japanese Audio&English Sub(EngSub):
```bash
sdl -s 3 -t engsub 'https://aniworld.to/anime/stream/rent-a-girlfriend'
```

If an episode has multiple languages, the general language preference is as follows:
* English Anime Website: EngSub > EngDub
* German Anime Website: GerDub > GerSub > EngSub > EngDub
* German non-Anime Website: GerDub > GerSub > EngDub > EngSub
<p align="right"><a href="#sdl">Back to top</a></p>

<!-- Downloading with extractor directly -->
### Downloading with extractor directly
```bash
sdl -u 'https://streamtape.com/e/DXYPVBeKrpCkMwD'
sdl -u=voe 'https://prefulfilloverdoor.com/e/8cu8qkojpsx9'
```
<p align="right"><a href="#sdl">Back to top</a></p>

<!-- Help Output -->
### Help output
```
Usage: sdl [OPTIONS] <URL>

Arguments:
  <URL>  Download URL

Options:
      --type <VIDEO_TYPE>
          Only download specific video type [possible values: raw, dub, sub]
      --lang <LANGUAGE>
          Only download specific language [possible values: english, german]
  -t <TYPE_LANGUAGE>
          Shorthand for language and video type
  -e, --episodes <RANGES>
          Only download specific episodes
  -s, --seasons <RANGES>
          Only download specific seasons
  -u, --extractor[=<NAME>]
          Use underlying extractors directly
  -N, --concurrent-downloads <INF|NUMBER>
          Concurrent downloads [default: 5]
  -r, --retries <INF|NUMBER>
          Number of download retries [default: 5]
      --ddos-wait-episodes <NEVER|NUMBER>
          Amount of requests before waiting [default: 4]
      --ddos-wait-ms <MILLISECONDS>
          The duration in milliseconds to wait [default: 60000]
      --mpv
          Play in mpv
  -d, --debug
          Enable debug mode
  -h, --help
          Print help
  -V, --version
          Print version
```
<p align="right"><a href="#sdl">Back to top</a></p>

<!-- Notes -->
## Notes
If FFmpeg and ChromeDriver are not found in the `PATH`, they will be downloaded automatically.

Also, I don't plan to add new sites or extractors, but you're welcome to create a Pull Request if you want to add one.

By the way, it's also possible to use `sdl` as a library.
<p align="right"><a href="#sdl">Back to top</a></p>

<!-- Build from Source -->
## Build from source
Currently, Rust 1.75 or newer is required.
```
cargo build --release
```
The resulting executable is found at `target/release/sdl`.
<p align="right"><a href="#sdl">Back to top</a></p>

<!-- Report a bug -->
## Report a bug/Request a Feature
See the [open issues](https://github.com/Jettcodey/sdl/issues) for a full list of proposed features (and known issues).
##### Always report bugs and issues in English! If you report in any other language, your issue will be ignored and closed.
<p align="right"><a href="#sdl">Back to top</a></p>

## Thanks
* [aniworld_scraper](https://github.com/wolfswolke/aniworld_scraper) for the inspiration and showing how it could be done.
* [Funami580](https://github.com/Funami580) for Developing this Command line utility.
<p align="right"><a href="#sdl">Back to top</a></p>

## Legal Notice
This Project/Library is for educational purposes only. Downloading or accessing copyrighted content without permission may be illegal in your country. I am not responsible for any misuse or legal consequences. **Use at your own risk**.
<p align="right"><a href="#sdl">Back to top</a></p>
