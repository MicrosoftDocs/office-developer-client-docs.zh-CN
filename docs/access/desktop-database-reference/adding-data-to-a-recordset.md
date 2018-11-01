---
title: 向记录集添加数据
TOCTitle: Adding Data to a Recordset
ms:assetid: a3d121a8-f52f-66cd-8849-c3a75aeb276a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249761(v=office.15)
ms:contentKeyID: 48546797
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b013ab0b05242b4928f7a9b9d974ef98ca6103d0
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25885022"
---
# <a name="adding-data-to-a-recordset"></a><span data-ttu-id="9b9a8-102">将数据添加到记录集</span><span class="sxs-lookup"><span data-stu-id="9b9a8-102">Adding Data to a Recordset</span></span>


<span data-ttu-id="9b9a8-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="9b9a8-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="9b9a8-p101">**Recordset** 可能是最常使用的 ADO 对象。在 ADO 中，最好将 **Recordset** 看作从数据源得到的结果集和与其关联的游标行为的组合。因此，可以将数据放在 **Recordset** 中，然后使用 **Recordset** 的方法和属性在数据行中导航，查看行中的值以及操作结果集。</span><span class="sxs-lookup"><span data-stu-id="9b9a8-p101">The **Recordset** is probably the most used of the ADO objects. In ADO a **Recordset** is best thought of as the combination of a result set from a data source and its associated cursor behaviors. Thus, you can put data into a **Recordset** and then use the **Recordset** methods and properties to navigate through the rows of data, view the values in the rows, and otherwise manipulate the result set.</span></span>

<span data-ttu-id="9b9a8-p102">这一节将重点介绍如何向 **Recordset** 添加数据。有关在数据中导航或更新数据的信息，请参阅 [第 4 章：编辑数据](chapter-4-editing-data.md)和[第 5 章：更新和持久化数据](chapter-5-updating-and-persisting-data.md)。完全不需要 **Command** 对象的高级功能，就能将结果设置添加到 **Recordset** 。通常，可以通过设置 **Recordset** 的 **Source** 属性或将命令字符串传递到 **Recordset** 对象的 **Open** 方法来执行命令。</span><span class="sxs-lookup"><span data-stu-id="9b9a8-p102">This section will focus on adding data to the **Recordset**. For information about navigating through the data or updating the data, see [Chapter 4: Editing Data](chapter-4-editing-data.md) and [Chapter 5: Updating and Persisting Data](chapter-5-updating-and-persisting-data.md). You do not always need the advanced capabilities of a **Command** object to add your result set to a **Recordset**. Often, you can execute your command by setting the **Source** property on the **Recordset** or passing a command string to the **Recordset** object **Open** method.</span></span>

<span data-ttu-id="9b9a8-p103">可以用多种方式将数据源的数据添加到 **Recordset** ，所使用的技术取决于应用程序的需要和提供程序的功能。</span><span class="sxs-lookup"><span data-stu-id="9b9a8-p103">There are a variety of ways to add data from your data source to a **Recordset**. The technique you use depends on the needs of your application and the capabilities of your provider.</span></span>

