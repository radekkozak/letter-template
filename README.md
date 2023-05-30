<br>
<p align="center">
<picture>
    <source media="(max-width: 640px)" srcset="https://github.com/radekkozak/letter/blob/main/assets/letter-header-slogan.svg" width="90%">
    <img src="https://github.com/radekkozak/letter/blob/main/assets/letter-header-slogan.svg" alt="Letter header" width="50%">
</picture>
</p>
<p align="center">
<picture>
    <source media="(max-width: 640px)" srcset="https://github.com/radekkozak/letter/blob/main/assets/letter-cat.gif" width="70%">
    <img src="https://github.com/radekkozak/letter/blob/main/assets/letter-cat.gif" alt="Letter cat" width="40%">
</picture>
</p>
<br><br>

## A minimalistic *cat-like* app that delivers a digest of your RSS feeds as templated newsletter.

<br>

**How it works? Simple!** Every day at 11 am (or at time of your choosing) *letter*  runs on 
the server via `cron` and fetches all your precious RSS feeds to check whether 
there is anything new from yesterday. After some mapping and rendering newsletter digest is created
and sent via e-mail. All in a *catsy* manner. And right into your inbox.

<br>

## Use this Letter Template 

to have your own daily readings delivered with [Letter]("https://github.com/radekkozak/letter)

### Quick Howto

1. Click **Use this template** button above and create your repo from this template


2. [Create secret variables](https://docs.github.com/en/actions/security-guides/encrypted-secrets) in your newly created repository with keys as seen below in [Required environment variables](required-environment-variables)


3. Fill up your favorite feeds either in plain `feeds.txt` file or via `feeds.opml` (OPML file can be exported from most rss services)
 
 
4. _(optionally)_ Change cron time settings in `letter.yml` to your liking. By default *letter* will deliver your readings everyday at 11am UTC. You can also check if everything works as you want by triggering Github workflow via provided `manual-trigger.yml`.
   
### Set your environment variables 

Below _Github Secrets_ are required for running Letter workflows

```bash
LETTER_FEEDS=plain # plain or opml (default is plain)

MAIL_TO=dailyread@example.com
MAIL_FROM=Letter <letter@example.com>

SMTP_HOST=smtp.gmail.com # or whatever mail service you use
SMTP_PORT=465 # or some other
SMTP_SECURE=true # in most cases set this to true if you are connecting to port 465

SMTP_USERNAME=username
SMTP_PASSWORD=password
```

<br>

## Email newsletter template

Letter uses [Handlebars](https://handlebarsjs.com) with html extension as default templating engine. Email is generated from `letter` template inside `emails` directory. You can make it your own as you please. Templating
assumes the structure of `html`, `subject` and `text` html files. Here's how *letter* template looks by default:<br><br>

<div align="center">
    <img src="https://github.com/radekkozak/letter/blob/main/assets/letter-example.jpg" width="830" alt="Default Letter newsletter template"/>
</div>

## Notes

### OPML file structure can be flat or nested

Sometimes certain services like i.e Feedly, export OPML feeds in a nested manner. Letter supports both flat 
and categorized notations. Even in the same file. Please see [feeds.opml.example](https://github.com/letter/rss/feeds.xml.example)

### Gmail considerations

If you use Gmail for sending out the newsletter and your account has Two-Factor Authentication (2FA) enabled you 
need to generate app-specific password which then can be used in place of your regular `EMAIL_PASS` variable in `.env` file.

## License

Meow-what ? Cats don't need no stinking licenses. Just be good and state the source of the original cat [wink]. 

## Cats and credits

**I have tried hard to find original authors of cat gif and cat avatar used in the template and header**. Long time ago i found those chucklesome pics sitting in my old computer folder one day and they sparked me to make this simple *why-not* weekend project. Funny enough i found myself using it for this day (What can i say - i just love my RSS readings delivered as email - i'm weird that way) Aaanywho - **if you are the original author of any of these lovely cats, please let me know** so i could give credit where credit is due.     
