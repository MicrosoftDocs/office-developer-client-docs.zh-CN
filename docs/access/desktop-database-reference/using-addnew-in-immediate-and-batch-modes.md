---
title: 在即时模式和批模式下使用 AddNew
TOCTitle: Using AddNew in Immediate and Batch Modes
ms:assetid: 1dc32284-9514-083d-ce56-58abbafa7bb7
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248970(v=office.15)
ms:contentKeyID: 48543602
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 929c01032924182d8db1bd5b06b573fb5d0171ae
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28701576"
---
# <a name="using-addnew-in-immediate-and-batch-modes"></a><span data-ttu-id="d17c7-102">在即时和批模式下使用 AddNew</span><span class="sxs-lookup"><span data-stu-id="d17c7-102">Using AddNew in Immediate and Batch modes</span></span>


<span data-ttu-id="d17c7-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="d17c7-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="d17c7-104">**AddNew**方法的行为取决于**Recordset**对象以及是否传递*FieldList*和*Values*参数的更新模式。</span><span class="sxs-lookup"><span data-stu-id="d17c7-104">The behavior of the **AddNew** method depends on the updating mode of the **Recordset** object and whether you pass the *FieldList* and *Values* arguments.</span></span>

<span data-ttu-id="d17c7-p101">在即时更新模式（在此模式中，只要调用 **Update** 方法，提供程序就会将更改写入基础数据源）中，不使用参数调用 **AddNew** 方法会将 **EditMode** 属性设置为 **adEditAdd**。提供程序在本地缓存所有字段值的更改。调用 **Update** 方法会将新记录张贴到数据库并将 **EditMode** 属性重新设置为 **adEditNone**。如果传递 *FieldList* 和 *Values* 参数，ADO 立即将新记录张贴到数据库（不再需要 **Update** 调用）；而 **EditMode** 属性值不会改变 (**adEditNone**)。</span><span class="sxs-lookup"><span data-stu-id="d17c7-p101">In immediate update mode (in which the provider writes changes to the underlying data source once you call the **Update** method), calling the **AddNew** method without arguments sets the **EditMode** property to **adEditAdd.** The provider caches any field value changes locally. Calling the **Update** method posts the new record to the database and resets the **EditMode** property to **adEditNone**. If you pass the *FieldList* and *Values* arguments, ADO immediately posts the new record to the database (no **Update** call is necessary); the **EditMode** property value does not change (**adEditNone**).</span></span>

<span data-ttu-id="d17c7-109">在批更新模式中，调用不带参数的 **AddNew** 方法会将 **EditMode** 属性设置为 **adEditAdd** 。</span><span class="sxs-lookup"><span data-stu-id="d17c7-109">In batch update mode, calling the **AddNew** method without arguments sets the **EditMode** property to **adEditAdd**.</span></span> <span data-ttu-id="d17c7-110">提供程序在本地缓存所有字段值的更改。</span><span class="sxs-lookup"><span data-stu-id="d17c7-110">The provider caches any field value changes locally.</span></span> <span data-ttu-id="d17c7-111">调用 **Update** 方法会将新记录添加到当前 **Recordset** 并将 **EditMode** 属性重新设置为 **adEditNone** ，但是在调用 **UpdateBatch** 方法之前，提供程序不会将更改张贴到基础数据库中。</span><span class="sxs-lookup"><span data-stu-id="d17c7-111">Calling the **Update** method adds the new record to the current **Recordset** and resets the **EditMode** property to **adEditNone**, but the provider does not post the changes to the underlying database until you call the **UpdateBatch** method.</span></span> <span data-ttu-id="d17c7-112">如果传递*FieldList*和*Values*参数，ADO 将新记录发送到用于存储缓存; 中的提供程序您需要调用**UpdateBatch**方法发布到基础数据库的新记录。</span><span class="sxs-lookup"><span data-stu-id="d17c7-112">If you pass the *FieldList* and *Values* arguments, ADO sends the new record to the provider for storage in a cache; you need to call the **UpdateBatch** method to post the new record to the underlying database.</span></span> <span data-ttu-id="d17c7-113">有关 **Update** 和 **UpdateBatch** 的详细信息，请参阅 [第 5 章：更新和持久化数据](chapter-5-updating-and-persisting-data.md)。</span><span class="sxs-lookup"><span data-stu-id="d17c7-113">For more information about **Update** and **UpdateBatch**, see [Chapter 5: Updating and Persisting Data](chapter-5-updating-and-persisting-data.md).</span></span>

