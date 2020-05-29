# Github action examples

Repo to store example github actions:
* Example 1: [Print hello world on every branch push](.github/workflows/ex1-hello-world.yaml)
* Example 2: [Run branch checks in order on every branch push](.github/workflows/ex2-branch-checks-seq.yaml)
* Example 3: [Run branch checks in parallel on every branch push](.github/workflows/ex3-branch-checks-multi-job.yaml)
* Example 4: [Example secret and env var used on every branch push](.github/workflows/ex4-secrets-and-env-vars.yaml)
* Example 5: [Manually trigger a workflow](.github/workflows/ex5-manual-trigger.yaml)


## How to manually trigger a pipeline
1. Create a [personal access token](https://help.github.com/en/github/authenticating-to-github/creating-a-personal-access-token-for-the-command-line) and give it access to everything in the "repo" section
1. Run the following curl command with your personal access token
```
curl -H "Accept: application/vnd.github.everest-preview+json" \
    -H "Authorization: token <personal_access_token>" \
    --request POST \
    --data '{"event_type": "trigger", "client_payload": { "text": "a title"}}' \
    https://api.github.com/repos/fransmith89/github-action-examples/dispatches
```
