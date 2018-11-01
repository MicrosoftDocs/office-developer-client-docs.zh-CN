---
title: Workspaces.Count Property (DAO)
TOCTitle: Count Property
ms:assetid: bc7c5a11-13d3-27bd-1be4-5d069e888ac2
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822719(v=office.15)
ms:contentKeyID: 48547414
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 0632556d7e62b426f462e17d732db323513afcec
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25888249"
---
# <a name="workspacescount-property-dao"></a><span data-ttu-id="16017-102">Workspaces.Count Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="16017-102">Workspaces.Count Property (DAO)</span></span>


<span data-ttu-id="16017-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="16017-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="16017-p101">返回指定集合中的对象数。只读。</span><span class="sxs-lookup"><span data-stu-id="16017-p101">Returns the number of objects in the specified collection. Read-only.</span></span>

## <a name="syntax"></a><span data-ttu-id="16017-106">语法</span><span class="sxs-lookup"><span data-stu-id="16017-106">Syntax</span></span>

<span data-ttu-id="16017-107">*表达式*。计数</span><span class="sxs-lookup"><span data-stu-id="16017-107">*expression* .Count</span></span>

<span data-ttu-id="16017-108">*表达式*一个代表**Workspaces**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="16017-108">*expression* A variable that represents a **Workspaces** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="16017-109">注解</span><span class="sxs-lookup"><span data-stu-id="16017-109">Remarks</span></span>

<span data-ttu-id="16017-p102">由于集合的成员是从 0 开始编号的，因此应始终将循环编写为从第 0 个成员开始，而在 **Count** 属性的值减 1 处结束。如果想要在不检查 **Count** 属性的情况下遍历集合成员，则可以使用 **For Each...Next** 命令。</span><span class="sxs-lookup"><span data-stu-id="16017-p102">Because members of a collection begin with 0, you should always code loops starting with the 0 member and ending with the value of the **Count** property minus 1. If you want to loop through the members of a collection without checking the **Count** property, you can use a **For Each...Next** command.</span></span>

<span data-ttu-id="16017-p103">**Count** 属性设置从不为 Null。如果其值为 0，则表示集合中没有对象。</span><span class="sxs-lookup"><span data-stu-id="16017-p103">The **Count** property setting is never Null. If its value is 0, there are no objects in the collection.</span></span>

