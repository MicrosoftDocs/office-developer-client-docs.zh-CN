---
title: 确定什么受支持
TOCTitle: Determining what is supported
ms:assetid: 47b44dc9-e0fd-f204-0c68-e0de9247ee2c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249221(v=office.15)
ms:contentKeyID: 48544602
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 3abef84f05ad279edba1fcc753f0b412a807a7b9
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28712692"
---
# <a name="determining-what-is-supported"></a><span data-ttu-id="7b818-102">确定什么受支持</span><span class="sxs-lookup"><span data-stu-id="7b818-102">Determining what is supported</span></span>

<span data-ttu-id="7b818-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="7b818-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="7b818-p101">**Supports** 方法用于确定指定的 **Recordset** 对象是否支持特定类型的功能。它的语法如下：</span><span class="sxs-lookup"><span data-stu-id="7b818-p101">The **Supports** method is used to determine whether a specified **Recordset** object supports a particular type of functionality. It has the following syntax:</span></span>

`boolean = recordset.Supports( CursorOptions )`

<span data-ttu-id="7b818-p102">**Supports** 返回布尔值，以指示提供程序是否支持 *CursorOptions* 参数所标识的所有功能。可以使用 **Supports** 方法来确定 **Recordset** 对象支持哪些类型的功能。如果 **Recordset** 对象支持其相应常量在 *CursorOptions* 中的功能，则 **Supports** 方法返回 **True**。否则，它返回 **False**。</span><span class="sxs-lookup"><span data-stu-id="7b818-p102">**Supports** returns a Boolean value that indicates whether all of the features identified by the *CursorOptions* argument are supported by the provider. You can use the **Supports** method to determine what types of functionality a **Recordset** object supports. If the **Recordset** object supports the features whose corresponding constants are in *CursorOptions*, the **Supports** method returns **True**. Otherwise, it returns **False**.</span></span>

<span data-ttu-id="7b818-p103">通过使用 **Supports** 方法，可以检查 **Recordset** 对象是否有添加新记录、使用书签、使用 **Find** 方法、使用滚动、使用 **Index** 属性和执行批更新等功能。有关常量及其含义的完整列表，请参阅 [CursorOptionEnum](cursoroptionenum.md)。</span><span class="sxs-lookup"><span data-stu-id="7b818-p103">Using the **Supports** method, you can check for the ability of the **Recordset** object to add new records, use bookmarks, use the **Find** method, use scrolling, use the **Index** property, and to perform batch updates. For a complete list of constants and their meanings, see [CursorOptionEnum](cursoroptionenum.md).</span></span>

<span data-ttu-id="7b818-p104">尽管对于给定功能 **Supports** 方法可能返回 **True** ，但并不能保证提供程序在所有环境下都能提供此功能。 **Supports** 方法只是返回在满足某些条件的情况下提供程序是否支持指定的功能。例如， **Supports** 方法可以指示 **Recordset** 对象支持更新，即使游标基于多表联接 - 其中的某些列是不可更新的。</span><span class="sxs-lookup"><span data-stu-id="7b818-p104">Although the **Supports** method may return **True** for a given functionality, it does not guarantee that the provider can make the feature available under all circumstances. The **Supports** method simply returns whether the provider can support the specified functionality, assuming certain conditions are met. For example, the **Supports** method may indicate that a **Recordset** object supports updates, even though the cursor is based on a multiple table join — some columns of which are not updateable.</span></span>

