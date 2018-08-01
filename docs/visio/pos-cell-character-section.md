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
ms.openlocfilehash: 50ce5a3f7caf3e716f430aa08326281c8dc847f7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780960"
---
# <a name="pos-cell-character-section"></a><span data-ttu-id="a7970-103">Pos 单元格（“Character”部分）</span><span class="sxs-lookup"><span data-stu-id="a7970-103">Pos Cell (Character Section)</span></span>

<span data-ttu-id="a7970-104">确定形状的文本相对于基准线的位置。</span><span class="sxs-lookup"><span data-stu-id="a7970-104">Determines the position of the shape's text relative to the baseline.</span></span>
  
|<span data-ttu-id="a7970-105">**值**</span><span class="sxs-lookup"><span data-stu-id="a7970-105">**Value**</span></span>|<span data-ttu-id="a7970-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="a7970-106">**Description**</span></span>|<span data-ttu-id="a7970-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="a7970-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="a7970-108">0</span><span class="sxs-lookup"><span data-stu-id="a7970-108">0</span></span>  <br/> | <span data-ttu-id="a7970-109">标准位置</span><span class="sxs-lookup"><span data-stu-id="a7970-109">Normal position</span></span>  <br/> |<span data-ttu-id="a7970-110">**visPosNormal**</span><span class="sxs-lookup"><span data-stu-id="a7970-110">**visPosNormal**</span></span> <br/> |
| <span data-ttu-id="a7970-111">1</span><span class="sxs-lookup"><span data-stu-id="a7970-111">1</span></span>  <br/> | <span data-ttu-id="a7970-112">上标</span><span class="sxs-lookup"><span data-stu-id="a7970-112">Superscript</span></span>  <br/> |<span data-ttu-id="a7970-113">**visPosSuper**</span><span class="sxs-lookup"><span data-stu-id="a7970-113">**visPosSuper**</span></span> <br/> |
| <span data-ttu-id="a7970-114">2</span><span class="sxs-lookup"><span data-stu-id="a7970-114">2</span></span>  <br/> | <span data-ttu-id="a7970-115">下标</span><span class="sxs-lookup"><span data-stu-id="a7970-115">Subscript</span></span>  <br/> |<span data-ttu-id="a7970-116">**visPosSub**</span><span class="sxs-lookup"><span data-stu-id="a7970-116">**visPosSub**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a7970-117">说明</span><span class="sxs-lookup"><span data-stu-id="a7970-117">Remarks</span></span>

<span data-ttu-id="a7970-118">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Pos 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="a7970-118">To get a reference to the Pos cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="a7970-119">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="a7970-119">Cell name:</span></span>  <br/> | <span data-ttu-id="a7970-120">Char.Pos [ *i* ] 其中*i* = < 1 >，2，3...</span><span class="sxs-lookup"><span data-stu-id="a7970-120">Char.Pos[  *i*  ]            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="a7970-121">要从某个程序按索引获取对 Pos 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="a7970-121">To get a reference to the Pos cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="a7970-122">内容索引：</span><span class="sxs-lookup"><span data-stu-id="a7970-122">Section index:</span></span>  <br/> |<span data-ttu-id="a7970-123">**visSectionCharacter**</span><span class="sxs-lookup"><span data-stu-id="a7970-123">**visSectionCharacter**</span></span> <br/> |
| <span data-ttu-id="a7970-124">行索引：</span><span class="sxs-lookup"><span data-stu-id="a7970-124">Row index:</span></span>  <br/> |<span data-ttu-id="a7970-125">**visRowCharacter** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="a7970-125">**visRowCharacter** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="a7970-126">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="a7970-126">Cell index:</span></span>  <br/> |<span data-ttu-id="a7970-127">**visCharacterPos**</span><span class="sxs-lookup"><span data-stu-id="a7970-127">**visCharacterPos**</span></span> <br/> |
   

