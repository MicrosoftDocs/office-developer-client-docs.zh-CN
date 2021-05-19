---
title: AddMarkup 单元格（“Document Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1030801
localization_priority: Normal
ms.assetid: 46146424-b4c9-2240-36c0-19bb35ec51d1
description: 指示是否正对文档进行审阅以便加标记。
ms.openlocfilehash: 4e0860639b0d89fce2c35a8947bd5ac00fcc63e5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427631"
---
# <a name="addmarkup-cell-document-properties-section"></a><span data-ttu-id="f8622-103">AddMarkup 单元格（“Document Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="f8622-103">AddMarkup Cell (Document Properties Section)</span></span>

<span data-ttu-id="f8622-104">指示是否正对文档进行审阅以便加标记。</span><span class="sxs-lookup"><span data-stu-id="f8622-104">Indicates whether the document is being reviewed for markup.</span></span>
  
|<span data-ttu-id="f8622-105">**值**</span><span class="sxs-lookup"><span data-stu-id="f8622-105">**Value**</span></span>|<span data-ttu-id="f8622-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="f8622-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f8622-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="f8622-107">TRUE</span></span>  <br/> |<span data-ttu-id="f8622-108">正在对文档进行审阅。</span><span class="sxs-lookup"><span data-stu-id="f8622-108">Document is being reviewed.</span></span>  <br/> |
|<span data-ttu-id="f8622-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="f8622-109">FALSE</span></span>  <br/> |<span data-ttu-id="f8622-110">未对文档进行审阅（默认值）。</span><span class="sxs-lookup"><span data-stu-id="f8622-110">Document is not being reviewed (the default).</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f8622-111">备注</span><span class="sxs-lookup"><span data-stu-id="f8622-111">Remarks</span></span>

<span data-ttu-id="f8622-112">当 AddMarkup 单元格设置为 TRUE 时，审阅者正在添加标记，并且更改将应用于标记贴页而不是原始绘图页。</span><span class="sxs-lookup"><span data-stu-id="f8622-112">When the AddMarkup cell is set to TRUE, the reviewer is adding markup and changes are applied to markup overlay pages, not to original drawing pages.</span></span> <span data-ttu-id="f8622-113">当 AddMarkup 单元格为 FALSE 时，将禁用标记跟踪，并且更改将应用于原始绘图页。</span><span class="sxs-lookup"><span data-stu-id="f8622-113">When the AddMarkup cell is FALSE, markup tracking is off and changes are applied to the original drawing pages.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f8622-114">可以使用 GUARD 函数阻止在文档上标记。</span><span class="sxs-lookup"><span data-stu-id="f8622-114">You can prevent markup on your documents by using the GUARD function.</span></span> <span data-ttu-id="f8622-115">如果 AddMarkup 单元格包含公式 =GUARD (FALSE) ，则 **"跟踪标记** "命令处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="f8622-115">If the AddMarkup cell contains the formula =GUARD(FALSE), the **Track Markup** command is disabled.</span></span> 
  
<span data-ttu-id="f8622-116">此设置对应于 **“审阅”** 选项卡上的 **“标记”** 组中的 **“跟踪标记”** 命令设置。</span><span class="sxs-lookup"><span data-stu-id="f8622-116">This setting corresponds to the **Track Markup** command setting in the **Markup** group on the **Review** tab.</span></span> 
  
<span data-ttu-id="f8622-117">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 AddMarkup 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="f8622-117">To get a reference to the AddMarkup cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f8622-118">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="f8622-118">Cell name:</span></span>  <br/> |<span data-ttu-id="f8622-119">AddMarkup</span><span class="sxs-lookup"><span data-stu-id="f8622-119">AddMarkup</span></span>  <br/> |
   
<span data-ttu-id="f8622-120">若要从某个程序按索引获取对 AddMarkup 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="f8622-120">To get a reference to the AddMarkup cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f8622-121">内容索引：</span><span class="sxs-lookup"><span data-stu-id="f8622-121">Section index:</span></span>  <br/> |<span data-ttu-id="f8622-122">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="f8622-122">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="f8622-123">行索引：</span><span class="sxs-lookup"><span data-stu-id="f8622-123">Row index:</span></span>  <br/> |<span data-ttu-id="f8622-124">**visRowDoc**</span><span class="sxs-lookup"><span data-stu-id="f8622-124">**visRowDoc**</span></span> <br/> |
|<span data-ttu-id="f8622-125">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="f8622-125">Cell index:</span></span>  <br/> |<span data-ttu-id="f8622-126">**visDocAddMarkup**</span><span class="sxs-lookup"><span data-stu-id="f8622-126">**visDocAddMarkup**</span></span> <br/> |
   

