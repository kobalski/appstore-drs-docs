---
title: CancelTestOrder Endpoint
sidebar: dash
permalink: dash-canceltestorder-endpoint.html
product: Dash Replenishment Service
toc-style: kramdown
github: true
---


CancelTestOrder allows developers to cancel test orders for one or all slots in the device. If the `SLOT_ID` is not provided, test orders from all slots will be canceled.  

## Path

<pre class="curl">
/testOrders/<span class="endpointParam">{SLOT_ID}</span>
</pre>

## HTTP Method

DELETE

## Header Parameters

```
x-amzn-accept-type: com.amazon.dash.replenishment.DrsCancelTestOrdersResult@1.0
x-amzn-type-version: com.amazon.dash.replenishment. DrsCancelTestOrdersInput@1.0
Authorization: Bearer (ACCESS_TOKEN)
```

## Versioning

Versioning is used to incrementally update API functionality without directly impacting customers. x-amzn-type-version and x-amzn-accept-type headers must be sent with each call. The following are supported by the ResetSlotLock Endpoint:

```
x-amzn-type-version: com.amazon.dash.replenishment.DrsCancelTestOrdersInput@1.0
x-amzn-accept-type: com.amazon.dash.replenishment.DrsCancelTestOrdersResult@1.0
```

## Response Example

```
HTTP/1.1 200 OK
x-amzn-type-version: com.amazon.dash.replenishment.DrsCancelTestOrdersResult@1.0
{
  "slotOrderStatuses": [
    {
      "orderStatus": "NO_ORDER_IN_PROGRESS",
      "slotId": "slot1"
    },
    {
      "orderStatus": "NO_ORDER_IN_PROGRESS",
      "slotId": "slot2"
    }
  ]
}
```

## Error Responses
<table>
   <colgroup>
      <col width="40%" />
      <col width="60%" />
   </colgroup>
  <thead>
    <tr>
      <th>Errors</th>
      <th>Descriptions</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>HTTP/1.1 500 Internal Server Error</td>
      <td>Indicates that an error occurred internally to the server.</td>
    </tr>
    <tr>
      <td>HTTP/1.1 400 Bad Request</td>
      <td>Client error: an error occurred due to data passed in by the client (e.g., bad token).  Amazon will make a best effort to provide feedback on the nature of the failure in the response body.</td>
    </tr>
  </tbody>
</table>

{% include links.html %}
