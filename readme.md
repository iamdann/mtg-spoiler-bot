# MTG Spoiler Bot
This nifty little python application will scrape the newest spoilers from [Mythic Spoiler](http://mythicspoiler.com/) 
and caches the data into `.json` files. Card images will be saved too!

In the future this application will be able to be linked with ~~Whatsapp~~ Telegram and automatically send the newest spoilers inside your playgroups groups app!

## Getting Started
1. Get a API key [here](https://telegram.me/botfather).
2. Run:
```
docker run -e API_TOKEN=<YOUR-API-TOKEN> \
  -v $(pwd)/mtg-spoiler-bot-cache:/usr/src/app/app/cache \
  docker.pkg.github.com/dfsoeten/mtg-spoiler-bot/mtg-spoiler-bot:latest
```


## Options
The following options can be changed in `config.json`, these options will impact how the application is run.

| Option           | Values    | Description                                                             |
|------------------|-----------|-------------------------------------------------------------------------|
| domain           | [url]     | Domain of mythicspoiler.com, probably don't want to touch this          |
| new-sets-url     | [url]     | Newest sets on mythicspoiler, probably don't want to touch this either  |
| silent           | [boolean] | Turns all output on or of                                               |
| debug is-enabled | [boolean] | Turns on debug messages when an exception is thrown while scraping data |
| debug card-index | [int]     | Index of the to debug card in a set                                     |

## Testing
You can run the avaiable unit test by executing `docker build . -t mtg-spoiler-bot && docker run -v $(pwd):/usr/src/app mtg-spoiler-bot python3 test.py` in the root of this directory.

## Pretty Printing
It can pretty print magic cards, for what it's worth..

![pretty print example](pretty-print-example.jpeg)