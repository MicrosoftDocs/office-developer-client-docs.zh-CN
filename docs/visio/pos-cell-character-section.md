---
title: Pos 单元格（“Character”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm805
localization_priority: Normal
ms.assetid: c02186ce-6a20-fbe7-588d-d64c3ea4dec4
description: 确定形状的文本相对于基准线的位置。
ms.openlocfilehash: d5f6823d6f55493095d29054745f62b579a47893
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359813"
---
# <a name="pos-cell-character-section"></a><span data-ttu-id="8b143-103">Pos 单元格（“Character”内容）</span><span class="sxs-lookup"><span data-stu-id="8b143-103">Pos Cell (Character Section)</span></span>

<span data-ttu-id="8b143-104">确定形状的文本相对于基准线的位置。</span><span class="sxs-lookup"><span data-stu-id="8b143-104">Determines the position of the shape's text relative to the baseline.</span></span>
  
|<span data-ttu-id="8b143-105">**Value**</span><span class="sxs-lookup"><span data-stu-id="8b143-105">**Value**</span></span>|<span data-ttu-id="8b143-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="8b143-106">**Description**</span></span>|<span data-ttu-id="8b143-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="8b143-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="8b143-108">0</span><span class="sxs-lookup"><span data-stu-id="8b143-108">0</span></span>  <br/> | <span data-ttu-id="8b143-109">标准位置</span><span class="sxs-lookup"><span data-stu-id="8b143-109">Normal position</span></span>  <br/> |<span data-ttu-id="8b143-110">**visPosNormal**</span><span class="sxs-lookup"><span data-stu-id="8b143-110">**visPosNormal**</span></span> <br/> |
| <span data-ttu-id="8b143-111">1</span><span class="sxs-lookup"><span data-stu-id="8b143-111">1</span></span>  <br/> | <span data-ttu-id="8b143-112">Superscript</span><span class="sxs-lookup"><span data-stu-id="8b143-112">Superscript</span></span>  <br/> |<span data-ttu-id="8b143-113">**visPosSuper**</span><span class="sxs-lookup"><span data-stu-id="8b143-113">**visPosSuper**</span></span> <br/> |
| <span data-ttu-id="8b143-114">双面</span><span class="sxs-lookup"><span data-stu-id="8b143-114">2</span></span>  <br/> | <span data-ttu-id="8b143-115">Subscript</span><span class="sxs-lookup"><span data-stu-id="8b143-115">Subscript</span></span>  <br/> |<span data-ttu-id="8b143-116">**visPosSub**</span><span class="sxs-lookup"><span data-stu-id="8b143-116">**visPosSub**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8b143-117">注解</span><span class="sxs-lookup"><span data-stu-id="8b143-117">Remarks</span></span>

<span data-ttu-id="8b143-118">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Pos 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="8b143-118">To get a reference to the Pos cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="8b143-119">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="8b143-119">Cell name:</span></span>  <br/> | <span data-ttu-id="8b143-120">Char. [ *i* ] 其中*i* = <1>, 2, 3 .。。</span><span class="sxs-lookup"><span data-stu-id="8b143-120">Char.Pos[  *i*  ]            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="8b143-121">要从某个程序按索引获取对 Pos 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="8b143-121">To get a reference to the Pos cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="8b143-122">内容索引：</span><span class="sxs-lookup"><span data-stu-id="8b143-122">Section index:</span></span>  <br/> |<span data-ttu-id="8b143-123">**visSectionCharacter**</span><span class="sxs-lookup"><span data-stu-id="8b143-123">**visSectionCharacter**</span></span> <br/> |
| <span data-ttu-id="8b143-124">行索引：</span><span class="sxs-lookup"><span data-stu-id="8b143-124">Row index:</span></span>  <br/> |<span data-ttu-id="8b143-125">**visRowCharacter** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="8b143-125">**visRowCharacter** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="8b143-126">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="8b143-126">Cell index:</span></span>  <br/> |<span data-ttu-id="8b143-127">**visCharacterPos**</span><span class="sxs-lookup"><span data-stu-id="8b143-127">**visCharacterPos**</span></span> <br/> |
   

