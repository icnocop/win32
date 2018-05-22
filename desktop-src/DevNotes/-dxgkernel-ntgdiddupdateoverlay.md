﻿---
Description: 'Repositions or modifies the visual attributes of an overlay surface.'
ms.assetid: '6d39166c-0efc-450d-adf4-9f4dfdf7c57f'
title: NtGdiDdUpdateOverlay function
---

# NtGdiDdUpdateOverlay function

\[This function is subject to change with each operating system revision. Instead, use the Microsoft DirectDraw and Microsoft Direct3DAPIs; these APIs insulate applications from such operating system changes, and hide many other difficulties involved in interacting directly with display drivers.\]

Repositions or modifies the visual attributes of an overlay surface.

## Syntax


```C++
DWORD APIENTRY NtGdiDdUpdateOverlay(
  _In_    HANDLE                hSurfaceDestination,
  _In_    HANDLE                hSurfaceSource,
  _Inout_ PDD_UPDATEOVERLAYDATA puUpdateOverlayData
);
```



## Parameters

<dl> <dt>

*hSurfaceDestination* \[in\]
</dt> <dd>

Handle to previously created kernel-mode DirectDraw object.

</dd> <dt>

*hSurfaceSource* \[in\]
</dt> <dd>

Handle to a [**DD\_SURFACE\_LOCAL**](ddstrcts_07a504fc-c8bb-4b48-b825-4da3012e4f95.xml) structure that describes the overlay surface.

</dd> <dt>

*puUpdateOverlayData* \[in, out\]
</dt> <dd>

Pointer to a [**DD\_UPDATEOVERLAYDATA**](ddstrcts_43001aad-c6c1-4908-b945-bc612bd7297a.xml) structure that contains the information required to update the overlay.

</dd> </dl>

## Return value

**NtGdiDdUpdateOverlay** returns one of the following callback codes.



| Return code                                                                                              | Description                                                                                                                                                                                                                                                                                                                                                                |
|----------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <dl> <dt>**DDHAL\_DRIVER\_HANDLED**</dt> </dl>    | The driver has performed the operation and returned a valid return code for that operation. If this code is DD\_OK, DirectDraw or Direct3D proceeds with the function. Otherwise, DirectDraw or Direct3D returns the error code provided by the driver and aborts the function.<br/>                                                                                 |
| <dl> <dt>**DDHAL\_DRIVER\_NOTHANDLED**</dt> </dl> | The driver has no comment on the requested operation. If the driver is required to have implemented a particular callback, DirectDraw or Direct3D reports an error condition. Otherwise, DirectDraw or Direct3D handles the operation as if the driver callback had not been defined by executing the DirectDraw or Direct3D device-independent implementation.<br/> |



 

## Requirements



|                                     |                                                                                    |
|-------------------------------------|------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 2000 Professional \[desktop apps only\]<br/>                         |
| Minimum supported server<br/> | Windows 2000 Server \[desktop apps only\]<br/>                               |
| Header<br/>                   | <dl> <dt>Ntgdi.h</dt> </dl> |



## See also

<dl> <dt>

[Graphics Low Level Client Support](-dxgkernel-low-level-client-support.md)
</dt> </dl>

 

 



