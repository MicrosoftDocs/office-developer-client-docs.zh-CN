---
title: QueryDefs 属性 (DAO)
TOCTitle: Count Property
ms:assetid: 8caa01c5-692f-95e4-4b11-6e6c591f5872
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197340(v=office.15)
ms:contentKeyID: 48546240
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 95624c82ee9ab322eec5455759cf4ec2e9708dba
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32300957"
---
# <a name="querydefscount-property-dao"></a><span data-ttu-id="8710d-102">QueryDefs 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="8710d-102">QueryDefs.Count property (DAO)</span></span>


<span data-ttu-id="8710d-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="8710d-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="8710d-104">返回指定集合中的对象数。</span><span class="sxs-lookup"><span data-stu-id="8710d-104">Returns the number of objects in the specified collection.</span></span> <span data-ttu-id="8710d-105">此为只读属性。</span><span class="sxs-lookup"><span data-stu-id="8710d-105">Read-only.</span></span>

## <a name="syntax"></a><span data-ttu-id="8710d-106">语法</span><span class="sxs-lookup"><span data-stu-id="8710d-106">Syntax</span></span>

<span data-ttu-id="8710d-107">*表达式*。计数</span><span class="sxs-lookup"><span data-stu-id="8710d-107">*expression* .Count</span></span>

<span data-ttu-id="8710d-108">*表达式*一个代表**QueryDefs**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="8710d-108">*expression* A variable that represents a **QueryDefs** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="8710d-109">注解</span><span class="sxs-lookup"><span data-stu-id="8710d-109">Remarks</span></span>

<span data-ttu-id="8710d-p102">由于集合的成员由 0 开始，因此应始终将循环编写为从第 0 个成员开始，并在 **Count** 属性的值减 1 处结束。如果需要在集合的成员中循环且不检查 **Count** 属性，可以使用 **For Each...Next** 命令。</span><span class="sxs-lookup"><span data-stu-id="8710d-p102">Because members of a collection begin with 0, you should always code loops starting with the 0 member and ending with the value of the **Count** property minus 1. If you want to loop through the members of a collection without checking the **Count** property, you can use a **For Each...Next** command.</span></span>

<span data-ttu-id="8710d-p103">**Count** 属性设置从不为 Null。如果其值为 0，则表示集合中没有对象。</span><span class="sxs-lookup"><span data-stu-id="8710d-p103">The **Count** property setting is never Null. If its value is 0, there are no objects in the collection.</span></span>

