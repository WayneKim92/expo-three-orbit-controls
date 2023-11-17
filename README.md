# expo-three-orbit-controls

[![supports iOS](https://img.shields.io/badge/iOS-4630EB.svg?style=flat-square&logo=APPLE&labelColor=999999&logoColor=fff)](https://itunes.apple.com/app/apple-store/id982107779)
[![supports Android](https://img.shields.io/badge/Android-4630EB.svg?style=flat-square&logo=ANDROID&labelColor=A4C639&logoColor=fff)](https://play.google.com/store/apps/details?id=host.exp.exponent&referrer=expo-three-orbit-controls)
[![supports web](https://img.shields.io/badge/web-4630EB.svg?style=flat-square&logo=GOOGLE-CHROME&labelColor=4285F4&logoColor=fff)](https://docs.expo.io/workflow/web/)

This is a very rough port of [Three.js `OrbitControls`](https://threejs.org/docs/#examples/en/controls/OrbitControls) for universal React apps with Expo.

- Fully written in TypeScript because it's the best! 🌟
- Internally this uses a basic PanResponder for gestures. PRs to migrate PanResponder to React Native Gesture Handler are very welcome.
- On web, two finger gestures aren't currently implemented.
- On native, the camera may jump when panning + zooming ends due to issues with React Native `PanResponder`.

## ☁️ Installation

Add this line to your `package.json` dependencies

```json
"expo-three-orbitcontrols": "https://github.com/foufrix/expo-three-orbit-controls",
```

Then run `yarn` or `npm install` depending of your package manager.

## 🚀 Usage

Import into your project:

```tsx
import { useState } from 'react';
import { Canvas } from '@react-three/fiber/native';
import OrbitControls from 'expo-three-orbitcontrols';
import { Camera } from 'three';


const Test = () => {
    const [camera, setCamera] = useState<Camera | null>(null);    
    return(
      <View style={{ flex: 1 }}>
        <OrbitControls style={{ flex: 1 }} camera={camera}>
          <Canvas onCreated={({ camera }) => setCamera(camera)}></Canvas>
        </OrbitControls>
     </View>
    )
}
```


Check out the [example](./example/App.tsx) for more info.

## Roadmap

- [ ] Zoom
- [ ] Move around
- [X] Move scene 
