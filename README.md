# gift-os-types

The gift-os-types repository holds column types used in populating the Table Schema page of the Gift-publisher. 

There are two required files, and if not found in this repo, Table Schema will be loaded from the default [os-types](https://github.com/datopian/gift-publisher/blob/main/src/db/os-types.json) and [os-type-descriptions](https://github.com/datopian/gift-publisher/blob/main/src/db/os-type-descriptions.json) that ships with Gift-publisher.

### os-types.json
os-types is a json object, and must be in the following format:

```json
{
  "name of type 1" : {
      "dataType": "string",
      "dimensionType": "",
      "parent": "",
  },
  "name of type 2" : {
     "dataType": "int",
      "dimensionType": "",
      "parent": "",
  }

}
```

For example:

```json
{
    "activity:generic:contract:code": {
        "dataType": "string",
        "dimensionType": "activity",
        "parent": "activity:generic:subproject:code",
        "uniqueIdentifier": true
    },
    "activity:generic:contract:label": {
        "dataType": "string",
        "dimensionType": "activity",
        "labelfor": "activity:generic:contract:code"
    }
}
```

## os-type-descriptions.json
os-type-descriptions is a json object, and must be in the following format:

```json
{
  "name of type 1:": {
    "displayName": "Type 1",
    "description": "The activity that's being funded (e.g. project, program, contract etc.)",
  },
  "name of type 2": {
    "displayName": "Type 2",
    "description": "Activity codes or labels that do not adhere to a specific standard"
  }

}
```

For example:
```json
{
  "activity:": {
    "displayName": "Activity",
    "description": "The activity that's being funded (e.g. project, program, contract etc.)",
    "group": "300-Activity"
  },
  "activity:generic:": {
    "displayName": "Non-standard Activity",
    "description": "Activity codes or labels that do not adhere to a specific standard"
  }
}
```
