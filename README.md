An IP based authentication passport strategy.

## Installation

npm i eugeniop/passport-ip --save

## Usage

Register the strategy in passport as follows:

```javascript
var passport = require('passport');
var IpStrategy = require('passport-ip').Strategy;

passport.use(new IpStrategy({
  range: '10.0.0.0/8'
}, function(profile, done){
  done(null, profile);
  //profile.id is the ip address.
}));
```

## Configuration behind a proxy

If you are running your express application behind a proxy that you trust:

```javascript
app.enable('trust proxy');
```

Then passport-ip will use the X-Forwarded-For header.

## License

MIT 2014 Eugenio Pace