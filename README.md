# vallox-api

[![Build Status](https://travis-ci.org/danielbayerlein/vallox-api.svg?branch=master)](https://travis-ci.org/danielbayerlein/vallox-api)
[![JavaScript Style Guide](https://img.shields.io/badge/code_style-standard-brightgreen.svg)](https://standardjs.com)
[![Greenkeeper badge](https://badges.greenkeeper.io/danielbayerlein/vallox-api.svg)](https://greenkeeper.io/)

API for [Vallox](https://www.vallox.com) ventilation units

## Installation

Not yet available.

## Usage

### Initalize

Returns the client instance.

```javascript
new Vallox({ ip: '192.168.178.33', port: 80 })
```

### `.getProfile()`

Returns the current profile id.

```javascript
await client.getProfile()
```

[Example](./examples/getProfile.js)

### `.fetchMetric(string)`

Returns the value of the metric key.

```javascript
await client.fetchMetric('A_CYC_FAN_SPEED')
```

[Example](./examples/fetchMetric.js)

### `.fetchMetrics(array[string])`

Returns an array with the values if the metric keys.

```javascript
await client.fetchMetrics([
  'A_CYC_TEMP_EXHAUST_AIR',
  'A_CYC_TEMP_OUTDOOR_AIR'
])
```

[Example](./examples/fetchMetrics.js)

### `.setProfile(int, int)`

Sets the profile.

```javascript
// Permanently AWAY profile
await client.setProfile(client.PROFILES.AWAY)

// FIREPLACE mode for configured timeout
await client.setProfile(client.PROFILES.FIREPLACE)

// FIREPLACE mode for 30 min
await client.setProfile(client.PROFILES.FIREPLACE, 30)
```

[Example](./examples/setProfile.js)

### `.setValues(object{string: int})`

Sets the value for the metric key.

```javascript
await client.setValues({
  'A_CYC_HOME_SPEED_SETTING': 60
})
```

[Example](./examples/setValues.js)

## Supported units

* ValloPlus 350 MV
* _Please add your tested unit_

## Credits

* [yozik04/vallox_websocket_api](https://github.com/yozik04/vallox_websocket_api)

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new [Pull Request](../../pull/new/master)

## Copyright

Copyright (c) 2019-present Daniel Bayerlein. See [LICENSE](./LICENSE.md) for details.