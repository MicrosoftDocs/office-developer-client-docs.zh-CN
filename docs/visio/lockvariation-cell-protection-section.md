---
title: 'LockVariation Cell (Protection Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 36acb95d-5d3b-4d8b-9b6c-effbc78c84c2
description: 确定是否可以将应用于页面或形状的主题变体作为布尔值进行更改。
ms.openlocfilehash: 69c991e3da7a96d6c59dc825dfb78fdad3d432e7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427925"
---
# <a name="lockvariation-cell-protection-section"></a><span data-ttu-id="849ed-103">LockVariation Cell (Protection Section) </span><span class="sxs-lookup"><span data-stu-id="849ed-103">LockVariation Cell (Protection Section)</span></span>

<span data-ttu-id="849ed-104">确定是否可以将应用于页面或形状的主题变体作为布尔值进行更改。</span><span class="sxs-lookup"><span data-stu-id="849ed-104">Determines whether the theme variation applied to the page or shape can be changed, as a Boolean.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="849ed-105">TRUE</span><span class="sxs-lookup"><span data-stu-id="849ed-105">TRUE</span></span>  <br/> |<span data-ttu-id="849ed-106">应用于页面或形状的当前变体无法更改。</span><span class="sxs-lookup"><span data-stu-id="849ed-106">The current variation applied to the page or shape cannot be changed.</span></span>  <br/> |
|<span data-ttu-id="849ed-107">FALSE</span><span class="sxs-lookup"><span data-stu-id="849ed-107">FALSE</span></span>  <br/> |<span data-ttu-id="849ed-108">可以更改页面或形状的变体。</span><span class="sxs-lookup"><span data-stu-id="849ed-108">The variation of the page or shape can be changed.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="849ed-109">备注</span><span class="sxs-lookup"><span data-stu-id="849ed-109">Remarks</span></span>

<span data-ttu-id="849ed-110">若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 CellsU 属性从某个程序按名称获取对 **LockVariation** 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="849ed-110">To get a reference to the **LockVariation** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="849ed-111">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="849ed-111">Cell name:</span></span>  <br/> | <span data-ttu-id="849ed-112">LockVariation</span><span class="sxs-lookup"><span data-stu-id="849ed-112">LockVariation</span></span>  <br/> |
   
<span data-ttu-id="849ed-113">若要从程序按索引获取对 **LockVariation** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="849ed-113">To get a reference to the **LockVariation** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="849ed-114">内容索引：</span><span class="sxs-lookup"><span data-stu-id="849ed-114">Section index:</span></span>  <br/> |<span data-ttu-id="849ed-115">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="849ed-115">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="849ed-116">行索引：</span><span class="sxs-lookup"><span data-stu-id="849ed-116">Row index:</span></span>  <br/> |<span data-ttu-id="849ed-117">**visRowLock**</span><span class="sxs-lookup"><span data-stu-id="849ed-117">**visRowLock**</span></span> <br/> |
| <span data-ttu-id="849ed-118">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="849ed-118">Cell index:</span></span>  <br/> |<span data-ttu-id="849ed-119">**visLockVariation**</span><span class="sxs-lookup"><span data-stu-id="849ed-119">**visLockVariation**</span></span> <br/> |
   

