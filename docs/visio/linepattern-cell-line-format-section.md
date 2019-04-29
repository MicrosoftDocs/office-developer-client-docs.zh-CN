---
title: LinePattern 单元格（“Line Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm560
localization_priority: Normal
ms.assetid: a416762b-7294-c99f-d9f1-332c3ed35dff
description: 确定形状的线型。在 LinePattern 单元格中输入的值是一个数字，此数字是线型集合中的索引。
ms.openlocfilehash: eec5bed18777f7822f9544d59dce7722f2f732bb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416753"
---
# <a name="linepattern-cell-line-format-section"></a><span data-ttu-id="f4127-104">LinePattern 单元格（“Line Format”内容）</span><span class="sxs-lookup"><span data-stu-id="f4127-104">LinePattern Cell (Line Format Section)</span></span>

<span data-ttu-id="f4127-p102">确定形状的线型。在 LinePattern 单元格中输入的值是一个数字，此数字是线型集合中的索引。</span><span class="sxs-lookup"><span data-stu-id="f4127-p102">Determines the line pattern of the shape. The value entered in the LinePattern cell is a number that is an index into a collection of line patterns.</span></span>
  
|<span data-ttu-id="f4127-107">**值**</span><span class="sxs-lookup"><span data-stu-id="f4127-107">**Value**</span></span>|<span data-ttu-id="f4127-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="f4127-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f4127-109">0</span><span class="sxs-lookup"><span data-stu-id="f4127-109">0</span></span>  <br/> |<span data-ttu-id="f4127-110">没有线型</span><span class="sxs-lookup"><span data-stu-id="f4127-110">No line pattern</span></span>  <br/> |
|<span data-ttu-id="f4127-111">1</span><span class="sxs-lookup"><span data-stu-id="f4127-111">1</span></span>  <br/> |<span data-ttu-id="f4127-112">实线</span><span class="sxs-lookup"><span data-stu-id="f4127-112">Solid</span></span>  <br/> |
|<span data-ttu-id="f4127-113">2 - 23</span><span class="sxs-lookup"><span data-stu-id="f4127-113">2 - 23</span></span>  <br/> |<span data-ttu-id="f4127-114">各种线型</span><span class="sxs-lookup"><span data-stu-id="f4127-114">Assorted line patterns</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f4127-115">说明</span><span class="sxs-lookup"><span data-stu-id="f4127-115">Remarks</span></span>

<span data-ttu-id="f4127-116">可以在 **“线条”** 对话框中查看线型集合（在 **“开始”** 选项卡上的 **“形状”** 组中，单击 **“线条”**，指向 **“虚线”**，然后单击 **“其他线条”**）。</span><span class="sxs-lookup"><span data-stu-id="f4127-116">You can view the line pattern collection in the **Line** dialog box (on the **Home** tab, in the **Shape** group, click **Line**, point to **Dashes**, and then click **More Lines**).</span></span>
  
<span data-ttu-id="f4127-117">若要指定自定义的线型，请使用本单元格中的 USE 函数。</span><span class="sxs-lookup"><span data-stu-id="f4127-117">To specify a custom line pattern, use the USE function in this cell.</span></span>
  
<span data-ttu-id="f4127-118">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 LinePattern 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="f4127-118">To get a reference to the LinePattern cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f4127-119">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="f4127-119">Cell name:</span></span>  <br/> |<span data-ttu-id="f4127-120">LinePattern</span><span class="sxs-lookup"><span data-stu-id="f4127-120">LinePattern</span></span>  <br/> |
   
<span data-ttu-id="f4127-121">若要从某个程序按索引获取对 LinePattern 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="f4127-121">To get a reference to the LinePattern cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f4127-122">内容索引：</span><span class="sxs-lookup"><span data-stu-id="f4127-122">Section index:</span></span>  <br/> |<span data-ttu-id="f4127-123">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="f4127-123">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="f4127-124">行索引：</span><span class="sxs-lookup"><span data-stu-id="f4127-124">Row index:</span></span>  <br/> |<span data-ttu-id="f4127-125">**visRowLine**</span><span class="sxs-lookup"><span data-stu-id="f4127-125">**visRowLine**</span></span> <br/> |
|<span data-ttu-id="f4127-126">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="f4127-126">Cell index:</span></span>  <br/> |<span data-ttu-id="f4127-127">**visLinePattern**</span><span class="sxs-lookup"><span data-stu-id="f4127-127">**visLinePattern**</span></span> <br/> |
   

