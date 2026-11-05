# Get A Dad Joke - A GitHub Action

The [Get A Dad Joke Action](https://github.com/mickeygoussetorg/get-a-dad-joke) is a [composite run step custom action](https://docs.github.com/en/actions/creating-actions/creating-a-composite-run-steps-action) that tells you a dad joke. After all, who doesn't love dad jokes, right? 

This action makes use of the [icanhazdadjoke api](https://icanhazdadjoke.com/api) to randomly retrieve a joke as a text string.  The action will display the joke in the run log, and also output the joke as an output variable, that can be used by other steps.

# Example Workflow

```
jobs:
  tellmeajoke:
    runs-on: ubuntu-latest
    steps:
      # Get the joke
      - id: myjoke
        uses: mickeygoussetorg/get-a-dad-joke@v1
      # Use the joke output in another step
      - name: Output Dad Joke
        run: echo "${{ steps.myjoke.outputs.dad-joke }}"
```

# Output Variables

Variable Name | Description
------------- | -----------
**dad-joke** | Text string containing the dad joke

## Privacy

This Action contacts Chainguard's licensing server to verify authorization. Connection metadata (IP address, GitHub repository identifier, timestamp, and any metadata encoded in the auth token) is transmitted to Chainguard, Inc. even if authorization is denied in accordance with our [Privacy Notice](https://www.chainguard.dev/legal/privacy-notice)
