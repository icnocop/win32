---
Description: 'TBD.'
audience: developer
author: 'REDMOND\\danlep'
manager: 'REDMOND\\timlt'
ms.assetid: 'd4fb24d9-b010-4d3e-8a0b-d7269ebd6e38'
ms.prod: 'windows-server-dev'
ms.technology: 'compute-cluster-pack'
ms.tgt_platform: multiple
title: 'MPI\_File\_get\_group function'
---

# MPI\_File\_get\_group function

TBD

## Syntax


```C++
int MPIAPI MPI_File_get_group(
  ������MPI_File �file,
  _Out_�MPI_Group *group
);
```



## Parameters

<dl> <dt>

*file* 
</dt> <dd>

TBD

</dd> <dt>

*group* \[out\]
</dt> <dd>

TBD

</dd> </dl>

## Return value

TBD

## Fortran

``` syntax
MPI_FILE_GET_GROUP(FH, GROUP, IERROR)
    INTEGER FH, GROUP, IERROR
```

## Requirements



|                    |                                                                                                                                                                                          |
|--------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Product<br/> | HPC Pack 2012 MS-MPI Redistributable Package, HPC Pack 2008 R2 MS-MPI Redistributable Package, HPC Pack 2008 MS-MPI Redistributable Package or HPC Pack 2008 Client Utilities<br/> |
| Header<br/>  | <dl> <dt>Mpi.h; </dt> <dt>Mpif.h</dt> </dl>                                           |
| Library<br/> | <dl> <dt>Msmpi.lib</dt> </dl>                                                                                                     |
| DLL<br/>     | <dl> <dt>Msmpi.dll</dt> </dl>                                                                                                     |



## See also

<dl> <dt>

[MPI File Functions](mpi-file-functions.md)
</dt> </dl>

�

�



