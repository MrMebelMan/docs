---
id: ory-update-project
title: ory update project
description: ory update project Update Ory Cloud Project Service Configuration
---

<!--
This file is auto-generated.

To improve this file please make your change against the appropriate "./cmd/*.go" file.
-->

## ory update project

Update Ory Cloud Project Service Configuration

### Synopsis

Use this command to replace your current Ory Cloud Project&#39;s service
configuration. All values will be overwritten. To update individual settings use
the `patch` command instead.

If the `--name` flag is not set, the project&#39;s name will not be changed.

The full configuration payload can be found at

    https://www.ory.sh/docs/reference/api#operation/updateProject

As an example an input could look like:

    {
      &#34;name&#34;: &#34;my updated name&#34;,
      &#34;identity&#34;: {
    	&#34;services&#34;: {
    	  &#34;config&#34;: {
    		&#34;courier&#34;: {
    		  &#34;smtp&#34;: {
    			&#34;from_name&#34;: &#34;...&#34;
    		  }
    		  // ...
    		}
    	  }
    	}
      }
    }

```
ory update project id [flags]
```

### Examples

```
$ ory update project ecaaa3cb-0730-4ee8-a6df-9553cdfeef89 \
	--name \"my updated name\" \
	--file /path/to/config.json \
	--file /path/to/config.yml \
	--file https://example.org/config.yaml \
	--file base64://<json>

ID		ecaaa3cb-0730-4ee8-a6df-9553cdfeef89
SLUG	good-wright-t7kzy3vugf
STATE	running
NAME	Example Project

$ ory update project ecaaa3cb-0730-4ee8-a6df-9553cdfeef89 \
	--name \"my updated name\" \
	--file /path/to/config.json \
	--format json-pretty

{
  "name": "my updated name",
  "identity": {
	"services": {
	  "config": {
		"courier": {
		  "smtp": {
			"from_name": "..."
		  }
		  // ...
		}
	  }
	}
  }
}
```

### Options

```
  -f, --file strings    Configuration file(s) (file://config.json, https://example.org/config.yaml, ...) to update the project
      --format string   Set the output format. One of table, json, yaml, and json-pretty. (default "default")
  -h, --help            help for project
  -n, --name string     The name of the project, required when quiet mode is used
  -q, --quiet           Be quiet with output printing.
  -y, --yes             Confirm all dialogues with yes.
```

### Options inherited from parent commands

```
  -c, --config string   Path to the Ory Cloud configuration file.
```

### SEE ALSO

- [ory update](ory-update) - Update resources
