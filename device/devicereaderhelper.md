---
description: >-
  DeviceReaderHelper from com.pmi.iqossdk.sdk.DeviceReaderHelper, used for value
  parsing
---

# DeviceReaderHelper

### isFlag

```text
public static boolean isFlag(int i, int i2) {
        return ((i >> i2) & 1) != 0;
}

public static boolean isFlag(long j, int i) {
        return ((j >> i) & 1) != 0;
}
```

### unsignedInt8ToBytes

```text
public static byte unsignedInt8ToBytes(int i) {
        return (byte) (i & v.as);
}
```

### getBits

```text
public static int getBits(int i, int i2, int i3) {
    return (i & ((v.as >>> (8 - i3)) << i2)) >> i2;
}
```

