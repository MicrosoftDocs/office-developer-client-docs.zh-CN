---
title: Fields 属性 (DAO)
TOCTitle: Count Property
ms:assetid: 574de1db-2640-159b-7756-28c37acc9f83
ms:mtpsurl: https://msdn.microsoft.com/library/Ff194261(v=office.15)
ms:contentKeyID: 48544969
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 99eb21ba4f4ef13c902fc0d029dba59c30066853
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292543"
---
# <a name="fieldscount-property-dao"></a><span data-ttu-id="1fa1e-102">Fields 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="1fa1e-102">Fields.Count property (DAO)</span></span>


<span data-ttu-id="1fa1e-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="1fa1e-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="1fa1e-104">返回指定集合中的对象数目。</span><span class="sxs-lookup"><span data-stu-id="1fa1e-104">Returns the number of objects in the specified collection.</span></span> <span data-ttu-id="1fa1e-105">**Integer** 类型，只读。</span><span class="sxs-lookup"><span data-stu-id="1fa1e-105">Read-only **Integer**.</span></span>

## <a name="syntax"></a><span data-ttu-id="1fa1e-106">语法</span><span class="sxs-lookup"><span data-stu-id="1fa1e-106">Syntax</span></span>

<span data-ttu-id="1fa1e-107">*表达式*。计数</span><span class="sxs-lookup"><span data-stu-id="1fa1e-107">*expression* .Count</span></span>

<span data-ttu-id="1fa1e-108">*表达式*一个代表**Fields**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="1fa1e-108">*expression* A variable that represents a **Fields** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="1fa1e-109">注解</span><span class="sxs-lookup"><span data-stu-id="1fa1e-109">Remarks</span></span>

<span data-ttu-id="1fa1e-p102">由于集合的成员由 0 开始，因此应始终将循环编写为从第 0 个成员开始，并在 **Count** 属性的值减 1 处结束。如果需要在集合的成员中循环且不检查 **Count** 属性，可以使用 **For Each...Next** 命令。</span><span class="sxs-lookup"><span data-stu-id="1fa1e-p102">Because members of a collection begin with 0, you should always code loops starting with the 0 member and ending with the value of the **Count** property minus 1. If you want to loop through the members of a collection without checking the **Count** property, you can use a **For Each...Next** command.</span></span>

<span data-ttu-id="1fa1e-p103">**Count** 属性设置从不为 Null。如果其值为 0，则表示集合中没有对象。</span><span class="sxs-lookup"><span data-stu-id="1fa1e-p103">The **Count** property setting is never Null. If its value is 0, there are no objects in the collection.</span></span>

