---
title: 步骤 3：填充字段列表框
TOCTitle: 'Step 3: Populate the Fields List Box'
ms:assetid: b304d3a1-2237-d6f5-6e32-c6e5b9946e10
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249855(v=office.15)
ms:contentKeyID: 48547187
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ae1513c47c79da4f4df7fee2f3f3d7b3507ac1c7
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25876657"
---
# <a name="step-3-populate-the-fields-list-box"></a>步骤 3：填充字段列表框


**适用于**： Access 2013、 Office 2013

## <a name="step-3-populate-the-fields-list-box"></a>步骤 3：填充字段列表框

**填充 Fields 列表框**

将以下代码插入 lstMain 的 Click 事件处理程序中：

```vb 
 
Private Sub lstMain_Click() 
    Dim rec As Record 
    Dim rs As Recordset 
    Set rec = New Record 
    Set rs = New Recordset 
    grs.MoveFirst 
    grs.Move lstMain.ListIndex 
    lstDetails.Clear 
    rec.Open grs 
    Select Case rec.RecordType 
        Case adCollectionRecord: 
            Set rs = rec.GetChildren 
            While Not rs.EOF 
                lstDetails.AddItem rs(0) 
                rs.MoveNext 
            Wend 
        Case adSimpleRecord: 
            recFields rec, lstDetails, txtDetails 
             
        Case adStructDoc: 
    End Select 
     
End Sub 
```

此代码声明并实例化本地**Record**和**Recordset**对象、 录制和 rs，分别。

LstMain 中所选资源相对应的行进行 grs 的当前行。 然后**Details**列表框处于清除状态并拍摄打开与的当前行。 然后**Details**列表框处于清除状态并拍摄打开与作为源 grs 的当前行。

如果资源是集合记录 （作为由**RecordType**指定），则本地**Recordset**rs，打开录制的子级。然后 lstdetails 将用的值的行上的拍摄子级打开。随后，lstdetails rs 的行中的值。

如果该资源是一个简单记录，则将调用 recFields。有关 recFields 的详细信息，请参阅下一步。

如果该资源是结构化文档，则将不实现任何代码。

