# Quick Start

To start with Toloka-Kit:

1. Get an OAuth token in your [profile](https://platform.toloka.ai/requester/profile/integration) or in the [Sandbox profile](https://platform.sandbox.toloka.ai/requester/profile/integration).

2. Install the Toloka-Kit package:

    ```shell
    $ pip install toloka-kit
    ```

3. Check access to the API with the following Python script. The script:
    * Imports the package.
    * Asks to enter the OAuth token.
    * Requests general information about your account.

    ```python
    import toloka.client as toloka

    target = 'SANDBOX'      # Send requests to the Sandbox
    # target = 'PRODUCTION' # Uncomment to send requests to the production version

    toloka_client = toloka.TolokaClient(input("Enter your token:"), target)
    print(toloka_client.get_requester())
    ```

## What's Next

* Complete one of the [tutorials](../guide/concepts/usecases.md) to get acquainted with Toloka web interface.
* Try [Toloka-Kit usage examples](https://github.com/Toloka/toloka-kit/tree/main/examples#toloka-kit-usage-examples).
* Read the package reference starting with [TolokaClient](reference/toloka.client.TolokaClient.md).
* Study [Toloka API documentation](../api/index.md).
* See other features in [Toloka requester's guide](../guide/concepts/overview.md).
* Contribute to [Toloka-Kit on GitHub](https://github.com/Toloka/toloka-kit): open pull requests, report bugs or share your [usage examples](https://github.com/Toloka/toloka-kit/tree/main/examples#need-more-examples).
