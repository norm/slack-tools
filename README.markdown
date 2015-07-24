Miscellaneous Slack Tools
=========================

All written in python. You will need to have the `requests` library installed
(`sudo pip install requests`).


*   `add-github-webhook`

    If you don't like Slack having write access to Github in order to provide
    notifications, use this script to easily add a webhook to your repo.

    Usage:

        export GITHUB_TOKEN=somethingsomethingtoken
        export SLACK_WEBHOOK=https://hooks.slack.com/...
        python add-github-webhook norm/slack-tools
