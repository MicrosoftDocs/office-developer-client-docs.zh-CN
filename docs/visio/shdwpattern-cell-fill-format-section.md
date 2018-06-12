---
title: ShdwPattern 单元格（“Fill Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm935
localization_priority: Normal
ms.assetid: eca73b80-9835-9011-1dce-187ccee92e76
description: 确定某一形状的阴影的填充图案。
ms.openlocfilehash: fd24a8d23d62436a6d81cf6b8049dcabe47db677
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781324"
---
# <a name="shdwpattern-cell-fill-format-section"></a><span data-ttu-id="c05c2-103">ShdwPattern 单元格（“Fill Format”内容）</span><span class="sxs-lookup"><span data-stu-id="c05c2-103">ShdwPattern Cell (Fill Format Section)</span></span>

<span data-ttu-id="c05c2-104">确定某一形状的阴影的填充图案。</span><span class="sxs-lookup"><span data-stu-id="c05c2-104">Determines the fill pattern for a shape's shadow.</span></span>
  
|<span data-ttu-id="c05c2-105">**值**</span><span class="sxs-lookup"><span data-stu-id="c05c2-105">**Value**</span></span>|<span data-ttu-id="c05c2-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="c05c2-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c05c2-107">0</span><span class="sxs-lookup"><span data-stu-id="c05c2-107">0</span></span>  <br/> |<span data-ttu-id="c05c2-108">无（透明填充）</span><span class="sxs-lookup"><span data-stu-id="c05c2-108">None (transparent fill)</span></span>  <br/> |
|<span data-ttu-id="c05c2-109">1</span><span class="sxs-lookup"><span data-stu-id="c05c2-109">1</span></span>  <br/> |<span data-ttu-id="c05c2-110">前景纯色</span><span class="sxs-lookup"><span data-stu-id="c05c2-110">Solid foreground color</span></span>  <br/> |
|<span data-ttu-id="c05c2-111">2-40</span><span class="sxs-lookup"><span data-stu-id="c05c2-111">2 - 40</span></span>  <br/> |<span data-ttu-id="c05c2-112">各种类型的图案</span><span class="sxs-lookup"><span data-stu-id="c05c2-112">Assorted patterns</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c05c2-113">注解</span><span class="sxs-lookup"><span data-stu-id="c05c2-113">Remarks</span></span>

<span data-ttu-id="c05c2-114">若要设置的填充图案，输入一个号码从 0 到 40，这是一种模式的索引。</span><span class="sxs-lookup"><span data-stu-id="c05c2-114">To set the fill pattern, enter a number from 0 to 40, which is an index into a collection of patterns.</span></span> <span data-ttu-id="c05c2-115">在**填充**对话框中，可以查看填充图案集合 （在**主页**选项卡，**形状**组中，单击**填充**，然后单击**填充选项**）。</span><span class="sxs-lookup"><span data-stu-id="c05c2-115">You can view the fill pattern collection in the **Fill** dialog box (on the **Home** tab, in the **Shape** group, click **Fill**, and then click **Fill Options**).</span></span>
  
<span data-ttu-id="c05c2-116">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 ShdwPattern 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="c05c2-116">To get a reference to the ShdwPattern cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c05c2-117">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="c05c2-117">Cell name:</span></span>  <br/> |<span data-ttu-id="c05c2-118">ShdwPattern</span><span class="sxs-lookup"><span data-stu-id="c05c2-118">ShdwPattern</span></span>  <br/> |
   
<span data-ttu-id="c05c2-119">若要从某个程序按索引获取对 ShdwPattern 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="c05c2-119">To get a reference to the ShdwPattern cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c05c2-120">内容索引：</span><span class="sxs-lookup"><span data-stu-id="c05c2-120">Section index:</span></span>  <br/> |<span data-ttu-id="c05c2-121">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="c05c2-121">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="c05c2-122">行索引：</span><span class="sxs-lookup"><span data-stu-id="c05c2-122">Row index:</span></span>  <br/> |<span data-ttu-id="c05c2-123">**visRowFill**</span><span class="sxs-lookup"><span data-stu-id="c05c2-123">**visRowFill**</span></span> <br/> |
|<span data-ttu-id="c05c2-124">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="c05c2-124">Cell index:</span></span>  <br/> |<span data-ttu-id="c05c2-125">**visFillShdwPattern**</span><span class="sxs-lookup"><span data-stu-id="c05c2-125">**visFillShdwPattern**</span></span> <br/> |
   

