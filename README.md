# Black Swan Causal Labs plugins

A plugin marketplace for Claude Code and Cowork. Each plugin installs one of the
[Black Swan Causal Labs](https://blackswancausallabs.com) MCP servers for real-world
evidence, pharmacoepidemiology and public health, with no configuration files to edit.

## Install

In Claude Code or Cowork, add the marketplace once:

```
/plugin marketplace add Black-Swan-Causal-Labs/bscl-plugins
```

Then open `/plugin` and pick the tools you want, or install one directly:

```
/plugin install nhanes@black-swan-causal-labs
```

The local servers run with [uv](https://docs.astral.sh/uv/). Install it first if you don't have it.

## Plugins

| Plugin | What it does | Server | License |
|---|---|---|---|
| `nhanes` | Analyze CDC NHANES the way NCHS does: correct survey weights, pooled cycles, design-based CIs and NCHS reliability flags | [nhanes-mcp](https://github.com/Black-Swan-Causal-Labs/nhanes-mcp) 0.5.1, local | MIT |
| `target-checklist` | Score how completely a target trial emulation reports what the TARGET guideline requires | [target-mcp](https://github.com/Black-Swan-Causal-Labs/target-mcp) 0.2.0, local | Apache-2.0 |
| `robins-i` | ROBINS-I V2 risk-of-bias assessment for one result of a non-randomized cohort study | [robins-i-mcp](https://github.com/Black-Swan-Causal-Labs/robins-i-mcp) 0.1.0, local | Apache-2.0 |
| `openfda` | Resolve FDA application numbers and product names to regulatory metadata (CDER, CBER, CDRH) | [openfda-mcp](https://github.com/Black-Swan-Causal-Labs/openfda-mcp) 0.1.0, local | MIT |
| `dag-studio` | Causal DAG analysis: backdoor paths, adjustment sets, bias simulation, validated against dagitty | [dagstudio-mcp](https://github.com/Black-Swan-Causal-Labs/dagstudio-mcp), hosted | Apache-2.0 |

`dag-studio` connects to a hosted server and asks for a trial token when you enable it.
Request one at jdiazdecaro@blackswancausallabs.com.

Each plugin runs the server exactly as published on PyPI and in the
[official MCP Registry](https://registry.modelcontextprotocol.io) (`com.blackswancausallabs/*`),
pinned to the version listed above. The plugins add no skills or instructions of their own,
so the tools behave as they did in each server's validation.

## Browser tools

[DAG Studio](https://blackswancausallabs.com/dag-studio.html) and the
[Study Design Diagram Studio](https://blackswancausallabs.com/study-design-studio.html) also expose
WebMCP tools to browser-based agents directly from the web page. Those run in the browser, not
through a plugin.

## License

The marketplace files in this repository are MIT licensed. Each server keeps its own license,
listed above.

© 2026 Black Swan Causal Labs
