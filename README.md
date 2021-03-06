## CLI for the Audit Log using GHEC

This CLI made in node helps on querying the audit log. It can query the full
audit providing all the data the API can serve, or, given a cursor, it can 
provide the newest entries from that specific moment.

You can build an sh script on top of this one to store the data or query it.

### CLI arguments
This script can take the following arguments:
```
> node ghec-audit-log-cli.js "--help"

Usage: audit-log-ghec-cli [options]

Options:
  -v, --version            Output the current version
  -t, --token <string>     the token to access the API (mandatory)
  -o, --org <string>       the organization we want to extract the audit log from
  -cfg, --config <string>  location for the config yaml file. Default ".ghec-audit-log" (default: "./.ghec-audit-log")
  -p, --pretty             prints the json data in a readable format (default: false)
  -l, --limit              a maximum limit on the number of items retrieved
  -c, --cursor <string>    if provided, this cursor will be used to query the newest entries from the cursor provided. If not present,
                the result will contain all the audit log from the org
  -h, --help               display help for command

```

Optionally, you can create a file called `.ghec-audit-log` that supports
the token and organization, and omit the parameters while running the script.

```yaml
org: org-name
token: xxxxxxxxxxxxxxxx
```

### Running the CLI

Execute the command using node or npm.

#### npm
```shell script
$ npm run start -- --pretty
```

### node
```shell script
$ node audit-log-ghec-cli --pretty
```

### Installing as CLI

Optionally you can install the script as a CLI and run it from the command line. To install it run:
```shell script
$ git clone https://github.com/droidpl/ghec-audit-log-cli
$ cd ghec-audit-log-cli
$ npm link
```

Then you can execute the script as a CLI using:
```shell script
$ ghec-audit-log-cli -v
```
