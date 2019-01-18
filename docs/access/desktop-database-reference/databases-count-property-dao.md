---
title: Databases.Count 属性 (DAO)
TOCTitle: Count Property
ms:assetid: 7c542b17-9806-e00e-8cbd-58d6d17e98c4
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196364(v=office.15)
ms:contentKeyID: 48545831
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: cd8908492721315202c5bdf26109753c88905a07
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28720126"
---
# <a name="databasescount-property-dao"></a><span data-ttu-id="4e7ff-102">Databases.Count 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="4e7ff-102">Databases.Count property (DAO)</span></span>


<span data-ttu-id="4e7ff-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="4e7ff-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="4e7ff-p101">返回指定集合中的对象数。只读。</span><span class="sxs-lookup"><span data-stu-id="4e7ff-p101">Returns the number of objects in the specified collection. Read-only.</span></span>

## <a name="syntax"></a><span data-ttu-id="4e7ff-106">语法</span><span class="sxs-lookup"><span data-stu-id="4e7ff-106">Syntax</span></span>

<span data-ttu-id="4e7ff-107">*表达式*。计数</span><span class="sxs-lookup"><span data-stu-id="4e7ff-107">*expression* .Count</span></span>

<span data-ttu-id="4e7ff-108">*表达式*一个代表**Databases**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="4e7ff-108">*expression* A variable that represents a **Databases** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="4e7ff-109">注解</span><span class="sxs-lookup"><span data-stu-id="4e7ff-109">Remarks</span></span>

<span data-ttu-id="4e7ff-p102">由于集合的成员是从 0 开始编号的，因此应始终将循环编写为从第 0 个成员开始，而在 **Count** 属性的值减 1 处结束。如果想要在不检查 **Count** 属性的情况下遍历集合成员，则可以使用 **For Each...Next** 命令。</span><span class="sxs-lookup"><span data-stu-id="4e7ff-p102">Because members of a collection begin with 0, you should always code loops starting with the 0 member and ending with the value of the **Count** property minus 1. If you want to loop through the members of a collection without checking the **Count** property, you can use a **For Each...Next** command.</span></span>

<span data-ttu-id="4e7ff-p103">**Count** 属性设置从不为 Null。如果其值为 0，则表示集合中没有对象。</span><span class="sxs-lookup"><span data-stu-id="4e7ff-p103">The **Count** property setting is never Null. If its value is 0, there are no objects in the collection.</span></span>

