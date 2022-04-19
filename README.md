A React hook to access data from the [Ambient Light API](https://developer.mozilla.org/en-US/docs/Web/API/AmbientLightSensor).

## Installation

Using `npm`:

```sh
npm install --save react-hook-ambient-light
```

Using `yarn`:

```sh
yarn add react-hook-ambient-light
```

## Usage

```jsx
import React from 'react'
import useAmbientLightSensor from 'react-hook-ambient-light'

const ComponentWithAccelerometer = () => {
  const sensor = useAmbientLightSensor()

  return !sensor.error ? (
    <ul>
      <li>X: {sensor.x}</li>
      <li>Y: {sensor.y}</li>
      <li>Z: {sensor.z}</li>
    </ul>
  ) : (
    <p>No ambient light, sorry.</p>
  )
}
```

### Using `SensorOptions`

If you want to use this feature, simply provide `useAmbientLightSensor` with a `SensorOptions` object:

```jsx
const sensor = useAmbientLightSensor({
  frequency: 60, // cycles per second
})
```

## Notes

Access to data from the Ambient Light API needs user permission.

## Caveats

Ambient Light API is available only in secure contexts (only using HTTPS).

## Credits

Credit to [Bence A. Tóth](https://github.com/bence-toth) for his original hook code for [Geolocation](https://www.npmjs.com/package/react-hook-geolocation).

## License

LGPL-3.0
