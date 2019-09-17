---
description: The Code Examples For "Getting the values" page.
---

# Code Examples

## Getting Battery Values \(using JavaScript\)

### Examples Here:

{% embed url="https://codesandbox.io/s/blissful-lamport-475tt?fontsize=14" caption="CodeSandbox with iQOS.parser library to parse Holder Status." %}

### Another Example With Push-Notifications:

[https://0x77dev.github.io/iqos.web/index.html](https://0x77dev.github.io/iqos.web/index.html)

{% code-tabs %}
{% code-tabs-item title="Parsing The Holder Charge Value:" %}
```javascript
const HolderChargeEventHandler = (event) => {
    let value = event.target.value;
    let batteryValue = new Uint8Array(value.buffer.slice(-1))[0];
    if (value.buffer.byteLength == 7) {
        return batteryValue;
    } else {
         throw new Error("HOLDER NOT INSIDE THE CHARGER");
    }
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

{% code-tabs %}
{% code-tabs-item title="Parsing The Charger Charge Value:" %}
```javascript
const ChargerChargeEventHandler = (event) => {
    let value = event.target.value;
    let batteryValue = new Uint8Array(value.buffer.slice(const HolderChargeEventHandler = (event) => {
    let value = event.target.value;
    let batteryValue = new Uint8Array(value.buffer.slice(-3))[0];
    if (value.buffer.byteLength == 7) {
        return batteryValue;
    } else {
         let batteryValue = new Uint8Array(value.buffer.slice(-2))[0];
    }
};
```
{% endcode-tabs-item %}
{% endcode-tabs %}

{% code-tabs %}
{% code-tabs-item title="Connecting to iQOS" %}
```javascript
let optionalServices = ["daebb240-b041-11e4-9e45-0002a5d5c51b"];
//f8a54120-b041-11e4-9be7-0002a5d5c51b battery status characteristic

console.log('Requesting any Bluetooth Device...');
navigator.bluetooth.requestDevice({
    acceptAllDevices: true,
    optionalServices: optionalServices
})
    .then(device => {
        console.log('Connecting to GATT Server...');
        return device.gatt.connect();
    })
    .then(server => {
        console.log('Getting Services...');
        return server.getPrimaryServices();
    })
    .then(services => {
        console.log('Getting Characteristics...');
        let queue = Promise.resolve();
        services.forEach(service => {
            queue = queue.then(_ => service.getCharacteristics().then(characteristics => {
                console.log('> Service: ' + service.uuid);
                characteristics.forEach(characteristic => {
                    // log('> C: ', characteristic.uuid.uuid);
                    console.log(characteristic.uuid);
                    if (characteristic.uuid == "f8a54120-b041-11e4-9be7-0002a5d5c51b") {
                        console.log("characteristic of battery found");
                        characteristic.startNotifications().then(characteristic => {
                            characteristic.addEventListener(
                                'characteristicvaluechanged', handleCharacteristicValueChanged
                            );

                        })
                            .catch(error => { console.log(error); });

                    }
                    console.log("Reinsert holder to begin...");
                });
            }));
        });
        return queue;
    })
    .catch(error => {
        console.log('Argh! ' + error);
    });

const handleCharacteristicValueChanged = (event) => {
    console.log(HolderChargeEventHandler(event));
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

{% hint style="warning" %}
Tested only on iQOS 2.4+ and Chrome 70
{% endhint %}

## Getting Battery Values \(using Python\)

> Will be soon...



