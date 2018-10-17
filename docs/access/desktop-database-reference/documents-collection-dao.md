---
title: Documents Collection (DAO)
TOCTitle: Documents Collection
ms:assetid: ae2fef58-34e7-eea6-ca51-d3903432c7f5
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821742(v=office.15)
ms:contentKeyID: 48547063
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 92a9dc96b438a55401df95a63ea47b85d96b0f83
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468840"
---
# <a name="documents-collection-dao"></a><span data-ttu-id="3ae5a-102">Documents Collection (DAO)</span><span class="sxs-lookup"><span data-stu-id="3ae5a-102">Documents Collection (DAO)</span></span>


<span data-ttu-id="3ae5a-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="3ae5a-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="3ae5a-104">**Documents** 集合包含特定类型对象的所有 **Document** 对象（仅适用于 Microsoft Access 数据库引擎数据库）。</span><span class="sxs-lookup"><span data-stu-id="3ae5a-104">A **Documents** collection contains all of the **Document** objects for a specific type of object (Microsoft Access database engine databases only).</span></span>

## <a name="remarks"></a><span data-ttu-id="3ae5a-105">注解</span><span class="sxs-lookup"><span data-stu-id="3ae5a-105">Remarks</span></span>

<span data-ttu-id="3ae5a-106">每个 **Container** 对象具有一个 **Documents** 集合，该集合包含对 **Container** 所指定的内置对象类型的实例进行描述的 **Document** 对象。</span><span class="sxs-lookup"><span data-stu-id="3ae5a-106">Each **Container** object has a **Documents** collection containing **Document** objects that describe instances of built-in objects of the type specified by the **Container**.</span></span>

<span data-ttu-id="3ae5a-107">若要按照序号或 **Name** 属性设置来引用集合中的 **Document** 对象，可以使用下列任何一种语法形式：</span><span class="sxs-lookup"><span data-stu-id="3ae5a-107">To refer to a **Document** object in a collection by its ordinal number or by its **Name** property setting, use any of the following syntax forms:</span></span>

  - <span data-ttu-id="3ae5a-108">**Documents**(0)</span><span class="sxs-lookup"><span data-stu-id="3ae5a-108">**Documents**(0)</span></span>

  - <span data-ttu-id="3ae5a-109">**文档**（"*name*"）</span><span class="sxs-lookup"><span data-stu-id="3ae5a-109">**Documents**("*name*")</span></span>

  - <span data-ttu-id="3ae5a-110">**文档**\!\[*名称*\]</span><span class="sxs-lookup"><span data-stu-id="3ae5a-110">**Documents**\!\[*name*\]</span></span>

## <a name="example"></a><span data-ttu-id="3ae5a-111">示例</span><span class="sxs-lookup"><span data-stu-id="3ae5a-111">Example</span></span>

<span data-ttu-id="3ae5a-112">以下示例枚举 Tables 容器的 **Documents** 集合，然后枚举该集合中第一个 **Document** 对象的 **Properties** 集合。</span><span class="sxs-lookup"><span data-stu-id="3ae5a-112">This example enumerates the **Documents** collection of the Tables container, and then enumerates the **Properties** collection of the first **Document** object in the collection.</span></span>

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
