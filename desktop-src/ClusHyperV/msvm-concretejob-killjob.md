---
title: KillJob method of the Msvm\_ConcreteJob class
description: Shuts down a job.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\markl
ms.assetid: '94503c63-16ce-450e-8bcc-42bea6be5615'
ms.prod: 'windows-server-dev'
ms.technology:
- 'failover-cluster-hyperv'
- 'windows-management-instrumentation'
ms.tgt_platform: multiple
keywords: ["KillJob method", "KillJob method, Msvm_ConcreteJob class", "Msvm_ConcreteJob class, KillJob method"]
topic_type:
- apiref
api_name:
- Msvm_ConcreteJob.KillJob
api_location:
- VMMS.exe
api_type:
- COM
---

# KillJob method of the Msvm\_ConcreteJob class

> [!Note]  
> Deprecated description: Shuts down a job.

�

This method is deprecated. Instead we recommend that you use the **RequestStateChange** method.

## Syntax


```mof
uint32 KillJob(
  [in]�boolean DeleteOnKill
);
```



## Parameters

<dl> <dt>

*DeleteOnKill* \[in\]
</dt> <dd>

**True** if the job should be automatically deleted upon termination; otherwise, **false**.

> [!Note]  
> This parameter takes precedence of the **DeleteOnCompletion** property of the **CIM\_Job** class.

�

</dd> </dl>

## Return value

The possible returns values are:

<dl> <dt>


</dt> <dd>

0

Success

</dd> <dt>


</dt> <dd>

1

Not Supported

</dd> <dt>


</dt> <dd>

2

Unknown

</dd> <dt>


</dt> <dd>

3

Timeout

</dd> <dt>


</dt> <dd>

4

Failed

</dd> <dt>


</dt> <dd>

6

Access Denied

</dd> <dt>


</dt> <dd>

7

Not Found

</dd> <dt>


</dt> <dd>

8�32767

DMTF Reserved

</dd> <dt>


</dt> <dd>

32768�65535

Vendor Specific

</dd> </dl>

## Requirements



|                                     |                                                                                                        |
|-------------------------------------|--------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | None supported<br/>                                                                              |
| Minimum supported server<br/> | Windows Server�2016<br/>                                                                         |
| Namespace<br/>                | Root\\HyperVCluster\\v2<br/>                                                                     |
| MOF<br/>                      | <dl> <dt>WindowsHyperVCluster.V2.mof</dt> </dl> |
| DLL<br/>                      | <dl> <dt>VMMS.exe</dt> </dl>                    |



## See also

<dl> <dt>

[**Msvm\_ConcreteJob**](msvm-concretejob.md)
</dt> </dl>

�

�




