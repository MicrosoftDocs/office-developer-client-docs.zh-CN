---
title: 步骤 4：填充细节文本框
TOCTitle: 'Step 4: Populate the Details Text Box'
ms:assetid: fa5e4482-8986-0c03-1e46-7b7fefb5fb58
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250278(v=office.15)
ms:contentKeyID: 48548839
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: e0f04d52edc55c7ccc5163bc9a858d7bc8845702
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467370"
---
# <a name="step-4-populate-the-details-text-box"></a>步骤 4：填充细节文本框


**适用于**： Access 2013 |Office 2013

## <a name="step-4-populate-the-details-text-box"></a>步骤 4：填充细节文本框

**填充 Details 文本框**

新建一个名为 recFields 的子例程并插入以下代码：

```vb 
 
Sub recFields(r As Record, l As ListBox, t As TextBox) 
    Dim f As Field 
    Dim s As Stream 
    Set s = New Stream 
    Dim str As String 
     
    For Each f In r.Fields 
        l.AddItem f.Name & ": " & f.Value 
    Next 
    t.Text = "" 
    If r!RESOURCE_CONTENTCLASS = "text/plain" Then 
        s.Open r, adModeRead, adOpenStreamFromRecord 
        str = s.ReadText(1) 
        s.Position = 0 
        If Asc(Mid(str, 1, 1)) = 63 Then '//63 = "?" 
            s.Charset = "ascii" 
            s.Type = adTypeText 
        End If 
        t.Text = s.ReadText(adReadAll) 
    End If 
End Sub 
```

上面的代码用传递到 recFields 的简单记录的字段和值填充 lstDetails。如果该资源是文本文件，则将从该资源记录打开文本的 **Stream** 。该代码确定字符集是否为 ASCII 并将 **Stream** 内容复制到 txtDetails 中。

