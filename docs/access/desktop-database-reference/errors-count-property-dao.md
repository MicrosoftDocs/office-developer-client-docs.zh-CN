---
title: Errors 属性 (DAO)
TOCTitle: Count Property
ms:assetid: ad135955-3b18-4f99-66d9-aff1492df13b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821719(v=office.15)
ms:contentKeyID: 48547028
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: c2cbbed2c7061b225d969dbd7554191e8db4a28a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32293397"
---
# <a name="errorscount-property-dao"></a><span data-ttu-id="4caa7-102">Errors 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="4caa7-102">Errors.Count property (DAO)</span></span>


<span data-ttu-id="4caa7-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="4caa7-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="4caa7-104">返回指定集合中的对象数。</span><span class="sxs-lookup"><span data-stu-id="4caa7-104">Returns the number of objects in the specified collection.</span></span> <span data-ttu-id="4caa7-105">此为只读属性。</span><span class="sxs-lookup"><span data-stu-id="4caa7-105">Read-only.</span></span>

## <a name="syntax"></a><span data-ttu-id="4caa7-106">语法</span><span class="sxs-lookup"><span data-stu-id="4caa7-106">Syntax</span></span>

<span data-ttu-id="4caa7-107">*表达式*。计数</span><span class="sxs-lookup"><span data-stu-id="4caa7-107">*expression* .Count</span></span>

<span data-ttu-id="4caa7-108">*表达式*一个代表**Errors**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="4caa7-108">*expression* A variable that represents an **Errors** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="4caa7-109">注解</span><span class="sxs-lookup"><span data-stu-id="4caa7-109">Remarks</span></span>

<span data-ttu-id="4caa7-p102">由于集合的成员由 0 开始，因此应始终将循环编写为从第 0 个成员开始，并在 **Count** 属性的值减 1 处结束。如果需要在集合的成员中循环且不检查 **Count** 属性，可以使用 **For Each...Next** 命令。</span><span class="sxs-lookup"><span data-stu-id="4caa7-p102">Because members of a collection begin with 0, you should always code loops starting with the 0 member and ending with the value of the **Count** property minus 1. If you want to loop through the members of a collection without checking the **Count** property, you can use a **For Each...Next** command.</span></span>

<span data-ttu-id="4caa7-p103">**Count** 属性设置从不为 Null。如果其值为 0，则表示集合中没有对象。</span><span class="sxs-lookup"><span data-stu-id="4caa7-p103">The **Count** property setting is never Null. If its value is 0, there are no objects in the collection.</span></span>

