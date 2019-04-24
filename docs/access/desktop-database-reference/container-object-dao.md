---
title: 容器对象 (DAO)
TOCTitle: Container Object
ms:assetid: 22e487cd-e966-fe68-fff3-c680b460cbeb
ms:mtpsurl: https://msdn.microsoft.com/library/Ff191764(v=office.15)
ms:contentKeyID: 48543720
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: c9ebbeae35387f4fd59c39d4c20df6033edb06b0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295630"
---
# <a name="container-object-dao"></a><span data-ttu-id="f7e41-102">容器对象 (DAO)</span><span class="sxs-lookup"><span data-stu-id="f7e41-102">Container object (DAO)</span></span>

<span data-ttu-id="f7e41-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="f7e41-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="f7e41-104">**Container** 对象可将相似类型的 **Document** 对象组合在一起。</span><span class="sxs-lookup"><span data-stu-id="f7e41-104">A **Container** object groups similar types of **Document** objects together.</span></span>

## <a name="remarks"></a><span data-ttu-id="f7e41-105">注解</span><span class="sxs-lookup"><span data-stu-id="f7e41-105">Remarks</span></span>

<span data-ttu-id="f7e41-p101">每个 **Database** 对象都具有一个由内置 **Container** 对象组成的 **Containers** 集合。应用程序可以定义其自身的文档类型和相应的容器（仅适用于 Microsoft Access 数据库引擎数据库）；但是，不一定总能通过 DAO 支持这些对象。</span><span class="sxs-lookup"><span data-stu-id="f7e41-p101">Each **Database** object has a **Containers** collection consisting of built-in **Container** objects. Applications can define their own document types and corresponding containers (Microsoft Access database engine databases only); however, these objects may not always be supported through DAO.</span></span>

<span data-ttu-id="f7e41-p102">这些 **Container** 对象中的一部分是由 Microsoft Access 数据库引擎定义的，而其余部分可能是由其他应用程序定义的。下表列出由 Microsoft Access 数据库引擎定义的每个 **Container** 对象的名称，以及该名称包含的信息类型。</span><span class="sxs-lookup"><span data-stu-id="f7e41-p102">Some of these **Container** objects are defined by the Microsoft Access database engine while others may be defined by other applications. The following table lists the name of each **Container** object defined by the Microsoft Access database engine and what type of information it contains.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="f7e41-110">容器名称</span><span class="sxs-lookup"><span data-stu-id="f7e41-110">Container name</span></span></p></th>
<th><p><span data-ttu-id="f7e41-111">包含何类信息</span><span class="sxs-lookup"><span data-stu-id="f7e41-111">Contains information about</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f7e41-112">Databases</span><span class="sxs-lookup"><span data-stu-id="f7e41-112">Databases</span></span></p></td>
<td><p><span data-ttu-id="f7e41-113">保存的数据库</span><span class="sxs-lookup"><span data-stu-id="f7e41-113">Saved databases</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7e41-114">Tables</span><span class="sxs-lookup"><span data-stu-id="f7e41-114">Tables</span></span></p></td>
<td><p><span data-ttu-id="f7e41-115">保存的表和查询</span><span class="sxs-lookup"><span data-stu-id="f7e41-115">Saved tables and queries</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7e41-116">Relations</span><span class="sxs-lookup"><span data-stu-id="f7e41-116">Relations</span></span></p></td>
<td><p><span data-ttu-id="f7e41-117">保存的关系</span><span class="sxs-lookup"><span data-stu-id="f7e41-117">Saved relationships</span></span></p></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="f7e41-p103">[!注释] 不要将上表列出的 **Container** 对象与带有相同名称的集合相混淆。Databases **Container** 对象引用所有保存的数据库对象，但是 **Databases** 集合只引用在特定工作区中打开的数据库对象。</span><span class="sxs-lookup"><span data-stu-id="f7e41-p103">Don't confuse the **Container** objects listed in the preceding table with the collections of the same name. The Databases **Container** object refers to all saved database objects, but the **Databases** collection refers only to database objects that are open in a particular workspace.</span></span>

