# riiidbot

Hubot for `riiid`.

## Run

    $ docker run -it \
      -p <HOST_PORT>:<PORT_FOR_HUBOT> \
      -e HUBOT_SLACK_TOKEN=<YOUR_SLACK_TOKEN> \
      -e FIREBASE_URL=<FIREBASE_URL> \
      -e FIREBASE_SECRET=<FIREBASE_SECRET> \
      -e EXPRESS_PORT=<PORT_FOR_HUBOT> \
      riiid/riiidbot

Override `entrypoint` to test it locally.

    $ docker run -it -p 9000:9000 --entrypoint=/src/hubot/bin/hubot riiid/riiidbot

> passing `--rm` will always give you fresh container. see `$ docker run --help`.

## Running Locally

If you don't like `docker` (:feelsgood:),

    $ git clone riiid/riiidbot
    $ cd riiidbot
    $ npm run start-dev
    Hubot> hubot help

## Scripting

See `scripts/example.coffee`, or visit [Scripting Guide](https://github.com/github/hubot/blob/master/docs/scripting.md).

## Deploy

### Build Image

To build docker image for `riiidbot`,

    $ docker build -t riiid/riiidbot .

### Test Image on local

    $ docker run -it --rm riiid/riiidbot run start-dev

or If you with test with full env variables,

    $ docker run -it --rm \
      -p <HOST_PORT>:<PORT_FOR_HUBOT> \
      -e HUBOT_SLACK_TOKEN=<YOUR_SLACK_TOKEN> \
      -e FIREBASE_URL=<FIREBASE_URL> \
      -e FIREBASE_SECRET=<FIREBASE_SECRET> \
      -e EXPRESS_PORT=<PORT_FOR_HUBOT> \
      riiid/riiidbot
