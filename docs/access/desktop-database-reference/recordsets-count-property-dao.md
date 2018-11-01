---
title: Recordsets.Count Property (DAO)
TOCTitle: Count Property
ms:assetid: 4362aa16-c8e9-e517-887e-c4532bd1eef9
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192940(v=office.15)
ms:contentKeyID: 48544500
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3a5697dcb6dbf3eb306ac94041127ee3e5992467
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25881662"
---
# <a name="recordsetscount-property-dao"></a><span data-ttu-id="cfbdc-102">Recordsets.Count Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="cfbdc-102">Recordsets.Count Property (DAO)</span></span>


<span data-ttu-id="cfbdc-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="cfbdc-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="cfbdc-p101">返回指定集合中的对象数目。 **Integer** 类型，只读。</span><span class="sxs-lookup"><span data-stu-id="cfbdc-p101">Returns the number of objects in the specified collection. Read-only **Integer**.</span></span>

## <a name="syntax"></a><span data-ttu-id="cfbdc-106">语法</span><span class="sxs-lookup"><span data-stu-id="cfbdc-106">Syntax</span></span>

<span data-ttu-id="cfbdc-107">*表达式*。计数</span><span class="sxs-lookup"><span data-stu-id="cfbdc-107">*expression* .Count</span></span>

<span data-ttu-id="cfbdc-108">*表达式*一个代表**Recordsets**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="cfbdc-108">*expression* A variable that represents a **Recordsets** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="cfbdc-109">注解</span><span class="sxs-lookup"><span data-stu-id="cfbdc-109">Remarks</span></span>

<span data-ttu-id="cfbdc-p102">由于集合的成员是从 0 开始编号的，因此应始终将循环编写为从第 0 个成员开始，而在 **Count** 属性的值减 1 处结束。如果想要在不检查 **Count** 属性的情况下遍历集合成员，则可以使用 **For Each...Next** 命令。</span><span class="sxs-lookup"><span data-stu-id="cfbdc-p102">Because members of a collection begin with 0, you should always code loops starting with the 0 member and ending with the value of the **Count** property minus 1. If you want to loop through the members of a collection without checking the **Count** property, you can use a **For Each...Next** command.</span></span>

<span data-ttu-id="cfbdc-p103">**Count** 属性设置从不为 Null。如果其值为 0，则表示集合中没有对象。</span><span class="sxs-lookup"><span data-stu-id="cfbdc-p103">The **Count** property setting is never Null. If its value is 0, there are no objects in the collection.</span></span>

