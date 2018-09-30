# bunnycdn-node
[![CircleCI](https://circleci.com/gh/UintaGroup/bunnycdn-node.svg?style=svg)](https://circleci.com/gh/UintaGroup/bunnycdn-node)
[![codecov](https://codecov.io/gh/UintaGroup/bunnycdn-node/branch/master/graph/badge.svg)](https://codecov.io/gh/UintaGroup/bunnycdn-node)
[![Build Status](https://travis-ci.org/UintaGroup/bunnycdn-node.svg?branch=master)](https://travis-ci.org/UintaGroup/bunnycdn-node)

BunnyCDN node. 

A simple utility for working with bunnycdn's APIs

This was initially planned to be a simple utility for us to use to update js files on Bunny's storage platform and then bust their cache after a deployment. 

### Installation

```bash
$ npm install bunnycdn-node
```

set the following environment variables
 - BUNNY_API_KEY
 - BUNNY_STORAGE_API_KEY

### Usage

#### import
``` javascript
import { Bunny } from 'bunnycdn-node';
...
const bunny = new Bunny();

```

#### Storage 

All files in Storage Zone
``` javascript
const files: StorageZoneFile[] = await bunny.storage.get('mystoragezone');
```

Contents of specific file
``` javascript
const fileContents: string = await bunny.storage.getFile('mystoragezone/somepath/afile.js');
```

Update Contents of specific file
``` javascript
bunny.storage.update('mystorage/somepath/afile.js', 'console.log(\'I was updated\');');
```

Delete specific file
``` javascript
bunny.storage.delete('mystorage/somepath/afile.js');
```
