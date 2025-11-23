
A "partner" composite workflow to begin a kosli trail at the start of a workflow.

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
        uses: cyber-dojo/begin-kosli-trail@main
        with:
          flow_description: ""
...
```
