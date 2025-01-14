## Profiling with Blackfire.io

DDEV-Local has built-in [blackfire.io](https://blackfire.io) integration.

### Basic Blackfire Usage (Using Browser Plugin)

1. Create an account on [blackfire.io](https://blackfire.io)
2. Install the Chrome or Firefox [browser plugin](https://blackfire.io/docs/profiling-cookbooks/profiling-http-via-browser).
3. Get the Server ID, Server Token, Client ID, and Client Token from your Account->Credentials or environment on blackfire.io.
4. Configure ddev with the credentials, `ddev config global --web-environment="BLACKFIRE_SERVER_ID=<id>,BLACKFIRE_SERVER_TOKEN=<token>,BLACKFIRE_CLIENT_ID=<id>,BLACKFIRE_CLIENT_TOKEN=<token>"`. It's easiest to do this globally, but you can do the same thing at the project-level using `ddev config --web-environment`. (Note that you can also just manually edit the relevant config file.)
5. `ddev start`
6. `ddev blackfire on` to enable, `ddev blackfire off` to disable, `ddev blackfire status` to see status.
7. With Blackfire enabled, you can use the [browser extension](https://blackfire.io/docs/profiling-cookbooks/profiling-http-via-browser).

### Profiling with the Blackfire CLI

The Blackfire CLI is built into the web container.

1. `ddev config global --web-environment="BLACKFIRE_SERVER_ID=<id>,BLACKFIRE_SERVER_TOKEN=<token>,BLACKFIRE_CLIENT_ID=<id>,BLACKFIRE_CLIENT_TOKEN=<token>"`
2. `ddev start`
3. Examples of using the Blackfire CLI:

   * `ddev exec blackfire curl https://<yoursite>.ddev.site`
   * `ddev exec blackfire drush st`
   * `ddev exec blackfire curl https://<yoursite>.ddev.site`
   * `ddev ssh` and then use the Blackfire CLI as described in [Profiling HTTP Requests with the CLI](https://blackfire.io/docs/profiling-cookbooks/profiling-http-via-cli).
