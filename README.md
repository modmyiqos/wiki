---
description: BLE characteristics for iQOS 2.4+
---

# Getting the Values

## **BLE** _Characteristics_

The Battery Data Goes Here: 

{% code-tabs %}
{% code-tabs-item title="BLE BATTERY CHARACTERISTIC" %}
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



