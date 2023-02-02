# redpesk-cli installation and initialization

This action install the `redpesk-cli` tool (or `rp-cli`), and initialize the runner environment in order to be able to use the `rp-cli` commands in the current job.

Click on the following links for more information about **[redpesk](https://docs.redpesk.bzh/)** and **[redpesk-cli](https://docs.redpesk.bzh/docs/en/master/getting_started/rp_cli_quickstart/0_introduction.html)**.

## Usage

### Required Inputs

| Input           | Description                                                                                                        |
| --------------- | ------------------------------------------------------------------------------------------------------------------ |
| `factory-url`   | URL of the used redpesk factory                                                                                    |
| `factory-token` | Access token needed to connect to the redpesk factory. It is strongly recommended to use "secrets" for this input. |

### Optional Inputs

| Input          | Description                                                | Default value                                                                                        |
| -------------- | ---------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| `install-url`  | URL where the script that install rp-cli can be downloaded | "https://raw.githubusercontent.com/redpesk-devtools/redpesk-sdk-tools/master/install-redpesk-sdk.sh" |
| `factory-name` | Name to give to the redpesk factory used                   | "my-redpesk-factory"                                                                                 |

### Example

To use this action, you can add the following entry in your Github workflow.

```yaml
env:
    RP_REMOTE_FACTORY_URL: 'https://community-app.redpesk.bzh'
    RP_REMOTE_FACTORY_TOKEN: ${{ secrets.RP_REMOTE_FACTORY_TOKEN }}

uses: redpesk-infra/github-setup-rp-cli-action@v1
with:
    factory-url: "$RP_REMOTE_FACTORY_URL"
    factory-token: "$RP_REMOTE_FACTORY_TOKEN"
```