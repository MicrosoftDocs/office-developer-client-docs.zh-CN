---
title: Documents.Count 属性 (DAO)
TOCTitle: Count Property
ms:assetid: 3fc0b1e6-f7be-cd43-711f-5cf5763fe7f6
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192858(v=office.15)
ms:contentKeyID: 48544407
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053325
f1_categories:
- Office.Version=v15
ms.openlocfilehash: b01ec200278095893214f10dc9e50c5266153d72
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25918931"
---
# <a name="documentscount-property-dao"></a><span data-ttu-id="a99ea-102">Documents.Count 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="a99ea-102">Documents.Count property (DAO)</span></span>


<span data-ttu-id="a99ea-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="a99ea-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="a99ea-p101">返回指定集合中的对象数。只读。</span><span class="sxs-lookup"><span data-stu-id="a99ea-p101">Returns the number of objects in the specified collection. Read-only.</span></span>

## <a name="syntax"></a><span data-ttu-id="a99ea-106">语法</span><span class="sxs-lookup"><span data-stu-id="a99ea-106">Syntax</span></span>

<span data-ttu-id="a99ea-107">*表达式*。计数</span><span class="sxs-lookup"><span data-stu-id="a99ea-107">*expression* .Count</span></span>

<span data-ttu-id="a99ea-108">*表达式*一个代表**Documents**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="a99ea-108">*expression* A variable that represents a **Documents** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="a99ea-109">注解</span><span class="sxs-lookup"><span data-stu-id="a99ea-109">Remarks</span></span>

<span data-ttu-id="a99ea-p102">由于集合的成员是从 0 开始编号的，因此应始终将循环编写为从第 0 个成员开始，而在 **Count** 属性的值减 1 处结束。如果想要在不检查 **Count** 属性的情况下遍历集合成员，则可以使用 **For Each...Next** 命令。</span><span class="sxs-lookup"><span data-stu-id="a99ea-p102">Because members of a collection begin with 0, you should always code loops starting with the 0 member and ending with the value of the **Count** property minus 1. If you want to loop through the members of a collection without checking the **Count** property, you can use a **For Each...Next** command.</span></span>

<span data-ttu-id="a99ea-p103">**Count** 属性设置从不为 Null。如果其值为 0，则表示集合中没有对象。</span><span class="sxs-lookup"><span data-stu-id="a99ea-p103">The **Count** property setting is never Null. If its value is 0, there are no objects in the collection.</span></span>

