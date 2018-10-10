---
title: 发送更新：UpdateBatch
TOCTitle: 'Sending the Updates: UpdateBatch'
ms:assetid: a840b9a7-7ccd-9c31-7951-8921dadf381e
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249778(v=office.15)
ms:contentKeyID: 48546898
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: df52f5bf2dbada1176a76cda3b77dcbc9966b313
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466266"
---
# <a name="sending-the-updates-updatebatch"></a>发送更新：UpdateBatch


**适用于**： Access 2013 |Office 2013

## <a name="sending-the-updates-updatebatch-method"></a>发送更新：UpdateBatch

以下代码通过将 **LockType** 属性设置为 **adLockBatchOptimistic** 并将 **CursorLocation** 设置为 **adUseClient** 来成批打开 **Recordset** 。该代码添加了两个新记录并更改现有记录中某个字段的值，保存初始值，然后调用 **UpdateBatch** 将所做的更改发回到数据源。

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

如果您在调用 **UpdateBatch** 方法时正在编辑当前的记录或者正在添加新记录，ADO 在将批更改传输给提供程序之前，会自动调用 **Update** 方法来保存对当前记录进行的任何未决更改。

