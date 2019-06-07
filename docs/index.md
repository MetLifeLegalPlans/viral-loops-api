# Getting started

This module exports a single class that allows you to perform a series of API
interactions with Viral Loops. To get started, run

    from viral_loops_api import API

    api = API('secret_token_here')
    # ...

All methods in this library will return JSON (as parsed by `requests`),
and throw exceptions when there is a documented problem.

The [documentation](https://intercom.help/viral-loops) is rather sparse and
inconsistent on these endpoints and how they work, so this is not a complete
API library as of yet. If you find it is missing functionality for your
campaign, please submit a
[pull request or issue to the repository](https://github.com/bequest/viral-loops-api).

See the [API](API/index.md) page for documentation on the `API` class.

## Currently Supported Campaign Types

  * [The Altruistic Referral](https://intercom.help/viral-loops/the-altruistic-referral-template/the-altruistic-referral-your-web-app)
