---
title: Workspaces.Count 属性 (DAO)
TOCTitle: Count Property
ms:assetid: bc7c5a11-13d3-27bd-1be4-5d069e888ac2
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822719(v=office.15)
ms:contentKeyID: 48547414
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 692240130d0a5aa32899b94a18302721da01d44d
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28709647"
---
# <a name="workspacescount-property-dao"></a><span data-ttu-id="f725b-102">Workspaces.Count 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="f725b-102">Workspaces.Count property (DAO)</span></span>


<span data-ttu-id="f725b-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="f725b-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="f725b-p101">返回指定集合中的对象数。只读。</span><span class="sxs-lookup"><span data-stu-id="f725b-p101">Returns the number of objects in the specified collection. Read-only.</span></span>

## <a name="syntax"></a><span data-ttu-id="f725b-106">语法</span><span class="sxs-lookup"><span data-stu-id="f725b-106">Syntax</span></span>

<span data-ttu-id="f725b-107">*表达式*。计数</span><span class="sxs-lookup"><span data-stu-id="f725b-107">*expression* .Count</span></span>

<span data-ttu-id="f725b-108">*表达式*一个代表**Workspaces**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="f725b-108">*expression* A variable that represents a **Workspaces** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="f725b-109">注解</span><span class="sxs-lookup"><span data-stu-id="f725b-109">Remarks</span></span>

<span data-ttu-id="f725b-p102">由于集合的成员是从 0 开始编号的，因此应始终将循环编写为从第 0 个成员开始，而在 **Count** 属性的值减 1 处结束。如果想要在不检查 **Count** 属性的情况下遍历集合成员，则可以使用 **For Each...Next** 命令。</span><span class="sxs-lookup"><span data-stu-id="f725b-p102">Because members of a collection begin with 0, you should always code loops starting with the 0 member and ending with the value of the **Count** property minus 1. If you want to loop through the members of a collection without checking the **Count** property, you can use a **For Each...Next** command.</span></span>

<span data-ttu-id="f725b-p103">**Count** 属性设置从不为 Null。如果其值为 0，则表示集合中没有对象。</span><span class="sxs-lookup"><span data-stu-id="f725b-p103">The **Count** property setting is never Null. If its value is 0, there are no objects in the collection.</span></span>

