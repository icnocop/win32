---
title: ID3DX11EffectDepthStencilVariable SetDepthStencilState method
description: Sets the depth stencil state.
ms.assetid: '4ece246f-4466-4790-8f38-450b67fff7c6'
keywords: ["SetDepthStencilState method Direct3D 11", "SetDepthStencilState method Direct3D 11 , ID3DX11EffectDepthStencilVariable interface", "ID3DX11EffectDepthStencilVariable interface Direct3D 11 , SetDepthStencilState method"]
topic_type:
- apiref
api_name:
- ID3DX11EffectDepthStencilVariable.SetDepthStencilState
api_location:
- N/A
- N/A.dll
api_type:
- COM
---

# ID3DX11EffectDepthStencilVariable::SetDepthStencilState method

Sets the depth stencil state.

## Syntax


```C++
HRESULT SetDepthStencilState(
  �UINT �������������������Index,
  �ID3D11DepthStencilState *pDepthStencilState
);
```



## Parameters

<dl> <dt>

*Index* 
</dt> <dd>

Type: **[**UINT**](https://msdn.microsoft.com/library/windows/desktop/aa383751)**

Index into an array of depth-stencil interfaces. If there is only one depth-stencil interface, use 0.

</dd> <dt>

*pDepthStencilState* 
</dt> <dd>

Type: **[**ID3D11DepthStencilState**](id3d11depthstencilstate.md)\***

Pointer to an [**ID3D11DepthStencilState**](id3d11depthstencilstate.md) interface containing the new depth stencil state.

</dd> </dl>

## Return value

Type: **[**HRESULT**](455d07e9-52c3-4efb-a9dc-2955cbfd38cc)**

Returns one of the following [Direct3D 11 Return Codes](d3d11-graphics-reference-returnvalues.md).

## Remarks

> [!Note]  
> The DirectX SDK does not supply any compiled binaries for effects. You must use Effects 11 source to build your effects-type application. For more information about using Effects 11 source, see [Differences Between Effects 10 and Effects 11](d3d11-graphics-programming-guide-effects-differences.md).

�

## Requirements



|                    |                                                                                                                                              |
|--------------------|----------------------------------------------------------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>D3dx11effect.h</dt> </dl>                                                    |
| Library<br/> | <dl> <dt>N/A (An Effects 11 library is available online as shared source.)</dt> </dl> |



## See also

<dl> <dt>

[ID3DX11EffectDepthStencilVariable](id3dx11effectdepthstencilvariable.md)
</dt> </dl>

�

�




