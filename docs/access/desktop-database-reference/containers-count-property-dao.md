---
title: "\"容器\" 属性 (DAO)"
TOCTitle: Count Property
ms:assetid: 3b0bf865-a4d5-82bb-c1a9-9957f110db4c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192657(v=office.15)
ms:contentKeyID: 48544276
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 7553b0e7d64e059dfeed50f158f21f48455976d7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295588"
---
# <a name="containerscount-property-dao"></a><span data-ttu-id="c3f17-102">"容器" 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="c3f17-102">Containers.Count property (DAO)</span></span>


<span data-ttu-id="c3f17-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="c3f17-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="c3f17-104">返回 **[Connections](connection-object-dao.md)** 集合中的 **[Connection](connections-collection-dao.md)** 对象数。</span><span class="sxs-lookup"><span data-stu-id="c3f17-104">Returns the number of **[Connection](connection-object-dao.md)** objects in the **[Connections](connections-collection-dao.md)** collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="c3f17-105">语法</span><span class="sxs-lookup"><span data-stu-id="c3f17-105">Syntax</span></span>

<span data-ttu-id="c3f17-106">*表达式*。计数</span><span class="sxs-lookup"><span data-stu-id="c3f17-106">*expression* .Count</span></span>

<span data-ttu-id="c3f17-107">*表达式*一个代表**Connections**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="c3f17-107">*expression* A variable that represents a **Connections** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="c3f17-108">注解</span><span class="sxs-lookup"><span data-stu-id="c3f17-108">Remarks</span></span>

<span data-ttu-id="c3f17-p101">由于集合的成员由 0 开始，因此应始终将循环编写为从第 0 个成员开始，并在 **Count** 属性的值减 1 处结束。如果需要在集合的成员中循环且不检查 **Count** 属性，可以使用 **For Each...Next** 命令。</span><span class="sxs-lookup"><span data-stu-id="c3f17-p101">Because members of a collection begin with 0, you should always code loops starting with the 0 member and ending with the value of the **Count** property minus 1. If you want to loop through the members of a collection without checking the **Count** property, you can use a **For Each...Next** command.</span></span>

<span data-ttu-id="c3f17-p102">**Count** 属性设置从不为 Null。如果其值为 0，则表示集合中没有对象。</span><span class="sxs-lookup"><span data-stu-id="c3f17-p102">The **Count** property setting is never Null. If its value is 0, there are no objects in the collection.</span></span>

