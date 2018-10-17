---
title: 编辑现有记录
TOCTitle: Editing Existing Records
ms:assetid: 86b961e0-e0a5-85a2-1138-7ab2e696ec11
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249585(v=office.15)
ms:contentKeyID: 48546089
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 274cd7667506159e2309fffb3596781c004f7006
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467402"
---
# <a name="editing-existing-records"></a><span data-ttu-id="61502-102">编辑现有记录</span><span class="sxs-lookup"><span data-stu-id="61502-102">Editing Existing Records</span></span>


<span data-ttu-id="61502-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="61502-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="61502-p101">若要编辑现有记录，请移动到希望编辑的行，并更改想更改的字段的 **Value** 属性。有关 **Field** 对象的 **Value** 属性的详细信息，请参阅 [第 3 章：检查数据](chapter-3-examining-data.md)。取决于游标类型，需要使用 **Update** 或 **UpdateBatch** 将更改发送回数据源。有关详细信息，请参阅 [第 5 章：更新和持久化数据](chapter-5-updating-and-persisting-data.md)。</span><span class="sxs-lookup"><span data-stu-id="61502-p101">To edit existing records, move to the row you want to edit and change the **Value** property of the fields you want to change. For more information about the **Field** object's **Value** property, see [Chapter 3: Examining Data](chapter-3-examining-data.md). Depending on your cursor type, you will use **Update** or **UpdateBatch** to send changes back to the data source. For more information, see [Chapter 5: Updating and Persisting Data](chapter-5-updating-and-persisting-data.md).</span></span>

<span data-ttu-id="61502-p102">通常，更有效的方式是对命令对象使用存储过程来执行更新，同时执行其他操作，这是因为存储过程不需要创建游标。有关游标的详细信息，请参阅[第 8 章：了解游标和锁定](chapter-8-understanding-cursors-and-locks.md)。</span><span class="sxs-lookup"><span data-stu-id="61502-p102">It is usually more efficient to use a stored procedure with a command object to perform updates, as well as to perform other operations, because a stored procedure does not require the creation of a cursor. For more information about cursors, see [Chapter 8: Understanding Cursors and Locks](chapter-8-understanding-cursors-and-locks.md).</span></span>
