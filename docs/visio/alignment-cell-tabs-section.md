---
title: Alignment 单元格（“Tabs”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm35
localization_priority: Normal
ms.assetid: 84234177-a2df-6acc-2761-230bc5d12627
description: 指定制表位的对齐方式。
ms.openlocfilehash: 461357c9c838fb4c0e5b0159bf027dd6adce26f9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425538"
---
# <a name="alignment-cell-tabs-section"></a><span data-ttu-id="d5105-103">Alignment 单元格（“Tabs”内容）</span><span class="sxs-lookup"><span data-stu-id="d5105-103">Alignment Cell (Tabs Section)</span></span>

<span data-ttu-id="d5105-104">指定制表位的对齐方式。</span><span class="sxs-lookup"><span data-stu-id="d5105-104">Specifies the tab alignment.</span></span>
  
|<span data-ttu-id="d5105-105">**值**</span><span class="sxs-lookup"><span data-stu-id="d5105-105">**Value**</span></span>|<span data-ttu-id="d5105-106">**Alignment**</span><span class="sxs-lookup"><span data-stu-id="d5105-106">**Alignment**</span></span>|<span data-ttu-id="d5105-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="d5105-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="d5105-108">0</span><span class="sxs-lookup"><span data-stu-id="d5105-108">0</span></span>  <br/> | <span data-ttu-id="d5105-109">Left</span><span class="sxs-lookup"><span data-stu-id="d5105-109">Left</span></span>  <br/> |<span data-ttu-id="d5105-110">**visTabStopLeft**</span><span class="sxs-lookup"><span data-stu-id="d5105-110">**visTabStopLeft**</span></span> <br/> |
| <span data-ttu-id="d5105-111">1</span><span class="sxs-lookup"><span data-stu-id="d5105-111">1</span></span>  <br/> | <span data-ttu-id="d5105-112">居中</span><span class="sxs-lookup"><span data-stu-id="d5105-112">Center</span></span>  <br/> |<span data-ttu-id="d5105-113">**visTabStopCenter**</span><span class="sxs-lookup"><span data-stu-id="d5105-113">**visTabStopCenter**</span></span> <br/> |
| <span data-ttu-id="d5105-114">双面</span><span class="sxs-lookup"><span data-stu-id="d5105-114">2</span></span>  <br/> | <span data-ttu-id="d5105-115">右侧</span><span class="sxs-lookup"><span data-stu-id="d5105-115">Right</span></span>  <br/> |<span data-ttu-id="d5105-116">**visTabStopRight**</span><span class="sxs-lookup"><span data-stu-id="d5105-116">**visTabStopRight**</span></span> <br/> |
| <span data-ttu-id="d5105-117">第三章</span><span class="sxs-lookup"><span data-stu-id="d5105-117">3</span></span>  <br/> | <span data-ttu-id="d5105-118">十进制</span><span class="sxs-lookup"><span data-stu-id="d5105-118">Decimal</span></span>  <br/> |<span data-ttu-id="d5105-119">**visTabStopDecimal**</span><span class="sxs-lookup"><span data-stu-id="d5105-119">**visTabStopDecimal**</span></span> <br/> |
| <span data-ttu-id="d5105-120">4</span><span class="sxs-lookup"><span data-stu-id="d5105-120">4</span></span>  <br/> | <span data-ttu-id="d5105-121">逗号</span><span class="sxs-lookup"><span data-stu-id="d5105-121">Comma</span></span>  <br/> |<span data-ttu-id="d5105-122">**visTabStopComma**</span><span class="sxs-lookup"><span data-stu-id="d5105-122">**visTabStopComma**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d5105-123">说明</span><span class="sxs-lookup"><span data-stu-id="d5105-123">Remarks</span></span>

<span data-ttu-id="d5105-124">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Alignment 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="d5105-124">To get a reference to the Alignment cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="d5105-125">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="d5105-125">Cell name:</span></span>  <br/> | <span data-ttu-id="d5105-126">张.</span><span class="sxs-lookup"><span data-stu-id="d5105-126">Tabs.</span></span>  <span data-ttu-id="d5105-127">*ij*其中*i 和 j =* <1>, 2, 3</span><span class="sxs-lookup"><span data-stu-id="d5105-127">*ij*            where  *i and j =*  <1>, 2, 3</span></span>  <br/> |
   
<span data-ttu-id="d5105-128">要从某个程序按索引获取对 Alignment 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="d5105-128">To get a reference to the Alignment cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="d5105-129">内容索引：</span><span class="sxs-lookup"><span data-stu-id="d5105-129">Section index:</span></span>  <br/> |<span data-ttu-id="d5105-130">**visSectionTab**</span><span class="sxs-lookup"><span data-stu-id="d5105-130">**visSectionTab**</span></span> <br/> |
| <span data-ttu-id="d5105-131">行索引：</span><span class="sxs-lookup"><span data-stu-id="d5105-131">Row index:</span></span>  <br/> |<span data-ttu-id="d5105-132">\**visRowTab +\*\*\*i*其中*i* = 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="d5105-132">**visRowTab +** *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="d5105-133">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="d5105-133">Cell index:</span></span>  <br/> | <span data-ttu-id="d5105-134">(*j* \* 3) **+ visTabAlign**</span><span class="sxs-lookup"><span data-stu-id="d5105-134">(*j*  \*3) **+ visTabAlign**</span></span> <br/> |
   

