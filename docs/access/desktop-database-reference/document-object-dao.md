---
title: Document 对象 (DAO)
TOCTitle: Document Object
ms:assetid: b51d4545-b157-4c7c-fdbe-16a25afffdb3
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822082(v=office.15)
ms:contentKeyID: 48547247
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 0f82ace31a991a6700417d4c0d66bf775fcb7b26
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32293775"
---
# <a name="document-object-dao"></a><span data-ttu-id="0393e-102">Document 对象 (DAO)</span><span class="sxs-lookup"><span data-stu-id="0393e-102">Document object (DAO)</span></span>

<span data-ttu-id="0393e-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="0393e-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="0393e-p101">**Document** 对象包含有关对象实例的信息。该对象可以是数据库、保存的表、查询或关系（仅适用于 Microsoft Access 数据库引擎数据库）。</span><span class="sxs-lookup"><span data-stu-id="0393e-p101">A **Document** object includes information about one instance of an object. The object can be a database, saved table, query, or relationship (Microsoft Access database engine databases only).</span></span>

## <a name="remarks"></a><span data-ttu-id="0393e-106">注解</span><span class="sxs-lookup"><span data-stu-id="0393e-106">Remarks</span></span>

<span data-ttu-id="0393e-p102">每个 **Container** 对象具有一个 **Documents** 集合，该集合包含对 **Container** 所指定的内置对象类型的实例进行描述的 **Document** 对象。下表列出了每个 **Document** 描述的对象的类型、其 **Container** 对象的名称以及 **Document** 包含的信息类型。</span><span class="sxs-lookup"><span data-stu-id="0393e-p102">Each **Container** object has a **Documents** collection containing **Document** objects that describe instances of built-in objects of the type specified by the **Container**. The following table lists the type of object each **Document** describes, the name of its **Container** object, and what type of information **Document** contains.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="0393e-109">Document</span><span class="sxs-lookup"><span data-stu-id="0393e-109">Document</span></span></p></th>
<th><p><span data-ttu-id="0393e-110">Container</span><span class="sxs-lookup"><span data-stu-id="0393e-110">Container</span></span></p></th>
<th><p><span data-ttu-id="0393e-111">包含何类信息</span><span class="sxs-lookup"><span data-stu-id="0393e-111">Contains information about</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0393e-112">数据库</span><span class="sxs-lookup"><span data-stu-id="0393e-112">Database</span></span></p></td>
<td><p><span data-ttu-id="0393e-113">数据库</span><span class="sxs-lookup"><span data-stu-id="0393e-113">Databases</span></span></p></td>
<td><p><span data-ttu-id="0393e-114">保存的数据库</span><span class="sxs-lookup"><span data-stu-id="0393e-114">Saved database</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0393e-115">Table 或 Query</span><span class="sxs-lookup"><span data-stu-id="0393e-115">Table or query</span></span></p></td>
<td><p><span data-ttu-id="0393e-116">Tables</span><span class="sxs-lookup"><span data-stu-id="0393e-116">Tables</span></span></p></td>
<td><p><span data-ttu-id="0393e-117">保存的表或查询</span><span class="sxs-lookup"><span data-stu-id="0393e-117">Saved table or query</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0393e-118">关系</span><span class="sxs-lookup"><span data-stu-id="0393e-118">Relationship</span></span></p></td>
<td><p><span data-ttu-id="0393e-119">Relations</span><span class="sxs-lookup"><span data-stu-id="0393e-119">Relations</span></span></p></td>
<td><p><span data-ttu-id="0393e-120">保存的关系</span><span class="sxs-lookup"><span data-stu-id="0393e-120">Saved relationship</span></span></p></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="0393e-p103">[!注释] 不要将上表列出的 **Container** 对象与带有相同名称的集合相混淆。Databases **Container** 对象引用所有保存的数据库对象，但是 **Databases** 集合只引用在特定工作区中打开的数据库对象。</span><span class="sxs-lookup"><span data-stu-id="0393e-p103">Don't confuse the **Container** objects listed in the preceding table with the collections of the same name. The Databases **Container** object refers to all saved database objects, but the **Databases** collection refers only to database objects that are open in a particular workspace.</span></span>

<span data-ttu-id="0393e-123">对于 **Document** 对象，您可以进行下列操作：</span><span class="sxs-lookup"><span data-stu-id="0393e-123">With a **Document** object, you can:</span></span>

- <span data-ttu-id="0393e-124">使用 **Name** 属性返回在创建某个对象时用户或 Microsoft Access 数据库引擎为该对象指定的名称。</span><span class="sxs-lookup"><span data-stu-id="0393e-124">Use the **Name** property to return the name that a user or the Microsoft Access database engine gave to the object when it was created.</span></span>

- <span data-ttu-id="0393e-125">使用 **Container** 属性返回包含 **Document** 对象的 **Container** 对象的名称。</span><span class="sxs-lookup"><span data-stu-id="0393e-125">Use the **Container** property to return the name of the **Container** object that contains the **Document** object.</span></span>

