---
title: ResizePage 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm850
localization_priority: Normal
ms.assetid: d63fe874-1027-3436-dbc1-73e722bce22e
description: 确定在使用“配置布局”对话框（在“设计”选项卡上的“布局”组中，单击“重新布局页面”，然后单击“其他布局选项”）排放形状后是否放大页面以装入绘图。
ms.openlocfilehash: 8d0001ce35808f8c5f11068ed78865ce992af5cb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438090"
---
# <a name="resizepage-cell-page-layout-section"></a><span data-ttu-id="bda64-103">ResizePage 单元格（“Page Layout”内容）</span><span class="sxs-lookup"><span data-stu-id="bda64-103">ResizePage Cell (Page Layout Section)</span></span>

<span data-ttu-id="bda64-104">确定在使用"设计"选项卡上的"配置布局"对话框 (（在"布局"组中，单击"重新布局页面"，然后单击"其他布局选项") ）将形状布局后是否放大页面以将绘图括起来。  </span><span class="sxs-lookup"><span data-stu-id="bda64-104">Determines whether to enlarge the page to enclose the drawing after laying out shapes by using the **Configure Layout** dialog box (on the **Design** tab, in the **Layout** group, click **Re-Layout** Page, and then click **More Layout Options**).</span></span>
  
|<span data-ttu-id="bda64-105">**值**</span><span class="sxs-lookup"><span data-stu-id="bda64-105">**Value**</span></span>|<span data-ttu-id="bda64-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="bda64-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="bda64-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="bda64-107">TRUE</span></span>  <br/> | <span data-ttu-id="bda64-108">放大页面。</span><span class="sxs-lookup"><span data-stu-id="bda64-108">Enlarge the page.</span></span>  <br/> |
| <span data-ttu-id="bda64-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="bda64-109">FALSE</span></span>  <br/> | <span data-ttu-id="bda64-110">不放大页面。</span><span class="sxs-lookup"><span data-stu-id="bda64-110">Do not enlarge the page.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="bda64-111">备注</span><span class="sxs-lookup"><span data-stu-id="bda64-111">Remarks</span></span>

<span data-ttu-id="bda64-112">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ResizePage 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="bda64-112">To get a reference to the ResizePage cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="bda64-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="bda64-113">Cell name:</span></span>  <br/> | <span data-ttu-id="bda64-114">ResizePage</span><span class="sxs-lookup"><span data-stu-id="bda64-114">ResizePage</span></span>  <br/> |
   
<span data-ttu-id="bda64-115">若要从某个程序按索引获取对 ResizePage 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="bda64-115">To get a reference to the ResizePage cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="bda64-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="bda64-116">Section index:</span></span>  <br/> |<span data-ttu-id="bda64-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="bda64-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="bda64-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="bda64-118">Row index:</span></span>  <br/> |<span data-ttu-id="bda64-119">**visRowPageLayout**</span><span class="sxs-lookup"><span data-stu-id="bda64-119">**visRowPageLayout**</span></span> <br/> |
| <span data-ttu-id="bda64-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="bda64-120">Cell index:</span></span>  <br/> |<span data-ttu-id="bda64-121">**visPLOResizePage**</span><span class="sxs-lookup"><span data-stu-id="bda64-121">**visPLOResizePage**</span></span> <br/> |
   

