---
title: 发送更新： UpdateBatch
TOCTitle: 'Sending the updates: UpdateBatch'
ms:assetid: a840b9a7-7ccd-9c31-7951-8921dadf381e
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249778(v=office.15)
ms:contentKeyID: 48546898
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 7da0320bf42d1a1720bccfe8bf9e3843a2bb94f5
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25946935"
---
# <a name="sending-the-updates-updatebatch"></a><span data-ttu-id="259b9-102">发送更新： UpdateBatch</span><span class="sxs-lookup"><span data-stu-id="259b9-102">Sending the updates: UpdateBatch</span></span>


<span data-ttu-id="259b9-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="259b9-103">**Applies to**: Access 2013, Office 2013</span></span>

## <a name="sending-the-updates-updatebatch-method"></a><span data-ttu-id="259b9-104">发送更新：UpdateBatch</span><span class="sxs-lookup"><span data-stu-id="259b9-104">Sending the Updates: UpdateBatch Method</span></span>

<span data-ttu-id="259b9-p101">以下代码通过将 **LockType** 属性设置为 **adLockBatchOptimistic** 并将 **CursorLocation** 设置为 **adUseClient** 来成批打开 **Recordset** 。该代码添加了两个新记录并更改现有记录中某个字段的值，保存初始值，然后调用 **UpdateBatch** 将所做的更改发回到数据源。</span><span class="sxs-lookup"><span data-stu-id="259b9-p101">The following code opens a **Recordset** in batch mode by setting the **LockType** property to **adLockBatchOptimistic** and the **CursorLocation** to **adUseClient**. It adds two new records and changes the value of a field in an existing record, saving the original values, and then calls **UpdateBatch** to send the changes back to the data source.</span></span>

```vb 
 
'BeginBatchUpdate 
    strSQL = "SELECT ShipperId, CompanyName, Phone FROM Shippers" 
                  
    objRs1.CursorLocation = adUseClient 
    objRs1.Open strSQL, strConn, adOpenStatic, adLockBatchOptimistic, adCmdText 
     
    ' Change value of Phone field for first record in Recordset, saving value 
    ' for later restoration. 
    intId = objRs1("ShipperId") 
    strPhone = objRs1("Phone") 
     
    objRs1("Phone") = "(111) 555-1111" 
     
    'Add two new records 
    For i = 0 To 1 
        objRs1.AddNew 
        objRs1(1) = "New Shipper #" & CStr((i + 1)) 
        objRs1(2) = "(nnn) 555-" & i & i & i & i 
    Next i 
     
    ' Send the updates 
    objRs1.UpdateBatch 
'EndBatchUpdate 
```

<span data-ttu-id="259b9-107">如果您在调用 **UpdateBatch** 方法时正在编辑当前的记录或者正在添加新记录，ADO 在将批更改传输给提供程序之前，会自动调用 **Update** 方法来保存对当前记录进行的任何未决更改。</span><span class="sxs-lookup"><span data-stu-id="259b9-107">If you are editing the current record or adding a new record when you call the **UpdateBatch** method, ADO will automatically call the **Update** method to save any pending changes to the current record before transmitting the batched changes to the provider.</span></span>

