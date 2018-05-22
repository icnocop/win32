﻿---
Description: 'Remotable version of the IMFWorkQueueServices::BeginUnregisterTopologyWorkQueuesWithMMCSS method.'
ms.assetid: '1a168462-400d-46c9-a489-7b861770469f'
title: RemoteBeginUnregisterTopologyWorkQueuesWithMMCSS
---

# RemoteBeginUnregisterTopologyWorkQueuesWithMMCSS

Remotable version of the [**IMFWorkQueueServices::BeginUnregisterTopologyWorkQueuesWithMMCSS**](imfworkqueueservices-beginunregistertopologyworkqueueswithmmcss.md) method.

``` syntax
[call_as(BeginUnregisterTopologyWorkQueuesWithMMCSS)]
HRESULT RemoteBeginUnregisterTopologyWorkQueuesWithMMCSS(
    IMFRemoteAsyncCallback *pCallback
);
```

## Remarks

Applications cannot call this method directly, and objects do not implement this method. The method does not appear in the vtable for the interface. If [**BeginUnregisterTopologyWorkQueuesWithMMCSS**](imfworkqueueservices-beginunregistertopologyworkqueueswithmmcss.md) is called across process boundaries, the Media Foundation proxy/stub DLL translates the call into a call to the remote method and then translates it back.

## Requirements



|                                     |                                                                                                          |
|-------------------------------------|----------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista \[desktop apps only\]<br/>                                                           |
| Minimum supported server<br/> | Windows Server 2008 \[desktop apps only\]<br/>                                                     |
| Header<br/>                   | <dl> <dt>Mfobjects.h (include Mfidl.h)</dt> </dl> |
| Library<br/>                  | <dl> <dt>Mfuuid.lib</dt> </dl>                    |



## See also

<dl> <dt>

[**IMFWorkQueueServices**](imfworkqueueservices.md)
</dt> </dl>

 

 



