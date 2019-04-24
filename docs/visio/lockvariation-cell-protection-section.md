---
title: LockVariation 单元格 ("Protection" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 36acb95d-5d3b-4d8b-9b6c-effbc78c84c2
description: 确定应用于页面或形状的主题变体是否可更改为布尔值。
ms.openlocfilehash: 69c991e3da7a96d6c59dc825dfb78fdad3d432e7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358063"
---
# <a name="lockvariation-cell-protection-section"></a><span data-ttu-id="336e3-103">LockVariation 单元格 ("Protection" 部分)</span><span class="sxs-lookup"><span data-stu-id="336e3-103">LockVariation Cell (Protection Section)</span></span>

<span data-ttu-id="336e3-104">确定应用于页面或形状的主题变体是否可更改为布尔值。</span><span class="sxs-lookup"><span data-stu-id="336e3-104">Determines whether the theme variation applied to the page or shape can be changed, as a Boolean.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="336e3-105">TRUE</span><span class="sxs-lookup"><span data-stu-id="336e3-105">TRUE</span></span>  <br/> |<span data-ttu-id="336e3-106">应用于页面或形状的当前变体无法更改。</span><span class="sxs-lookup"><span data-stu-id="336e3-106">The current variation applied to the page or shape cannot be changed.</span></span>  <br/> |
|<span data-ttu-id="336e3-107">FALSE</span><span class="sxs-lookup"><span data-stu-id="336e3-107">FALSE</span></span>  <br/> |<span data-ttu-id="336e3-108">可以更改页面或形状的变体。</span><span class="sxs-lookup"><span data-stu-id="336e3-108">The variation of the page or shape can be changed.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="336e3-109">注解</span><span class="sxs-lookup"><span data-stu-id="336e3-109">Remarks</span></span>

<span data-ttu-id="336e3-110">若要从另一个公式按名称获取对**LockVariation**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用:</span><span class="sxs-lookup"><span data-stu-id="336e3-110">To get a reference to the **LockVariation** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="336e3-111">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="336e3-111">Cell name:</span></span>  <br/> | <span data-ttu-id="336e3-112">LockVariation</span><span class="sxs-lookup"><span data-stu-id="336e3-112">LockVariation</span></span>  <br/> |
   
<span data-ttu-id="336e3-113">若要从某个程序按索引获取对**LockVariation**单元格的引用, 请使用带下列参数的**CellsSRC**属性:</span><span class="sxs-lookup"><span data-stu-id="336e3-113">To get a reference to the **LockVariation** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="336e3-114">内容索引：</span><span class="sxs-lookup"><span data-stu-id="336e3-114">Section index:</span></span>  <br/> |<span data-ttu-id="336e3-115">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="336e3-115">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="336e3-116">行索引：</span><span class="sxs-lookup"><span data-stu-id="336e3-116">Row index:</span></span>  <br/> |<span data-ttu-id="336e3-117">**visRowLock**</span><span class="sxs-lookup"><span data-stu-id="336e3-117">**visRowLock**</span></span> <br/> |
| <span data-ttu-id="336e3-118">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="336e3-118">Cell index:</span></span>  <br/> |<span data-ttu-id="336e3-119">**visLockVariation**</span><span class="sxs-lookup"><span data-stu-id="336e3-119">**visLockVariation**</span></span> <br/> |
   

