---
title: LockVariation 单元格（“Protection”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 36acb95d-5d3b-4d8b-9b6c-effbc78c84c2
description: 确定是否应用于形状的页面的主题变体可更改，作为一个布尔值。
ms.openlocfilehash: c3c272a637f28aa4df43f6c23030d6676280138e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780664"
---
# <a name="lockvariation-cell-protection-section"></a><span data-ttu-id="4ca3d-103">LockVariation 单元格（“Protection”部分）</span><span class="sxs-lookup"><span data-stu-id="4ca3d-103">LockVariation Cell (Protection Section)</span></span>

<span data-ttu-id="4ca3d-104">确定是否应用于形状的页面的主题变体可更改，作为一个布尔值。</span><span class="sxs-lookup"><span data-stu-id="4ca3d-104">Determines whether the theme variation applied to the page or shape can be changed, as a Boolean.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="4ca3d-105">TRUE</span><span class="sxs-lookup"><span data-stu-id="4ca3d-105">TRUE</span></span>  <br/> |<span data-ttu-id="4ca3d-106">不能更改应用于页面或形状的当前变体。</span><span class="sxs-lookup"><span data-stu-id="4ca3d-106">The current variation applied to the page or shape cannot be changed.</span></span>  <br/> |
|<span data-ttu-id="4ca3d-107">FALSE</span><span class="sxs-lookup"><span data-stu-id="4ca3d-107">FALSE</span></span>  <br/> |<span data-ttu-id="4ca3d-108">可以更改的形状的页面变体。</span><span class="sxs-lookup"><span data-stu-id="4ca3d-108">The variation of the page or shape can be changed.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4ca3d-109">说明</span><span class="sxs-lookup"><span data-stu-id="4ca3d-109">Remarks</span></span>

<span data-ttu-id="4ca3d-110">要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**LockVariation**单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="4ca3d-110">To get a reference to the **LockVariation** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="4ca3d-111">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="4ca3d-111">Cell name:</span></span>  <br/> | <span data-ttu-id="4ca3d-112">LockVariation</span><span class="sxs-lookup"><span data-stu-id="4ca3d-112">LockVariation</span></span>  <br/> |
   
<span data-ttu-id="4ca3d-113">若要从某个程序按索引获取对**LockVariation**单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="4ca3d-113">To get a reference to the **LockVariation** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="4ca3d-114">内容索引：</span><span class="sxs-lookup"><span data-stu-id="4ca3d-114">Section index:</span></span>  <br/> |<span data-ttu-id="4ca3d-115">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="4ca3d-115">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="4ca3d-116">行索引：</span><span class="sxs-lookup"><span data-stu-id="4ca3d-116">Row index:</span></span>  <br/> |<span data-ttu-id="4ca3d-117">**visRowLock**</span><span class="sxs-lookup"><span data-stu-id="4ca3d-117">**visRowLock**</span></span> <br/> |
| <span data-ttu-id="4ca3d-118">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="4ca3d-118">Cell index:</span></span>  <br/> |<span data-ttu-id="4ca3d-119">**visLockVariation**</span><span class="sxs-lookup"><span data-stu-id="4ca3d-119">**visLockVariation**</span></span> <br/> |
   

