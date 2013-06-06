# GeoBag.js - Location Services Wrapper

Usage:

```javascript
define(function(require){
  var geo = require('geobag');

  // Override getPosition in the case that geo is not supported
  // and just send back some default coordinates
  if (!geo.isSupported()){
    geo.getLocation = function(callback){
      if (callback) return callback(null, config.defaults.location);
    };
  }

  // Get Location
  geo.getLocation(function(error, position){
    if (error) return console.error(error);

    console.log("Your position is:");
    console.log("Latitude:",   position.lat);
    console.log("Longitude:",  position.lon);
  });
});
```
