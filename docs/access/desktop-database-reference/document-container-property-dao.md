---
title: Document.Container Property (DAO)
TOCTitle: Container Property
ms:assetid: aa1ace1d-f0b8-e0b0-20b6-d3e296254c51
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821451(v=office.15)
ms:contentKeyID: 48546940
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053320
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 1b943c9668ce03df029eb4a27d4ed594d00300de
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467265"
---
# <a name="documentcontainer-property-dao"></a><span data-ttu-id="91f6c-102">Document.Container Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="91f6c-102">Document.Container Property (DAO)</span></span>


<span data-ttu-id="91f6c-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="91f6c-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="91f6c-p101">返回 [Document](container-object-dao.md) 对象所属的 \*\*\*\*Container\*\*\*\* 对象的名称（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="91f6c-p101">Returns the name of the **[Container](container-object-dao.md)** object to which a **Document** object belongs (Microsoft Access workspaces only). .</span></span>

## <a name="syntax"></a><span data-ttu-id="91f6c-106">语法</span><span class="sxs-lookup"><span data-stu-id="91f6c-106">Syntax</span></span>

<span data-ttu-id="91f6c-107">*表达式*。容器</span><span class="sxs-lookup"><span data-stu-id="91f6c-107">*expression* .Container</span></span>

<span data-ttu-id="91f6c-108">*表达式*一个代表**Document**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="91f6c-108">*expression* A variable that represents a **Document** object.</span></span>

## <a name="example"></a><span data-ttu-id="91f6c-109">示例</span><span class="sxs-lookup"><span data-stu-id="91f6c-109">Example</span></span>

<span data-ttu-id="91f6c-110">以下示例显示各种 **Document** 对象的 **Container** 属性。</span><span class="sxs-lookup"><span data-stu-id="91f6c-110">This example displays the **Container** property for a variety of **Document** objects.</span></span>

```vb 
Sub ContainerPropertyX() 
 
 Dim dbsNorthwind As Database 
 Dim ctrLoop As Container 
 
 Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
 
 ' Display the container name for the first Document 
 ' object in each Container object's Documents collection. 
 For Each ctrLoop In dbsNorthwind.Containers 
 Debug.Print "Document: " & ctrLoop.Documents(0).Name 
 Debug.Print " Container = " & _ 
 ctrLoop.Documents(0).Container 
 Next ctrLoop 
 
 dbsNorthwind.Close 
 
End Sub 
 
```

