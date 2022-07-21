# GMD2 Implementation
GMD2 File Format Implementation in Node JS <br>
**Only writing is supported. Stay tuned!**

Example:
```js
require('isomorphic-fetch');

var gmd2 = require("./gmd2");
var GD = require("gd.js");

var gd = new GD({
    logLevel: 0,
});

var getLevel = async () => {
  var level = await gd.levels.get(10565740); // Bloodbath Level ID
  var levelData = await level.resolve();
  var gmd2impl = new GMD2.GMD2Implementation(levelData, "Bloodbath.gmd2");
  gmd2impl.EmbedSong(); // Embed song to the file if required.
  gmd2impl.GenerateFile();
}

getLevel();
```

# Known Issues
- Level Description is not saved properly
