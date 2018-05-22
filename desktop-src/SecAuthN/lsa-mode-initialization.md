---
Description: 'When the computer system is started, the Local Security Authority (LSA) automatically loads all registered security support provider/authentication package (SSP/AP) DLLs into its process space. The following illustrations show the initialization process.'
ms.assetid: '2d52cbbf-9e28-4c6f-8b4c-448b73c6dbf8'
title: LSA Mode Initialization
---

# LSA Mode Initialization

When the computer system is started, the [*Local Security Authority*](security.l_gly#-security-local-security-authority-gly) (LSA) automatically loads all registered [*security support provider*](security.s_gly#-security-security-support-provider-gly)/[*authentication package*](security.a_gly#-security-authentication-package-gly) (SSP/AP) DLLs into its process space. The following illustrations show the initialization process.

> [!Note]  
> "Kerberos" represents the Microsoft [*Kerberos*](security.k_gly#-security-kerberos-protocol-gly) SSP/AP, and "My SSP/AP" represents a custom SSP/AP that contains two custom security packages.

 

![lsa mode initialization](images/lsamode1.png)

At startup, the LSA calls the [**SpLsaModeInitialize**](splsamodeinitialize.md) function in each SSP/AP to obtain pointers to the functions implemented by each [*security package*](security.s_gly#-security-security-package-gly) in the DLL. The function pointers are passed to the LSA in an array of [**SECPKG\_FUNCTION\_TABLE**](secpkg-function-table.md) structures.

![the lsa calls splsamodeinitialize to get function pointers](images/lsamode2.png)

After receiving the set of [**SECPKG\_FUNCTION\_TABLE**](secpkg-function-table.md) structures, the LSA calls each security package's [**SpInitialize**](spinitialize.md) function. The LSA uses this function call to pass each security package an [**LSA\_SECPKG\_FUNCTION\_TABLE**](lsa-secpkg-function-table.md) structure, which contains pointers to the LSA support functions available to security packages. In addition to storing the pointers to the LSA support functions, custom security packages should use their implementation of the **SpInitialize** function to perform any initialization-related processing.

For a list of the LSA support functions available to LSA-mode security packages, see [LSA Functions Called by SSP/APs](authentication-functions.md#lsa-functions-called-by-sspaps).

For information about registering an SSP/AP DLL, see [Registering SSP/AP DLLs](registering-ssp-ap-dlls.md).

 

 


