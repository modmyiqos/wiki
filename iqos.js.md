---
description: an iQOS library written in JavaScript to talk with iQOS over BLE.
---

# iQOS.js

{% embed url="https://codesandbox.io/s/iqosjs-demo-cdt6r" caption="iQOS.js CodeSandbox " %}

{% embed url="https://github.com/modmyiqos/iQOS.js" caption="Github Repository" %}

## How to Use

* You will need to install this library:
  * **yarn**: `yarn add @0x77/iqos`
  * **npm**: `npm i -S @0x77/iqos`
* Then you need to _import_ and _bootstrap_ it:

```javascript
// Import the library:
import iQOS from '@0x77/iqos';
const iqos = new iQOS();
// Then bootstrap:
iqos.bootstrap();
// You will receive a prompt to select iQOS device.
```

* Get the _charge status_:

```javascript
// Imagine that Holder not inside Chrager:
console.log(iqos.holderCharge);
// Will return -> false -> because its not inside Charger
/*
 If it will be inside Charger 
 it will be non false and 0 or 100
*/
console.log(iqos.chargerCharge);
// It will return the percentage of Charger Charge.

// To access the raw data of iQOS status you can use:
console.log(iqos.rawStatus);

// Check if device ready (to realtime data updates):
console.log(iqos.deviceReady);

// Check is it connected:
console.log(iqos.connected);
```

