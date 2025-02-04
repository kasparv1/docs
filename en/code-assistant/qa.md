# FAQ about {{ ca-full-name }}

## General questions about {#common-questions}

### Do I need a billing account to work with {{ ca-name }}? {#billing-account}

You **do not need** a [billing account](../billing/concepts/billing-account.md).

### Can I use the plugin without internet access? {#using-plugin-without-internet}

No. To work with {{ ca-short-name }}, you will need continuous internet access.

### How to change the user authenticated in the {{ ca-name }} plugin {#change-user}

To authenticate to the {{ ca-name }} plugin as another {{ yandex-cloud }} user, [log out](./quickstart.md#logout) of the profile and then re-authenticate as described in step 3 of [{#T}](./quickstart.md#install-plugin).

## Working in Visual Studio Code {#vs-code-ide}

### Authentication error {#crypto-is-not-defined}

Error message:

```text
crypto is not defined
```

This is an error returned by the internal IDE library used for authentication in {{ yandex-cloud }}. To resolve this error, [upgrade](https://code.visualstudio.com/docs/setup/setup-overview#_update-cadence) your Visual Studio Code version.

{% cut "Below is an example of a Visual Studio Code build with plugin support" %}

```text
Version: 1.92.2 (system setup)
Commit: fee1edb8d6d72a0ddff41e5f71a671c23ed924b9
Date: 2024-08-14T17:29:30.058Z
Electron: 30.1.2
ElectronBuildId: 9870757
Chromium: 124.0.6367.243
Node.js: 20.14.0
V8: 12.4.254.20-electron.0
OS: Windows_NT x64 10.0.19045
```

{% endcut %}

See also [How to find out your IDE version](https://code.visualstudio.com/docs/setup/setup-overview#_how-do-i-know-which-version-im-running).

## Using JetBrains IDE {#jetbrains-ide}

### Which IDE versions are supported? {#ide-versions}

{{ ca-short-name }} supports JetBrains IDE versions 2024.1 and 2024.2.

### The plugin does not start, there is a 404 error, suggestions from {{ ca-short-name }} are not displayed {#plugin-doesnt-start}

Try restarting the IDE.

### Plugin is failing to install correctly {#plugin-installed-incorrectly}

{% include [plugin-ide-zip](../_includes/code-assistant/plugin-ide-zip.md) %}

### Error authenticating with the proxy {#auth-error-proxy}

Error message:

```text
Failed to authenticate with proxy
```

Check if the proxy server is enabled in the IDE. If it is, disable it and try authenticating again.

### How to get IDE logs {#get-logs-ide}

If you want to resolve issues with {{ ca-short-name }} through our [support]({{ link-console-support }}), make sure to prepare an IDE log file in advance:

1. In the IDE top menu, click **Help** and select **Show log in Explorer** (**Show Log in Finder** for macOS).
1. In the window that opens, copy the `idea.log` file and attach it to your support ticket.

### How to change the user authenticated in the {{ ca-name }} plugin {#change-user}

To authenticate in the {{ ca-name }} plugin as another {{ yandex-cloud }} user, [log out](./quickstart.md#logout) of your current account and re-authenticate as described in step 3 of [{#T}](./quickstart.md#install-plugin).
