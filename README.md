# pour.coffee
a pour over guide ☕️

## Development

```sh
deno install   # or --frozen, as CI does
deno task dev
deno task build
```

Dependencies and tasks live in `deno.json`. The stub `package.json` carries no
dependencies — it exists so Deno applies Node-style resolution to the prerender
entry Astro emits into `dist/`, which imports a few of Astro's own transitive
deps by bare specifier. Delete it and `deno task build` fails with
`Import "devalue" not a dependency and not in import map`.
