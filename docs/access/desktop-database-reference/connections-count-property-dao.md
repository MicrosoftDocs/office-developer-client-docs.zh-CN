---
title: Connections.Count Property (DAO)
TOCTitle: Count Property
ms:assetid: 9b2f0aaa-785a-7fe7-15c3-aea37fdacd12
ms:mtpsurl: https://msdn.microsoft.com/library/Ff198023(v=office.15)
ms:contentKeyID: 48546563
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c4f341abfea455acdc96a2883d0f4dee3bd2a5fe
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466265"
---
# <a name="connectionscount-property-dao"></a><span data-ttu-id="bb6dd-102">Connections.Count Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="bb6dd-102">Connections.Count Property (DAO)</span></span>


<span data-ttu-id="bb6dd-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="bb6dd-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="bb6dd-104">返回 **[Connections](connection-object-dao.md)** 集合中的 **[Connection](connections-collection-dao.md)** 对象数。</span><span class="sxs-lookup"><span data-stu-id="bb6dd-104">Returns the number of **[Connection](connection-object-dao.md)** objects in the **[Connections](connections-collection-dao.md)** collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="bb6dd-105">语法</span><span class="sxs-lookup"><span data-stu-id="bb6dd-105">Syntax</span></span>

<span data-ttu-id="bb6dd-106">*表达式*。计数</span><span class="sxs-lookup"><span data-stu-id="bb6dd-106">*expression* .Count</span></span>

<span data-ttu-id="bb6dd-107">*表达式*一个代表**Connections**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="bb6dd-107">*expression* A variable that represents a **Connections** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="bb6dd-108">注解</span><span class="sxs-lookup"><span data-stu-id="bb6dd-108">Remarks</span></span>

<span data-ttu-id="bb6dd-p101">由于集合的成员是从 0 开始编号的，因此应始终将循环编写为从第 0 个成员开始，而在 **Count** 属性的值减 1 处结束。如果想要在不检查 **Count** 属性的情况下遍历集合成员，则可以使用 **For Each...Next** 命令。</span><span class="sxs-lookup"><span data-stu-id="bb6dd-p101">Because members of a collection begin with 0, you should always code loops starting with the 0 member and ending with the value of the **Count** property minus 1. If you want to loop through the members of a collection without checking the **Count** property, you can use a **For Each...Next** command.</span></span>

<span data-ttu-id="bb6dd-p102">**Count** 属性设置从不为 Null。如果其值为 0，则表示集合中没有对象。</span><span class="sxs-lookup"><span data-stu-id="bb6dd-p102">The **Count** property setting is never Null. If its value is 0, there are no objects in the collection.</span></span>

