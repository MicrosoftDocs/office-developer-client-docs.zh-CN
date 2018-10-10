---
title: 筛选更新记录
TOCTitle: Filtering for Updated Records
ms:assetid: 0dc22b0a-3501-078d-788c-40aa97f2e644
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248857(v=office.15)
ms:contentKeyID: 48543229
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 5f95c38da17ded3cc09c4fd8be0ad30342024093
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468016"
---
# <a name="filtering-for-updated-records"></a><span data-ttu-id="ae8d1-102">筛选更新记录</span><span class="sxs-lookup"><span data-stu-id="ae8d1-102">Filtering for Updated Records</span></span>


<span data-ttu-id="ae8d1-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="ae8d1-103">**Applies to**: Access 2013 | Office 2013</span></span>

## <a name="filtering-for-updated-records"></a><span data-ttu-id="ae8d1-104">筛选更新记录</span><span class="sxs-lookup"><span data-stu-id="ae8d1-104">Filtering for Updated Records</span></span>

<span data-ttu-id="ae8d1-p101">在调用 **UpdateBatch** 之前，可以使用 **Recordset** **Filter** 属性来只查看那些自从 **Recordset** 打开或上次调用 **UpdateBatch** 以来更改过的记录。为此，请将 **Filter** 设置为等于 **adFilterPendingRecords** ，以确定有多少记录将要更新，如下所示。</span><span class="sxs-lookup"><span data-stu-id="ae8d1-p101">Before you call **UpdateBatch**, you can use the **Recordset** **Filter** property to view only those records which have been changed since the **Recordset** was opened or the last call to **UpdateBatch**. To do this, set **Filter** equal to **adFilterPendingRecords** to determine how many records will be updated, as shown below.</span></span>

<span data-ttu-id="ae8d1-107">此示例在调用 **UpdateBatch** 之前先筛选 **Recordset** ，从而扩展了上一个 **UpdateBatch** 示例，这样，就可以向用户显示哪些记录将发生更改，并允许用户取消更新（使用 **CancelBatch** 方法）。</span><span class="sxs-lookup"><span data-stu-id="ae8d1-107">This example extends the previous **UpdateBatch** example by filtering the **Recordset** just before calling the **UpdateBatch**, showing the user which records will change and allowing her to cancel the update (using the **CancelBatch** method).</span></span>

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

