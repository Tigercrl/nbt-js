# NBT-Parser

Minecraft NBT (NamedBinary Tags) parser for Node.js

## Supports
* Java & Bedrock(Not tested) edition
* Parsing NBT / SNBT to JSON
* Dumping JSON to NBT

## Installation
```
npm install nbt-parser
```

## Usage

```typescript
// Importing
const NBT = require('nbt-parser');
// or
import NBT from "nbt-parser";

// Parse NBT
const nbt = NBT.parseJSON({ key: "value" });
const nbt = NBT.parseNBT(new Uint8Array([]), 'java');
const nbt = NBT.parseSNBT("{key:value}");

// Dumping NBT
nbt.toJSON();
nbt.toNBT('gzip', 'java');
nbt.toSNBT('formatted');

// Getting tags or payloads
const tag = nbt.getRootTag();
// tag.getTagName(), tag.getTagId() ...
const payload = tag.getPayload();
// payload.getValue(), payload.toSNBTValue(), payload.toUint8Array()...
```