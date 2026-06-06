
A composite workflow to begin a kosli trail at the start of a workflow.  
Requires a `.kosli.yml` template file and the following environment-variables:
- KOSLI_ORG
- KOSLI_FLOW
- KOSLI_TRAIL


Typical use is as follows:

```yml
name: Main

...

jobs:
  setup:
    runs-on: ubuntu-latest
    steps:
      ...

      - name: Begin Kosli Trail
        if: ${{ github.ref == 'refs/heads/main' }}
        uses: cyber-dojo/kosli-begin-trail@main
        with:
          cli_version: "${{ vars.KOSLI_CLI_VERSION }}"
          flow_description: "Diff files from two traffic-lights"
          flow_tags: |
            env=aws-beta
...
```

`flow_tags` is optional: one `key=value` per line, each applied to the Flow with
`kosli tag flow --set`. Tagging a build Flow with its target environment
(e.g. `env=aws-beta`) lets environment policies scope by `flow.tags.env`.
