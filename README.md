# Spotify Now Listening NUXT App

## What is this?

```bash NUXT Spotify now listening app. App is set to only allow user_id set through ENV to login. 
 Grabs currently playing Spotify song/podcast and displays along with current progress through track 
 Shows end user when you pause track & last track played when you finish your spotify session
       
 TODO: Spotify play history does not show podcast history so if the last thing you 
       listen to is a podcast it will display your last song when you quit spotify
       
 TODO: Display a list of last tracks played
       
 TODO: Allow people to join spotify listening party? Currently mobile only, need 
       to investigate if Spotify API allows for this
```

## Build Setup

```bash
# install dependencies
$ npm install

# serve with hot reload at localhost:3000
$ npm run dev

# build for production and launch server
$ npm run build
$ npm run start

# generate static project
$ npm run generate

# Environment Variable setup
    Setup Variables for:
    - REDIS_URL
    - SPOTIFY_USER_ID
    - CLIENT_URL
    - SPOTIFY_CLIENT_ID
    - SPOTIFY_CLIENT_SECRET

# Setup Spotify App
    Setup your spotify app with correct call back urls
    App will only respond to spotify user id set and from urls set in client_url


```

For detailed explanation on how things work, check out [Nuxt.js docs](https://nuxtjs.org).
# nowlistening
