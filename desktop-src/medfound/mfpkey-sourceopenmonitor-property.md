﻿---
Description: 'Contains a pointer to the application's IMFSourceOpenMonitor interface.'
ms.assetid: '5b94ae87-91fc-49d6-9355-83327cfdb3f3'
title: 'MFPKEY\_SourceOpenMonitor property'
---

# MFPKEY\_SourceOpenMonitor property

Contains a pointer to the application's [**IMFSourceOpenMonitor**](imfsourceopenmonitor.md) interface.



Data type

PROPVARIANT type (vt)

PROPVARIANT member

**IUnknown** pointer

VT\_UNKNOWN

**punkVal**



## Remarks

Applications can pass this property to the source resolver to get event notifications from the network source.

## Requirements



|                                     |                                                                                    |
|-------------------------------------|------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista \[desktop apps only\]<br/>                                     |
| Minimum supported server<br/> | Windows Server 2008 \[desktop apps only\]<br/>                               |
| Header<br/>                   | <dl> <dt>Mfidl.h</dt> </dl> |



## See also

<dl> <dt>

[Media Foundation Properties](media-foundation-properties.md)
</dt> </dl>

 

 



