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
# <a name="step-3-populate-the-fields-list-box"></a><span data-ttu-id="3d6e7-102">步骤 3：填充字段列表框</span><span class="sxs-lookup"><span data-stu-id="3d6e7-102">Step 3: Populate the Fields List Box</span></span>


<span data-ttu-id="3d6e7-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="3d6e7-103">**Applies to**: Access 2013, Office 2013</span></span>

## <a name="step-3-populate-the-fields-list-box"></a><span data-ttu-id="3d6e7-104">步骤 3：填充字段列表框</span><span class="sxs-lookup"><span data-stu-id="3d6e7-104">Step 3: Populate the Fields List Box</span></span>

<span data-ttu-id="3d6e7-105">**填充 Fields 列表框**</span><span class="sxs-lookup"><span data-stu-id="3d6e7-105">**To populate the Fields list box**</span></span>

<span data-ttu-id="3d6e7-106">将以下代码插入 lstMain 的 Click 事件处理程序中：</span><span class="sxs-lookup"><span data-stu-id="3d6e7-106">Insert the following code into the Click event handler of lstMain:</span></span>

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

<span data-ttu-id="3d6e7-107">此代码声明并实例化本地**Record**和**Recordset**对象、 录制和 rs，分别。</span><span class="sxs-lookup"><span data-stu-id="3d6e7-107">This code declares and instantiates local **Record** and **Recordset** objects, rec and and rs, respectively.</span></span>

<span data-ttu-id="3d6e7-108">LstMain 中所选资源相对应的行进行 grs 的当前行。</span><span class="sxs-lookup"><span data-stu-id="3d6e7-108">The row corresponding to the resource selected in lstMain is made the current row of grs.</span></span> <span data-ttu-id="3d6e7-109">然后**Details**列表框处于清除状态并拍摄打开与的当前行。</span><span class="sxs-lookup"><span data-stu-id="3d6e7-109">Then the **Details** list box is cleared and rec is opened with the current row of .</span></span> <span data-ttu-id="3d6e7-110">然后**Details**列表框处于清除状态并拍摄打开与作为源 grs 的当前行。</span><span class="sxs-lookup"><span data-stu-id="3d6e7-110">Then the **Details** list box is cleared and rec is opened with the current row of grs as the source.</span></span>

<span data-ttu-id="3d6e7-111">如果资源是集合记录 （作为由**RecordType**指定），则本地**Recordset**rs，打开录制的子级。然后 lstdetails 将用的值的行上的拍摄子级打开。随后，lstdetails rs 的行中的值。</span><span class="sxs-lookup"><span data-stu-id="3d6e7-111">If the resource is a collection record (as specified by **RecordType**), the local **Recordset**, rs, is opened on the children of rec. Then lstDetails is filled with the values from the rows of is opened on the children of rec. Then lstDetails is filled with the values from the rows of rs.</span></span>

<span data-ttu-id="3d6e7-p102">如果该资源是一个简单记录，则将调用 recFields。有关 recFields 的详细信息，请参阅下一步。</span><span class="sxs-lookup"><span data-stu-id="3d6e7-p102">If the resource is a simple record, recFields is called. For more information about recFields, see the next step.</span></span>

<span data-ttu-id="3d6e7-114">如果该资源是结构化文档，则将不实现任何代码。</span><span class="sxs-lookup"><span data-stu-id="3d6e7-114">No code is implemented if the resource is a structured document.</span></span>

