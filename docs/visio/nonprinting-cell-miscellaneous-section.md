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
ms.openlocfilehash: ab00914a9c59cfe94b3f7273f89684f43328b4d8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780791"
---
# <a name="nonprinting-cell-miscellaneous-section"></a><span data-ttu-id="99225-103">NonPrinting 单元格（“Miscellaneous”部分）</span><span class="sxs-lookup"><span data-stu-id="99225-103">NonPrinting Cell (Miscellaneous Section)</span></span>

<span data-ttu-id="99225-104">切换选中形状的打印状态 - 启用或禁用。</span><span class="sxs-lookup"><span data-stu-id="99225-104">Switches printing on and off for the selected shape.</span></span>
  
|<span data-ttu-id="99225-105">**值**</span><span class="sxs-lookup"><span data-stu-id="99225-105">**Value**</span></span>|<span data-ttu-id="99225-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="99225-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="99225-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="99225-107">TRUE</span></span>  <br/> | <span data-ttu-id="99225-108">禁用打印，但形状将显示在绘图窗口中。</span><span class="sxs-lookup"><span data-stu-id="99225-108">Printing disabled, but the shape will be displayed in the drawing window.</span></span>  <br/> |
| <span data-ttu-id="99225-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="99225-109">FALSE</span></span>  <br/> | <span data-ttu-id="99225-110">启用打印。</span><span class="sxs-lookup"><span data-stu-id="99225-110">Printing enabled.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="99225-111">注解</span><span class="sxs-lookup"><span data-stu-id="99225-111">Remarks</span></span>

<span data-ttu-id="99225-112">可以通过先选中参考线，再将其 NonPrinting 单元格的值设置为 FALSE 来打印参考线。</span><span class="sxs-lookup"><span data-stu-id="99225-112">You can print a guide by selecting it, and then setting the value of its NonPrinting cell to FALSE.</span></span>
  
<span data-ttu-id="99225-113">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 NonPrinting 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="99225-113">To get a reference to the NonPrinting cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="99225-114">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="99225-114">Cell name:</span></span>  <br/> | <span data-ttu-id="99225-115">NonPrinting</span><span class="sxs-lookup"><span data-stu-id="99225-115">NonPrinting</span></span>  <br/> |
   
<span data-ttu-id="99225-116">要从某个程序按索引获取对 NonPrinting 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="99225-116">To get a reference to the NonPrinting cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="99225-117">内容索引：</span><span class="sxs-lookup"><span data-stu-id="99225-117">Section index:</span></span>  <br/> |<span data-ttu-id="99225-118">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="99225-118">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="99225-119">行索引：</span><span class="sxs-lookup"><span data-stu-id="99225-119">Row index:</span></span>  <br/> |<span data-ttu-id="99225-120">**visRowMisc**</span><span class="sxs-lookup"><span data-stu-id="99225-120">**visRowMisc**</span></span> <br/> |
| <span data-ttu-id="99225-121">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="99225-121">Cell index:</span></span>  <br/> |<span data-ttu-id="99225-122">**visNonPrinting**</span><span class="sxs-lookup"><span data-stu-id="99225-122">**visNonPrinting**</span></span> <br/> |
   

