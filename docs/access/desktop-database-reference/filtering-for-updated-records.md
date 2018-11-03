---
title: 筛选更新记录
TOCTitle: Filtering for updated records
ms:assetid: 0dc22b0a-3501-078d-788c-40aa97f2e644
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248857(v=office.15)
ms:contentKeyID: 48543229
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b3bf6619b9b375642bc9f279aea92cb20df3b859
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25947810"
---
# <a name="filtering-for-updated-records"></a>筛选更新记录

**适用于**： Access 2013、 Office 2013

## <a name="filtering-for-updated-records"></a>筛选更新的记录

在调用 **UpdateBatch** 之前，可以使用 **Recordset** **Filter** 属性来只查看那些自从 **Recordset** 打开或上次调用 **UpdateBatch** 以来更改过的记录。为此，请将 **Filter** 设置为等于 **adFilterPendingRecords** ，以确定有多少记录将要更新，如下所示。

此示例在调用 **UpdateBatch** 之前先筛选 **Recordset** ，从而扩展了上一个 **UpdateBatch** 示例，这样，就可以向用户显示哪些记录将发生更改，并允许用户取消更新（使用 **CancelBatch** 方法）。

```vb 
 
'BeginFilterAffected 
    objRs1.Filter = adFilterPendingRecords 
    objRs1.MoveFirst 
     
    strMsg = "The following " & objRs1.RecordCount & " values will " & _ 
             "be updated. Do you wish to proceed?" 
    While Not objRs1.EOF 
        strMsg = strMsg & vbCrLf & objRs1(0) & vbTab & objRs1(1) & vbTab & _ 
                 objRs1(2) & vbCrLf 
        objRs1.MoveNext 
    Wend 
     
    blnResp = MsgBox(strMsg, vbYesNo, "Proceed with Update?") 
    If blnResp = True Then 
        objRs1.UpdateBatch 
    Else 
        objRs1.CancelBatch 
    End If 
'EndFilterAffected 
```

