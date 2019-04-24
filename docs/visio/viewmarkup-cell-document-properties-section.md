---
title: ViewMarkup 单元格（“Document Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1030802
localization_priority: Normal
ms.assetid: 6c956266-8266-3312-5a68-cc9d8bdb8cd9
description: 确定绘图窗口中是否显示标记。
ms.openlocfilehash: eeccdd0d14bf28630937b0e480822abb6fb19da5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355823"
---
# <a name="viewmarkup-cell-document-properties-section"></a><span data-ttu-id="a0f17-103">ViewMarkup 单元格（“Document Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="a0f17-103">ViewMarkup Cell (Document Properties Section)</span></span>

<span data-ttu-id="a0f17-104">确定绘图窗口中是否显示标记。</span><span class="sxs-lookup"><span data-stu-id="a0f17-104">Determines whether markup appears in the drawing window.</span></span> 
  
|<span data-ttu-id="a0f17-105">**Value**</span><span class="sxs-lookup"><span data-stu-id="a0f17-105">**Value**</span></span>|<span data-ttu-id="a0f17-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="a0f17-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a0f17-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="a0f17-107">TRUE</span></span>  <br/> |<span data-ttu-id="a0f17-108">在绘图上显示标记。</span><span class="sxs-lookup"><span data-stu-id="a0f17-108">Markup is displayed on the drawing.</span></span>  <br/> |
|<span data-ttu-id="a0f17-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="a0f17-109">FALSE</span></span>  <br/> |<span data-ttu-id="a0f17-110">不显示标记（默认值）。</span><span class="sxs-lookup"><span data-stu-id="a0f17-110">Markup is not displayed (the default).</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a0f17-111">注解</span><span class="sxs-lookup"><span data-stu-id="a0f17-111">Remarks</span></span>

 <span data-ttu-id="a0f17-112">标记跟踪打开时 (AddMarkup 单元格为 true), 即使关闭了标记跟踪 (AddMarkup 单元格为 FALSE), ViewMarkup 单元格也会自动设置为 true, 并且仍为 true。</span><span class="sxs-lookup"><span data-stu-id="a0f17-112">When markup tracking is turned on (AddMarkup cell is TRUE), the ViewMarkup cell is automatically set to TRUE and remains TRUE even after markup tracking has been turned off (AddMarkup cell is FALSE).</span></span> <span data-ttu-id="a0f17-113">当 AddMarkup 单元格为 TRUE 时，将忽略 ViewMarkup 单元格中的值。</span><span class="sxs-lookup"><span data-stu-id="a0f17-113">The value in the ViewMarkup cell is ignored when the AddMarkup cell is TRUE.</span></span> 
  
<span data-ttu-id="a0f17-114">在绘图中插入注释时，ViewMarkup 单元格也将设置为 TRUE（无论是否启用标记跟踪），并且必须设置为 TRUE 才能在绘图中看到注释。</span><span class="sxs-lookup"><span data-stu-id="a0f17-114">The ViewMarkup cell is also set to TRUE when comments are inserted in a drawing (whether or not markup tracking is turned on) and must be TRUE to see comments in the drawing.</span></span>
  
<span data-ttu-id="a0f17-115">此单元格对应于 **“审阅”** 选项卡上 **“标记”** 组中的 **“显示标记贴”** 命令。</span><span class="sxs-lookup"><span data-stu-id="a0f17-115">This cell corresponds to the **Show Markup** command in the **Markup** group on the **Review** tab.</span></span> 
  
<span data-ttu-id="a0f17-116">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ViewMarkup 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="a0f17-116">To get a reference to the ViewMarkup cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a0f17-117">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="a0f17-117">Cell name:</span></span>  <br/> |<span data-ttu-id="a0f17-118">ViewMarkup</span><span class="sxs-lookup"><span data-stu-id="a0f17-118">ViewMarkup</span></span>  <br/> |
   
<span data-ttu-id="a0f17-119">若要从某个程序按索引获取对 ViewMarkup 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="a0f17-119">To get a reference to the ViewMarkup cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a0f17-120">内容索引：</span><span class="sxs-lookup"><span data-stu-id="a0f17-120">Section index:</span></span>  <br/> |<span data-ttu-id="a0f17-121">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="a0f17-121">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="a0f17-122">行索引：</span><span class="sxs-lookup"><span data-stu-id="a0f17-122">Row index:</span></span>  <br/> |<span data-ttu-id="a0f17-123">**visRowDoc**</span><span class="sxs-lookup"><span data-stu-id="a0f17-123">**visRowDoc**</span></span> <br/> |
|<span data-ttu-id="a0f17-124">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="a0f17-124">Cell index:</span></span>  <br/> |<span data-ttu-id="a0f17-125">**visDocViewMarkup**</span><span class="sxs-lookup"><span data-stu-id="a0f17-125">**visDocViewMarkup**</span></span> <br/> |
   

