# Scrape site and push to Netlify

## The Basic version.

Website --> Github Action --> Netlify.

The basic steps are:

- Scrape target with `wget`
- Remove query strings
- Push to Netlify

## Setup

The action needs two secrets setup:

- `NETLIFY_AUTH_TOKEN`
- `NETLIFY_SITE_ID`

You can get both from netlify.

## Run

The action will run on push to master branch. If you add `-test` in the commit message, the action will disable.

## Heroku.

This was initially created to scrape a Ghost.org blog for IORoot hosted on Heroku.

Why Heroku? Well, it's free. And you can link a DB and CDN to the free instance. So Ghost will work on it.

Once I've made any changes on Heroku, I'd head over to github and run this action.

## Github.

This action will scrape the heroku dyno and generate a static version of the website. 

It then pushes the result over to Netlify.

## Netlify.

I use netlify because I wanted to see if I could link all of these services together, and it also seems to be faster and
more capable than github pages.

## New targets. 

The github action has a single variable called `scrapetarget` that you can point anywhere.