<span data-ttu-id="f7e41-p104">每个 **Container** 对象具有一个 **Documents** 集合，该集合包含对 **Container** 所指定的内置对象类型的实例进行描述的 **Document** 对象。通常，可以将 **Container** 对象用作指向 **Document** 对象中的信息的中间链接。还可以使用 **Containers** 集合设置给定类型的所有 **Document** 对象的安全性。</span><span class="sxs-lookup"><span data-stu-id="f7e41-p104">Each **Container** object has a **Documents** collection containing **Document** objects that describe instances of built-in objects of the type specified by the **Container**. You typically use a **Container** object as an intermediate link to the information in the **Document** object. You can also use the **Containers** collection to set security for all **Document** objects of a given type.</span></span>

<span data-ttu-id="f7e41-123">对于现有的 **Container** 对象，您可以进行下列操作：</span><span class="sxs-lookup"><span data-stu-id="f7e41-123">With an existing **Container** object, you can:</span></span>

- <span data-ttu-id="f7e41-124">使用 **Name** 属性返回 **Container** 对象的预定义名称。</span><span class="sxs-lookup"><span data-stu-id="f7e41-124">Use the **Name** property to return the predefined name of the **Container** object.</span></span>

- <span data-ttu-id="f7e41-p105">使用 **Owner** 属性设置或返回 **Container** 对象的所有者。要设置 **Owner** 属性，必须对 **Container** 对象具有写入权限，并且必须将属性设置为现有的 **User** 或 **Group** 对象的名称。</span><span class="sxs-lookup"><span data-stu-id="f7e41-p105">Use the **Owner** property to set or return the owner of the **Container** object. To set the **Owner** property, you must have write permission for the **Container** object, and you must set the property to the name of an existing **User** or **Group** object.</span></span>

- <span data-ttu-id="f7e41-127">使用 **Permissions** 和 **UserName** 属性设置对 **Container** 对象的访问权限；在 **Container** 对象的 **Documents** 集合中创建的任何 **Document** 对象将继承这些访问权限设置。</span><span class="sxs-lookup"><span data-stu-id="f7e41-127">Use the **Permissions** and **UserName** properties to set access permissions for the **Container** object; any **Document** object created in the **Documents** collection of a **Container** object inherits these access permission settings.</span></span>

<span data-ttu-id="f7e41-128">因为 **Container** 对象是内置，所以不能创建新的 **Container** 对象，或删除现有的此类对象。</span><span class="sxs-lookup"><span data-stu-id="f7e41-128">Because **Container** objects are built-in, you can't create new **Container** objects or delete existing ones.</span></span>

<span data-ttu-id="f7e41-129">若要按照序号或 **Name** 属性设置来引用集合中的 **Container** 对象，可以使用下列任何一种语法形式：</span><span class="sxs-lookup"><span data-stu-id="f7e41-129">To refer to a **Container** object in a collection by its ordinal number or by its **Name** property setting, use any of the following syntax forms:</span></span>

- <span data-ttu-id="f7e41-130">**容器**0</span><span class="sxs-lookup"><span data-stu-id="f7e41-130">**Containers**(0)</span></span>

- <span data-ttu-id="f7e41-131">**容器**("*名称*")</span><span class="sxs-lookup"><span data-stu-id="f7e41-131">**Containers**("*name*")</span></span>

- <span data-ttu-id="f7e41-132">\*\*\*\*\!容器\[*名称*\]</span><span class="sxs-lookup"><span data-stu-id="f7e41-132">**Containers**\!\[*name*\]</span></span>

## <a name="example"></a><span data-ttu-id="f7e41-133">示例</span><span class="sxs-lookup"><span data-stu-id="f7e41-133">Example</span></span>

<span data-ttu-id="f7e41-134">以下示例枚举 Northwind 数据库的 **Containers** 集合以及该集合中每个 **Container** 对象的 **Properties** 集合。</span><span class="sxs-lookup"><span data-stu-id="f7e41-134">This example enumerates the **Containers** collection of the Northwind database and the **Properties** collection of each **Container** object in the collection.</span></span>

```vb
    Sub ContainerObjectX() 
     
     Dim dbsNorthwind As Database 
     Dim ctrLoop As Container 
     Dim prpLoop As Property 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     
     With dbsNorthwind 
     
     ' Enumerate Containers collection. 
     For Each ctrLoop In .Containers 
     Debug.Print "Properties of " & ctrLoop.Name _ 
     & " container" 
     
     ' Enumerate Properties collection of each 
     ' Container object. 
     For Each prpLoop In ctrLoop.Properties 
     Debug.Print " " & prpLoop.Name _ 
     & " = " prpLoop 
     Next prpLoop 
     
     Next ctrLoop 
     
     .Close 
     End With 
     
    End Sub
```
