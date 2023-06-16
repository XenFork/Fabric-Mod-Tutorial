# Add the necessary resource files

## second step

### fabric.mod.json
- schemaVersion data version
- id modid
- version
- name Mod Alias
- description
- authors 
- contact Related Links for Projects
- license protocol
- icon
- environment generally do not need to be modified
- entrypoints entry point, more on that later
- mixins The json file definition for mixin injection [不是必须的]
- depends 
- custom Classic interface injection mixin loom:injected_interfaces
```json
{
  "schemaVersion": 1,
  "id": "tutorials",
  "version": "${version}",
  "name": "tutorials",
  "description": "",
  "authors": [],
  "contact": {
    "repo": "https://github.com/xenfork/tutorials"
  },
  "license": "MIT",
  "icon": "assets/tutorials/icon.png",
  "environment": "*",
  "entrypoints": {
    "server": [
    ],
    "client": [
    ]
  },
  "mixins": [
    "tutorials.mixins.json"
  ],
  "depends": {
    "fabricloader": ">=${loader_version}",
    "fabric": "*",
    "fabric-api": "*",
    "minecraft": "${minecraft_version}"
  },
  "custom": {
    "loom:injected_interfaces": {
    }
  }
}
```

### tutorials.mixins.json
- It is not required, you can leave this file when you don't need mixin code
- required Is it mandatory to load
- minVersion Minimum mixin version
- package The package where the mixin is located
- compatibilityLevel Java compiled version, here is java17
- injectors
    - defaultRequire Mixed sets required by default
- mixins Allows support for running mixins on both client and server
- client Only run mixins on the client side
- server Only run mixins on the server side
```json
{
  "required": true,
  "minVersion": "0.8",
  "package": "union.xenfork.tutorials.mixin",
  "compatibilityLevel": "JAVA_17",
  "injectors": {
    "defaultRequire": 1
  },
  "mixins": [
  ],
  "server": [
  ],
  "client": [
  ]
}
```

## such as
- [fabric.mod.json](../tutorials/src/main/resources/fabric.mod.json)
- [tutorials.mixins.json](../tutorials/src/main/resources/tutorials.mixins.json)
  ![icon](../tutorials/src/main/resources/assets/tutorials/icon.png)