---
Description: 'The DecryptMessage (General) function traps requests for renegotiation coming from the message sender. It notifies your application by decrypting the message data and returning the SEC\_I\_RENEGOTIATE value.'
ms.assetid: '036a93dc-7f52-42f8-945d-7f654289ef63'
title: Recognizing a Request to Renegotiate a Connection
---

# Recognizing a Request to Renegotiate a Connection

The [**DecryptMessage (General)**](decryptmessage--general-.md) function traps requests for renegotiation coming from the message sender. It notifies your application by decrypting the message data and returning the SEC\_I\_RENEGOTIATE value.

Your application must handle such requests by calling [**AcceptSecurityContext (General)**](acceptsecuritycontext--general-.md) (servers) or [**InitializeSecurityContext (General)**](initializesecuritycontext--general-.md) (clients) and passing in empty input buffers. After this initial call returns a value, proceed as though your application were creating a new connection.

 

 


