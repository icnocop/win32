---
Description: 'Indicates that you are finish sending SOA requests and that the broker should commit all requests.'
audience: developer
author: 'REDMOND\\danlep'
manager: 'REDMOND\\timlt'
ms.assetid: 'F1FAD8FD-D843-44FA-9D38-90F09D8BF334'
ms.prod: 'windows-server-dev'
ms.technology: 'compute-cluster-pack'
ms.tgt_platform: multiple
title: Indicate the End of Requests
---

# Indicate the End of Requests

Indicates that you are finish sending SOA requests and that the broker should commit all requests.

## Request

You can specify the **Indicate the End of Requests** request as follows.



| Method                      | Request URI                                                                                                                |
|-----------------------------|----------------------------------------------------------------------------------------------------------------------------|
| POST (before HPC Pack 2016) | https://*head\_node\_name*:*port*/WindowsHPC/*HPC\_cluster\_name*/session/*session\_identifier*/batch/*batch\_name*/Commit |
| POST (HPC Pack 2016)        | https://*head\_node\_name*:*port*/WindowsHPC/session/*session\_identifier*/batch/*batch\_name*/Commit                      |



�

For sessions that are managed by the Azure HPC Scheduler, the head node name should have a format of *Windows\_Azure\_service\_name*.cloudapp.net.

To get the name to use for the HPC cluster, use the [**Get Clusters**](get-clusters.md) operation.

### URI Parameters

You can specify the following additional parameters on the request URI.



| Parameter   | Description                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|-------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| api-version | Required if the request does not contain the api-version header. Specifies the version of the operation to use for this request. To specify Microsoft�HPC�Pack�2008�R2 with Service�Pack�3 (SP3), use a value of 2011-11-01. The minimum version that supports this operation is Microsoft�HPC�Pack�2008�R2 with SP3.<br/> The value of this URI parameter is ignored if the request also contains the api-version header.<br/> |



�

### Request Headers

The following table describes required and optional request headers.



| Request Header | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                |
|----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| api-version    | Required if the request does not include the api-version URI parameter. Specifies the version of the operation to use for this request. To specify Microsoft�HPC�Pack�2008�R2 with SP3, use a value of 2011-11-01. The minimum version that supports this operation is Microsoft�HPC�Pack�2008�R2 with SP3.<br/> The value specified in this header overrides the value specified in the api-version URI parameter if both are specified.<br/> |
| CONTENT-TYPE   | Indicates type of content that the request contains.<br/>                                                                                                                                                                                                                                                                                                                                                                                            |
| Content-Length | Required. Indicates the length of the request body. Specify 0 for this request.<br/>                                                                                                                                                                                                                                                                                                                                                                 |
| Accept         | Optional. Specifies the type of content accepted in the response. Specify application/json to get a response body that is an object represented as text in JavaScript Object Notation (JSON), or specify application/xml to get a response body that is formatted as XML. The default value is application/xml.<br/>                                                                                                                                 |



�

### Request Body

None.

## Response

The response includes an HTTP status code and a set of response headers.

### Status Code

A successful operation returns status code 201 (Created).

If the request includes neither the api-version URI parameter nor the api-version header, the operation returns status code 400 (Bad Request).

For more information about status codes, see [HttpStatusCode](https://msdn.microsoft.com/library/system.net.httpstatuscode.aspx).

The error response will be contained in a descriptive XML response (Note: Values will vary based on the error):


```XML
<HpcWebServiceFault xmlns="http://schemas.microsoft.com/HPCS2008R2/common" xmlns:i="http://www.w3.org/2001/XMLSchema-instance">
  <Code>267386880</Code>
  <Message>Error message text.</Message>
  <Values i:nil="true" xmlns:a="http://schemas.datacontract.org/2004/07/System.Collections.Generic"/>
</HpcWebServiceFault>
```



### Response Headers

The response for this operation includes the following standard HTTP headers:

-   Content-Length

-   Date

-   Pack

All standard headers conform to the [HTTP/1.1 protocol specification](http://www.w3.org/Protocols/rfc2616/rfc2616.mdl).

### Response Body

None.

## Remarks

This operation commits a pending batch of SOA requests. If the list of SOA requests were submitted using the Send Requests operation with a commit parameter of false, then the broker will not commit the SOA requests for the batch during the Send Requests operation. Instead, the broker will queue the batch of SOA requests. When the broker receives the Indicate the End of Requests operation, the broker commits the queued batch of SOA requests. See the commit URI parameter of the [**Send Requests**](send-a-batch-of-requests.md) operation for more information.

This operation is supported only for sessions that are managed by the Azure HPC Scheduler.

## Requirements



|                    |                                                                                      |
|--------------------|--------------------------------------------------------------------------------------|
| Product<br/> | HPC Pack 2008 R2 with at least SP3, or a later version of HPC Pack.<br/>       |
| Header<br/>  | <dl> <dt>Wbemcli.h</dt> </dl> |



�

�



