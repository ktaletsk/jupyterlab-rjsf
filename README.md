# jupyterlab-rjsf

> [React JSON Schema Form][rjsf] for [JupyterLab][lab]

[rjsf]: https://github.com/rjsf-team/react-jsonschema-form
[lab]: https://github.com/jupyterlab/jupyterlab

This is a hard fork of https://github.com/deathbeds/jupyterlab-starters/tree/master/packages/jupyterlab-rjsf (forked from the version 1.0.2). All the credit to original work belongs to https://github.com/bollwyvl and https://github.com/nrbgt.

There are some issues with formData and validation that I would like to fix in this fork. Hopefully, the fixes can make it back to the upstream at some point. 


## Description

This project adds the ability to use React JSON Schema Form in JupyterLab widgets 
and JupyterLab extensions, and other labextensions. 
To use it, it should specified as a dependency in package.json so it will
be installed for you, if needed.

## Usage

Use the `SchemaForm`, a `@lumino/widget` that you can put inside of any other
widget (such as the `DockPanel`). It's `model` exposes the `schema`, `formData`,
other `rjsf` specifics, and can be connected to with `model.stateChanged`.

```ts
const schema: any = {
  title: "My title",
  description: "My description",
  type: "object",
  properties: {
    name: {
      type: "string"
    },
    age: {
      type: "number"
    }
  },
  required: ["name"]
};

const formData: any = {
  name: "Jovyan",
  age: 99
};

SchemaForm(schema, { formData: formData })
```

## Development

To build package, run

```
npm install --force
npx tsc
```