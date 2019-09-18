---
description: BLE characteristics for iQOS 2.4+
---

# Getting the Values

{% page-ref page="code-examples.md" %}

## **BLE** _Characteristics_

| Characteristic | Description |
| :--- | :--- |
| 00002a00-0000-1000-8000-00805f9b34fb | Device Name |
| 00002a01-0000-1000-8000-00805f9b34fb | Appearance |
| 00002a04-0000-1000-8000-00805f9b34fb | Peripheral Preferred Connection Parameters |
| 00002a05-0000-1000-8000-00805f9b34fb | Service Changed |
| 00002a24-0000-1000-8000-00805f9b34fb | Model Number String |
| 00002a25-0000-1000-8000-00805f9b34fb | Serial Number String |
| 00002a28-0000-1000-8000-00805f9b34fb | Software Revision String |
| 00002a29-0000-1000-8000-00805f9b34fb | Manufacturer Name String |
| e16c6e20-b041-11e4-a4c3-0002a5d5c51b | UUID\_SCP\_CONTROL\_POINT |
| f8a54120-b041-11e4-9be7-0002a5d5c51b | UUID\_BATTERY\_INFORMATION |
| ecdfa4c0-b041-11e4-8b67-0002a5d5c51b | UUID\_DEVICE\_STATUS |

| **Service** | Description |
| :--- | :--- |
| 00001801-0000-1000-8000-00805f9b34fb | Generic Attribute |
| 00001800-0000-1000-8000-00805f9b34fb | Generic Access |
| daebb240-b041-11e4-9e45-0002a5d5c51b | UUID\_RRP\_SERVICE |

The Battery Data Goes Here: 

{% code-tabs %}
{% code-tabs-item title="UUID\_BATTERY\_INFORMATION" %}
```text
f8a54120-b041-11e4-9be7-0002a5d5c51b
```
{% endcode-tabs-item %}
{% endcode-tabs %}

When the _**Holder**_ inside the _**Charger**_, the length of value **is 7 bytes long**, **if not it will be 6 bytes long**...

**The Value of this** _**characteristic is an ByteArray**, and this is an description of the **bytes we know:**_

1. ~~WE DONT KNOW~~
2. ~~WE DONT KNOW~~
3. ~~WE DONT KNOW~~
4. **THE** _**CHARGER BATTERY VALUE**_
5. ~~WE DONT KNOW~~
6. ~~WE DONT KNOW~~
7. **If holder not inside this byte will not exist**, but if it exists the holder on charge, and _**this is an battery value**_ **\(on** _**iQOS 2.4+ it will be 0 or 100 only!**_**\)**



