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
ms.openlocfilehash: c2591fbc9f208b1bf9c7d0c85e6de765cd9825f6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32349040"
---
# <a name="shdwpattern-cell-fill-format-section"></a><span data-ttu-id="dbbcf-103">ShdwPattern 单元格（“Fill Format”内容）</span><span class="sxs-lookup"><span data-stu-id="dbbcf-103">ShdwPattern Cell (Fill Format Section)</span></span>

<span data-ttu-id="dbbcf-104">确定某一形状的阴影的填充图案。</span><span class="sxs-lookup"><span data-stu-id="dbbcf-104">Determines the fill pattern for a shape's shadow.</span></span>
  
|<span data-ttu-id="dbbcf-105">**Value**</span><span class="sxs-lookup"><span data-stu-id="dbbcf-105">**Value**</span></span>|<span data-ttu-id="dbbcf-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="dbbcf-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="dbbcf-107">0</span><span class="sxs-lookup"><span data-stu-id="dbbcf-107">0</span></span>  <br/> |<span data-ttu-id="dbbcf-108">无（透明填充）</span><span class="sxs-lookup"><span data-stu-id="dbbcf-108">None (transparent fill)</span></span>  <br/> |
|<span data-ttu-id="dbbcf-109">1</span><span class="sxs-lookup"><span data-stu-id="dbbcf-109">1</span></span>  <br/> |<span data-ttu-id="dbbcf-110">前景纯色</span><span class="sxs-lookup"><span data-stu-id="dbbcf-110">Solid foreground color</span></span>  <br/> |
|<span data-ttu-id="dbbcf-111">2 - 40</span><span class="sxs-lookup"><span data-stu-id="dbbcf-111">2 - 40</span></span>  <br/> |<span data-ttu-id="dbbcf-112">各种类型的图案</span><span class="sxs-lookup"><span data-stu-id="dbbcf-112">Assorted patterns</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="dbbcf-113">注解</span><span class="sxs-lookup"><span data-stu-id="dbbcf-113">Remarks</span></span>

<span data-ttu-id="dbbcf-p101">若要设置填充图案，请输入一个介于 0 和 40 之间的数字，该数字是图案集合中的索引。您可以在 **“填充”** 对话框（在 **“开始”** 选项卡上的 **“形状”** 组中，单击 **“填充”**，然后单击 **“填充选项”**）中查看填充图案集合。</span><span class="sxs-lookup"><span data-stu-id="dbbcf-p101">To set the fill pattern, enter a number from 0 to 40, which is an index into a collection of patterns. You can view the fill pattern collection in the **Fill** dialog box (on the **Home** tab, in the **Shape** group, click **Fill**, and then click **Fill Options**).</span></span>
  
<span data-ttu-id="dbbcf-116">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ShdwPattern 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="dbbcf-116">To get a reference to the ShdwPattern cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="dbbcf-117">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="dbbcf-117">Cell name:</span></span>  <br/> |<span data-ttu-id="dbbcf-118">ShdwPattern</span><span class="sxs-lookup"><span data-stu-id="dbbcf-118">ShdwPattern</span></span>  <br/> |
   
<span data-ttu-id="dbbcf-119">若要从某个程序按索引获取对 ShdwPattern 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="dbbcf-119">To get a reference to the ShdwPattern cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="dbbcf-120">内容索引：</span><span class="sxs-lookup"><span data-stu-id="dbbcf-120">Section index:</span></span>  <br/> |<span data-ttu-id="dbbcf-121">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="dbbcf-121">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="dbbcf-122">行索引：</span><span class="sxs-lookup"><span data-stu-id="dbbcf-122">Row index:</span></span>  <br/> |<span data-ttu-id="dbbcf-123">**visRowFill**</span><span class="sxs-lookup"><span data-stu-id="dbbcf-123">**visRowFill**</span></span> <br/> |
|<span data-ttu-id="dbbcf-124">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="dbbcf-124">Cell index:</span></span>  <br/> |<span data-ttu-id="dbbcf-125">**visFillShdwPattern**</span><span class="sxs-lookup"><span data-stu-id="dbbcf-125">**visFillShdwPattern**</span></span> <br/> |
   

