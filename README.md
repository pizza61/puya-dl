# puya-dl

Short Python script for batch downloading PuyaSubs releases

Doesn't work with shows longer than 75 episodes because I'm too lazy to implement it properly. Should work tho

## Requirements
* Python... a new version I guess
* `xdg-open` (doesn't work on Windows for now)
* a BitTorrent client

## Install
Just clone this repository, do `pip install -r requirements.txt`. You can do this venv thing if you want.

## Usage
`python main.py "search query"`

```
usage: main.py [-h] [-q QUALITY] [-e EPISODES] [--dryrun] [--quiet] title [title ...]

puya.moe batch download tool

positional arguments:
  title                 Exact title

optional arguments:
  -h, --help            show this help message and exit
  -q QUALITY, --quality QUALITY
                        Quality (usually only 720p and 1080p is available)
  -e EPISODES, --episodes EPISODES
                        Specify episodes to download
  --dryrun              Dry run (only for development)
  --quiet, --noconfirm  Don't ask for confirmation
```

Default quality is 1080p. If you want to specify a different one, use -q, for example -q 720p.

### Episode filters
By default, puya-dl selects and downloads all episodes. When -e argument is passed, only selected episodes are downloaded. Just enter episode number to select an episode. You can also use ranges like `1-3`. Seperate filters with a single comma (,).

For example, `python main.py title -e 1-2,5-6,10` will select episodes 1, 2, 5, 6 and 10.