# Telegram bot for Firefly III (alfa version! Can contain bugs, please send your issues!)

This is a Telegram bot for [Firefly III](https://github.com/firefly-iii/firefly-iii).

## The idea

Using financial tools needs a high level of self-discipline. You need to write down all the transactions every day. Some people can't do that.

This bot reminds you to enter data about your finances and makes some boring operations easier for you.

That's the easy way for you and your family to manage finances.

### Requirements for Firefly III

Every person that will work with your Firefly III should have their own personal pocket account.

All transactions that bot will create will be attached to budgets, so you should have budgets created.

All transactions should be made in the same currency.

## Self-hosted installation and running

### Installation on Ubuntu

Download source code from github (https://github.com/may-cat/firefly-iii-telegram-bot)

Ensure python3 and pip3 are installed (or install them):

```
apt-get install -y python3 pip3
```

Install python requirements

```
pip3 install -r requirements.txt
```

### Creating telegram bot

Find user `@BotFather` in your telegram. Register new bot with `/newbot` command - you will get access token like this: `677617003:AAEJr4hOJzFGqDNI6CO8jpSJzqdhnNaEghI`.

Rename/Copy `config.json.example` to `config.json` and put your access token there.

### Running bot manually

You can run telegram bot manually:

```
python3 bot.py
```

**Notice!** In some countries (for example: in Russia) you can't reach telegram.me server due governement restrictions. Use other country's hosting or VPN, Luke!

### Running bot as daemon

TODO: write algorithm

## Usage

### Connecting

Find your bot (BotFather told you how to do this) and send `/start` command to him. Follow bot's instructions.

It will ask you for your Firefly server, for example: `https://demo.firefly-iii.org`.

Then it will ask you for your personal firefly access token. You should generate it in your Firefly (for example on https://demo.firefly-iii.org/profile page in `Personal Access Tokens` section).

Then the bot will ask you to choose account for your pocket. Every day at 8 pm bot will ask you how much money do you have in your pocket. If the amount has increased, the bot will ask you where you got that money. If the amount has decreased, the bot asks you which budget you spent money on.

### Making transactions

Just tell your bot how much you spent and some description. For example `12 tea`. Bot will ask you which budget this transaction should be attached to and will add the transaction.

### Scheduled balance actualization

Once a day, at 20:00 bot will ask you, "how much money do you have in your pocket?"

If the amount has increased over what is currently in Firefly III, the bot will ask you where you got that money.

If it has decreased, the bot will calculate the difference and help you to create transaction for the difference.

## Contribute

Fell free to send your merge requests.

## Contact

You can contact me by e-mail: i@tsupko.tech or by telegram @i_tsupko

## Other stuff

### License

MIT
