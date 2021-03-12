---
description: ChargerSystemStatusInfo class from com.pmi.iqossdk
---

# ChargerSystemStatusInfo

## Preview

\_\_[_WARNING: Code down below is a PMI property_](../reversing/)\_\_

```text
public ChargerSystemStatusInfo(byte[] bArr) {
    this.chargerState = ChargerState.fromInt(DeviceReaderHelper.getBits(bArr[0], 0, 4));
    this.lowBattery = DeviceReaderHelper.isFlag((int) bArr[0], 6);
    this.chargerDefect = DeviceReaderHelper.isFlag((int) bArr[0], 7);
    this.holderState = HolderState.fromInt(DeviceReaderHelper.getBits(bArr[1], 0, 4));
    this.holderConnection = HolderConnection.fromInt(DeviceReaderHelper.getBits(bArr[1], 4, 2));
    this.holderDefect = DeviceReaderHelper.isFlag((int) bArr[1], 7);
}
```

## Values

| Name | Type |
| :--- | :--- |
| `chargerDefect` | boolean |
| `chargerState` | [ChargerState](chargersystemstatusinfo.md#chargerstate) |
| `holderConnection` | [HolderConnection](chargersystemstatusinfo.md#holderconnection) |
| `holderState` | [HolderState](chargersystemstatusinfo.md#holderstate) |
| `lowBattery` | boolean |

## Enums

#### HolderState

| Original Value \[int\] | Status |
| :--- | :--- |
| 1 | `CHARGING` |
| 2 | `CHARGED` |
| 3 | `READY_TO_USE` |
| 4 | `CLEANING` |
| 5 | `UNCHARGED` |
| default | `UNPLUGGED` |

#### HolderConnection

| Original Value \[int\] | Status |
| :--- | :--- |
| 1 | `RX_PIN_NOT_CONNECTED` |
| 2 | `TX_PIN_NOT_CONNECTED` |
| 3 | `NOT_CONNECTED` |
| default | `FULLY_CONNECTED` |

#### ChargerState

| Original Value \[int\] | Status |
| :--- | :--- |
| 1 | `CHARGING` |
| 2 | `CHARGED` |
| default | `IDLE` |

