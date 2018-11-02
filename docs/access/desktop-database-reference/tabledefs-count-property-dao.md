---
title: TableDefs.Count 属性 (DAO)
TOCTitle: Count Property
ms:assetid: 6e2cf3e5-524f-a643-b1dc-99a4b2bb2e63
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195561(v=office.15)
ms:contentKeyID: 48545508
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 88a38180973b83232c324d052db0548cb308740a
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25923768"
---
# <a name="tabledefscount-property-dao"></a><span data-ttu-id="bbff6-102">TableDefs.Count 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="bbff6-102">TableDefs.Count property (DAO)</span></span>


<span data-ttu-id="bbff6-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="bbff6-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="bbff6-p101">返回指定集合中的对象数。只读。</span><span class="sxs-lookup"><span data-stu-id="bbff6-p101">Returns the number of objects in the specified collection. Read-only.</span></span>

## <a name="syntax"></a><span data-ttu-id="bbff6-106">语法</span><span class="sxs-lookup"><span data-stu-id="bbff6-106">Syntax</span></span>

<span data-ttu-id="bbff6-107">*表达式*。计数</span><span class="sxs-lookup"><span data-stu-id="bbff6-107">*expression* .Count</span></span>

<span data-ttu-id="bbff6-108">*表达式*一个代表**TableDefs**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="bbff6-108">*expression* A variable that represents a **TableDefs** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="bbff6-109">注解</span><span class="sxs-lookup"><span data-stu-id="bbff6-109">Remarks</span></span>

<span data-ttu-id="bbff6-p102">由于集合的成员是从 0 开始编号的，因此应始终将循环编写为从第 0 个成员开始，而在 **Count** 属性的值减 1 处结束。如果想要在不检查 **Count** 属性的情况下遍历集合成员，则可以使用 **For Each...Next** 命令。</span><span class="sxs-lookup"><span data-stu-id="bbff6-p102">Because members of a collection begin with 0, you should always code loops starting with the 0 member and ending with the value of the **Count** property minus 1. If you want to loop through the members of a collection without checking the **Count** property, you can use a **For Each...Next** command.</span></span>

<span data-ttu-id="bbff6-p103">**Count** 属性设置从不为 Null。如果其值为 0，则表示集合中没有对象。</span><span class="sxs-lookup"><span data-stu-id="bbff6-p103">The **Count** property setting is never Null. If its value is 0, there are no objects in the collection.</span></span>

