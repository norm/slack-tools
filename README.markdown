Miscellaneous Slack Tools
=========================

All written in python. You will need to have the `requests` library installed
(`sudo pip install requests`).


## add-github-webhook

If you don't like Slack having write access to Github in order to provide
notifications, use this script to easily add a webhook to your repo.

Usage:

    # set the env variables
    export GITHUB_TOKEN=somethingsomethingtoken
    export SLACK_WEBHOOK=https://hooks.slack.com/...

    # add one (or more) repos...
    python add-github-webhook norm/slack-tools norm/bash-composition

    # ...or add all repos owned by the GITHUB_TOKEN's owner
    python add-github-webhook -u


## pubsub-to-slack

Push notifications to Slack by using redis pubsub. For when you don't
want your app to push information into Slack directly.

Listens to the namespace `chatter*`.

Pre-requisites:

*   Have redis running.

*   Install python libraries:

        pip install redis requests

Run the script:

    export SLACK_WEBHOOK=https://hooks.slack.com/...
    python pubsub-to-slack

Then publish messages to redis:

    # send plain text
    redis-cli publish chatter 'hello world'

    # send a JSON payload
    redis-cli publish chatter '{"text":"Hello", "username":"via-redis"}'

...and they should appear in Slack!
