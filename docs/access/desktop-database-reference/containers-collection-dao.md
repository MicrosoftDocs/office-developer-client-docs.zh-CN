---
title: Containers Collection (DAO)
TOCTitle: Containers Object
ms:assetid: 4996ee39-ea13-f560-3069-dd7bc6022119
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193464(v=office.15)
ms:contentKeyID: 48544642
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 5b87aaf5eec856b17372627b0b298e36fa322ea5
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468855"
---
# <a name="containers-collection-dao"></a><span data-ttu-id="cdee4-102">Containers Collection (DAO)</span><span class="sxs-lookup"><span data-stu-id="cdee4-102">Containers Collection (DAO)</span></span>

<span data-ttu-id="cdee4-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="cdee4-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="cdee4-104">**Containers**集合包含所有数据库中定义的**容器**对象。</span><span class="sxs-lookup"><span data-stu-id="cdee4-104">A **Containers** collection contains all of the **Container** objects that are defined in a database.</span></span>

## <a name="remarks"></a><span data-ttu-id="cdee4-105">注解</span><span class="sxs-lookup"><span data-stu-id="cdee4-105">Remarks</span></span>

<span data-ttu-id="cdee4-106">每个 **Database** 对象都具有一个由内置 **Container** 对象组成的 **Containers** 集合。</span><span class="sxs-lookup"><span data-stu-id="cdee4-106">Each **Database** object has a **Containers** collection consisting of built-in **Container** objects.</span></span> <span data-ttu-id="cdee4-107">这些 **Container** 对象中的一部分是由 Microsoft Access 数据库引擎定义的，而其余部分可能是由其他应用程序定义的。</span><span class="sxs-lookup"><span data-stu-id="cdee4-107">Some of these **Container** objects are defined by the Microsoft Access database engine while others may be defined by other applications.</span></span>

## <a name="example"></a><span data-ttu-id="cdee4-108">示例</span><span class="sxs-lookup"><span data-stu-id="cdee4-108">Example</span></span>

<span data-ttu-id="cdee4-109">以下示例枚举 Northwind 数据库的 **Containers** 集合以及该集合中每个 **Container** 对象的 **Properties** 集合。</span><span class="sxs-lookup"><span data-stu-id="cdee4-109">This example enumerates the **Containers** collection of the Northwind database and the **Properties** collection of each **Container** object in the collection.</span></span>

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
                Debug.Print "  " & prpLoop.Name _
                   & " = " prpLoop
             Next prpLoop
    
          Next ctrLoop
    
          .Close
       End With
    
    End Sub
```
