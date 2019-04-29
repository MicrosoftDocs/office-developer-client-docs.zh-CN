---
title: NonPrinting 单元格（“Miscellaneous”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251321
localization_priority: Normal
ms.assetid: 59fe0887-2092-4fad-ea38-2aba354f3b92
description: 切换选中形状的打印状态 - 启用或禁用。
ms.openlocfilehash: c3e1fc1b2d91fa4808f8ea89c904218c2236f5b0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437257"
---
# <a name="nonprinting-cell-miscellaneous-section"></a><span data-ttu-id="1bf52-103">NonPrinting 单元格（“Miscellaneous”内容）</span><span class="sxs-lookup"><span data-stu-id="1bf52-103">NonPrinting Cell (Miscellaneous Section)</span></span>

<span data-ttu-id="1bf52-104">切换选中形状的打印状态 - 启用或禁用。</span><span class="sxs-lookup"><span data-stu-id="1bf52-104">Switches printing on and off for the selected shape.</span></span>
  
|<span data-ttu-id="1bf52-105">**值**</span><span class="sxs-lookup"><span data-stu-id="1bf52-105">**Value**</span></span>|<span data-ttu-id="1bf52-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="1bf52-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="1bf52-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="1bf52-107">TRUE</span></span>  <br/> | <span data-ttu-id="1bf52-108">禁用打印，但形状将显示在绘图窗口中。</span><span class="sxs-lookup"><span data-stu-id="1bf52-108">Printing disabled, but the shape will be displayed in the drawing window.</span></span>  <br/> |
| <span data-ttu-id="1bf52-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="1bf52-109">FALSE</span></span>  <br/> | <span data-ttu-id="1bf52-110">启用打印。</span><span class="sxs-lookup"><span data-stu-id="1bf52-110">Printing enabled.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1bf52-111">说明</span><span class="sxs-lookup"><span data-stu-id="1bf52-111">Remarks</span></span>

<span data-ttu-id="1bf52-112">可以通过先选中参考线，再将其 NonPrinting 单元格的值设置为 FALSE 来打印参考线。</span><span class="sxs-lookup"><span data-stu-id="1bf52-112">You can print a guide by selecting it, and then setting the value of its NonPrinting cell to FALSE.</span></span>
  
<span data-ttu-id="1bf52-113">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 NonPrinting 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="1bf52-113">To get a reference to the NonPrinting cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="1bf52-114">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="1bf52-114">Cell name:</span></span>  <br/> | <span data-ttu-id="1bf52-115">打印</span><span class="sxs-lookup"><span data-stu-id="1bf52-115">NonPrinting</span></span>  <br/> |
   
<span data-ttu-id="1bf52-116">要从某个程序按索引获取对 NonPrinting 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="1bf52-116">To get a reference to the NonPrinting cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="1bf52-117">内容索引：</span><span class="sxs-lookup"><span data-stu-id="1bf52-117">Section index:</span></span>  <br/> |<span data-ttu-id="1bf52-118">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="1bf52-118">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="1bf52-119">行索引：</span><span class="sxs-lookup"><span data-stu-id="1bf52-119">Row index:</span></span>  <br/> |<span data-ttu-id="1bf52-120">**visRowMisc**</span><span class="sxs-lookup"><span data-stu-id="1bf52-120">**visRowMisc**</span></span> <br/> |
| <span data-ttu-id="1bf52-121">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="1bf52-121">Cell index:</span></span>  <br/> |<span data-ttu-id="1bf52-122">**visNonPrinting**</span><span class="sxs-lookup"><span data-stu-id="1bf52-122">**visNonPrinting**</span></span> <br/> |
   