- <span data-ttu-id="0393e-p104">使用 **Owner** 属性设置或返回对象的所有者。要设置 **Owner** 属性，必须对 **Document** 对象具有写入权限，并且必须将属性设置为现有的 **User** 或 **Group** 对象的名称。</span><span class="sxs-lookup"><span data-stu-id="0393e-p104">Use the **Owner** property to set or return the owner of the object. To set the **Owner** property, you must have write permission for the **Document** object, and you must set the property to the name of an existing **User** or **Group** object.</span></span>

- <span data-ttu-id="0393e-p105">使用 **UserName** 或 **Permissions** 属性设置或返回对象的用户或组的访问权限。要设置这些属性，必须具有对 **Document** 对象的写入权限，并且必须将 **UserName** 属性设置为现有的 **User** 或 **Group** 对象的名称。</span><span class="sxs-lookup"><span data-stu-id="0393e-p105">Use the **UserName** or **Permissions** properties to set or return the access permissions of a user or group for the object. To set these properties, you must have write permission for the **Document** object, and you must set the **UserName** property to the name of an existing **User** or **Group** object.</span></span>

- <span data-ttu-id="0393e-130">使用 **DateCreated** 和 **LastUpdated** 属性返回创建或上次修改 **Document** 对象时的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="0393e-130">Use the **DateCreated** and **LastUpdated** properties to return the date and time when the **Document** object was created and last modified.</span></span>

<span data-ttu-id="0393e-p106">因为 **Document** 对象对应于现有对象，所以不能创建新的 **Document** 对象，或删除现有的此类对象。若要按照序号或 **Name** 属性设置来引用集合中的 **Document** 对象，可以使用下列任何一种语法形式：</span><span class="sxs-lookup"><span data-stu-id="0393e-p106">Because a **Document** object corresponds to an existing object, you can't create new **Document** objects or delete existing ones. To refer to a **Document** object in a collection by its ordinal number or by its **Name** property setting, use any of the following syntax forms:</span></span>

- <span data-ttu-id="0393e-133">**Documents**(0)</span><span class="sxs-lookup"><span data-stu-id="0393e-133">**Documents**(0)</span></span>

- <span data-ttu-id="0393e-134">**文档**("*名称*")</span><span class="sxs-lookup"><span data-stu-id="0393e-134">**Documents**("*name*")</span></span>

- <span data-ttu-id="0393e-135">\*\*\*\*\!文档\[*名称*\]</span><span class="sxs-lookup"><span data-stu-id="0393e-135">**Documents**\!\[*name*\]</span></span>

## <a name="example"></a><span data-ttu-id="0393e-136">示例</span><span class="sxs-lookup"><span data-stu-id="0393e-136">Example</span></span>

<span data-ttu-id="0393e-137">以下示例枚举 Tables 容器的 **Documents** 集合，然后枚举该集合中第一个 **Document** 对象的 **Properties** 集合。</span><span class="sxs-lookup"><span data-stu-id="0393e-137">This example enumerates the **Documents** collection of the Tables container, and then enumerates the **Properties** collection of the first **Document** object in the collection.</span></span>

```vb 
Sub DocumentX() 
 
 Dim dbsNorthwind As Database 
 Dim docLoop As Document 
 Dim prpLoop As Property 
 
 Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
 
 With dbsNorthwind.Containers!Tables 
 Debug.Print "Documents in " & .Name & " container" 
 ' Enumerate the Documents collection of the Tables 
 ' container. 
 For Each docLoop In .Documents 
 Debug.Print " " & docLoop.Name 
 Next docLoop 
 With .Documents(0) 
 ' Enumerate the Properties collection of the first. 
 ' Document object of the Tables container. 
 Debug.Print "Properties of " & .Name & " document" 
 On Error Resume Next 
 For Each prpLoop In .Properties 
 Debug.Print " " & prpLoop.Name & " = " & _ 
 prpLoop 
 Next prpLoop 
 On Error GoTo 0 
 End With 
 End With 
 
 dbsNorthwind.Close 
 
End Sub 
 
```

<br/>

<span data-ttu-id="0393e-138">以下示例使用 **Owner** 和 **SystemDB** 属性显示多种 **Document** 对象的所有者。</span><span class="sxs-lookup"><span data-stu-id="0393e-138">This example uses the **Owner** and **SystemDB** properties to show the owners of a variety of **Document** objects.</span></span>

```vb 
Sub OwnerX() 
 
 ' Ensure that the Microsoft Access workgroup file is 
 ' available. 
 DBEngine.SystemDB = "system.mdw" 
 
 Dim dbsNorthwind As Database 
 Dim ctrLoop As Container 
 
 Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
 
 With dbsNorthwind 
 Debug.Print "Document owners:" 
 ' Enumerate Containers collection and show the owner 
 ' of the first Document in each container's Documents 
 ' collection. 
 For Each ctrLoop In .Containers 
 With ctrLoop 
 Debug.Print " [" & .Documents(0).Name & _ 
 "] in [" & .Name & _ 
 "] container owned by [" & _ 
 .Documents(0).Owner & "]" 
 End With 
 Next ctrLoop 
 
 .Close 
 End With 
 
End Sub 
 
```

