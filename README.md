# baslin [![Version](https://img.shields.io/badge/version-1.0.0-green.svg)]() [![Build Status](https://img.shields.io/badge/build-passing-brightgreen.svg)]()

Make, import and load custom, scaleable data archives with ease.

# Usage

Baslin uses bases to bind data to and build onto. To simply define new datasets or simply import or load pre-existing ones use the syntax provided:

```js

import * from baslin

const archive = new base("archive_build",  { "name": "example", "data": [] }); // Create new archive

// To import an external archive

const archive = new base("archive_import", { "type": "external", "url": "https://example.com/dataset123.js" });

// To load a local archive

const archive = new base ("archive_load", { "type": "native", "name": "example", "directory": "../example.js", }) // Referencing the directory is not required if the base has already been defined or used in the same file

```

When defining bases, you don't need establish a type but a name is required. If you want to cache data inside the browser to access without having to import it externally each time, you can use the global library's methods to do this.

```js

baslin.cache(archive, key) // This key will be used to access the archive later

// To check the cache you can run the method without any parameters

baslin.cache()

// Output: { key: archive }
```
