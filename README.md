
A "partner" composite workflow to begin a kosli trail at the start of a workflow.
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
...
```
