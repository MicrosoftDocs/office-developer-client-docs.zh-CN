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
ms.openlocfilehash: cccc6028de21299942e62c53aba48622baa95f98
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780577"
---
# <a name="linepattern-cell-line-format-section"></a><span data-ttu-id="0a60a-104">LinePattern 单元格（“Line Format”部分）</span><span class="sxs-lookup"><span data-stu-id="0a60a-104">LinePattern Cell (Line Format Section)</span></span>

<span data-ttu-id="0a60a-p102">确定形状的线型。在 LinePattern 单元格中输入的值是一个数字，此数字是线型集合中的索引。</span><span class="sxs-lookup"><span data-stu-id="0a60a-p102">Determines the line pattern of the shape. The value entered in the LinePattern cell is a number that is an index into a collection of line patterns.</span></span>
  
|<span data-ttu-id="0a60a-107">**值**</span><span class="sxs-lookup"><span data-stu-id="0a60a-107">**Value**</span></span>|<span data-ttu-id="0a60a-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="0a60a-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0a60a-109">0</span><span class="sxs-lookup"><span data-stu-id="0a60a-109">0</span></span>  <br/> |<span data-ttu-id="0a60a-110">没有线型</span><span class="sxs-lookup"><span data-stu-id="0a60a-110">No line pattern</span></span>  <br/> |
|<span data-ttu-id="0a60a-111">1</span><span class="sxs-lookup"><span data-stu-id="0a60a-111">1</span></span>  <br/> |<span data-ttu-id="0a60a-112">实线</span><span class="sxs-lookup"><span data-stu-id="0a60a-112">Solid</span></span>  <br/> |
|<span data-ttu-id="0a60a-113">2-23</span><span class="sxs-lookup"><span data-stu-id="0a60a-113">2 - 23</span></span>  <br/> |<span data-ttu-id="0a60a-114">各种线型</span><span class="sxs-lookup"><span data-stu-id="0a60a-114">Assorted line patterns</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0a60a-115">注解</span><span class="sxs-lookup"><span data-stu-id="0a60a-115">Remarks</span></span>

<span data-ttu-id="0a60a-116">可以在 **“线条”** 对话框中查看线型集合（在 **“开始”** 选项卡上的 **“形状”** 组中，单击 **“线条”**，指向 **“虚线”**，然后单击 **“其他线条”**）。</span><span class="sxs-lookup"><span data-stu-id="0a60a-116">You can view the line pattern collection in the **Line** dialog box (on the **Home** tab, in the **Shape** group, click **Line**, point to **Dashes**, and then click **More Lines**).</span></span>
  
<span data-ttu-id="0a60a-117">若要指定自定义的线型，请使用本单元格中的 USE 函数。</span><span class="sxs-lookup"><span data-stu-id="0a60a-117">To specify a custom line pattern, use the USE function in this cell.</span></span>
  
<span data-ttu-id="0a60a-118">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 LinePattern 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="0a60a-118">To get a reference to the LinePattern cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="0a60a-119">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="0a60a-119">Cell name:</span></span>  <br/> |<span data-ttu-id="0a60a-120">LinePattern</span><span class="sxs-lookup"><span data-stu-id="0a60a-120">LinePattern</span></span>  <br/> |
   
<span data-ttu-id="0a60a-121">若要从某个程序按索引获取对 LinePattern 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="0a60a-121">To get a reference to the LinePattern cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="0a60a-122">内容索引：</span><span class="sxs-lookup"><span data-stu-id="0a60a-122">Section index:</span></span>  <br/> |<span data-ttu-id="0a60a-123">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="0a60a-123">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="0a60a-124">行索引：</span><span class="sxs-lookup"><span data-stu-id="0a60a-124">Row index:</span></span>  <br/> |<span data-ttu-id="0a60a-125">**visRowLine**</span><span class="sxs-lookup"><span data-stu-id="0a60a-125">**visRowLine**</span></span> <br/> |
|<span data-ttu-id="0a60a-126">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="0a60a-126">Cell index:</span></span>  <br/> |<span data-ttu-id="0a60a-127">**visLinePattern**</span><span class="sxs-lookup"><span data-stu-id="0a60a-127">**visLinePattern**</span></span> <br/> |
   

