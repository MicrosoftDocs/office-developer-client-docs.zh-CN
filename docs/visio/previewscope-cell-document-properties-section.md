---
title: PreviewScope 单元格（“Document Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm820
localization_priority: Normal
ms.assetid: d03ae1b3-da6c-56d3-4f96-6e131c04e93e
description: 确定您的绘图是否包含预览。如果绘图中确实包含预览，则确定该预览是只显示绘图中的第一页还是显示所有页。
ms.openlocfilehash: 865da052f710481c146d3c2692ddf506018be789
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780967"
---
# <a name="previewscope-cell-document-properties-section"></a><span data-ttu-id="201b9-104">PreviewScope 单元格（“Document Properties”部分）</span><span class="sxs-lookup"><span data-stu-id="201b9-104">PreviewScope Cell (Document Properties Section)</span></span>

<span data-ttu-id="201b9-p102">确定您的绘图是否包含预览。如果绘图中确实包含预览，则确定该预览是只显示绘图中的第一页还是显示所有页。</span><span class="sxs-lookup"><span data-stu-id="201b9-p102">Determines whether your drawing includes a preview. If your drawing does include a preview, it determines whether the preview shows the first page only or all of the pages in the drawing.</span></span>
  
|<span data-ttu-id="201b9-107">**值**</span><span class="sxs-lookup"><span data-stu-id="201b9-107">**Value**</span></span>|<span data-ttu-id="201b9-108">**预览范围**</span><span class="sxs-lookup"><span data-stu-id="201b9-108">**Preview scope**</span></span>|<span data-ttu-id="201b9-109">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="201b9-109">**Automation constant**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="201b9-110">0</span><span class="sxs-lookup"><span data-stu-id="201b9-110">0</span></span>  <br/> | <span data-ttu-id="201b9-111">第一页</span><span class="sxs-lookup"><span data-stu-id="201b9-111">First page</span></span>  <br/> |<span data-ttu-id="201b9-112">**visDocPreviewScope1stPage**</span><span class="sxs-lookup"><span data-stu-id="201b9-112">**visDocPreviewScope1stPage**</span></span> <br/> |
| <span data-ttu-id="201b9-113">1</span><span class="sxs-lookup"><span data-stu-id="201b9-113">1</span></span>  <br/> | <span data-ttu-id="201b9-114">无</span><span class="sxs-lookup"><span data-stu-id="201b9-114">None</span></span>  <br/> |<span data-ttu-id="201b9-115">**visDocPreviewScopeNone**</span><span class="sxs-lookup"><span data-stu-id="201b9-115">**visDocPreviewScopeNone**</span></span> <br/> |
| <span data-ttu-id="201b9-116">2</span><span class="sxs-lookup"><span data-stu-id="201b9-116">2</span></span>  <br/> | <span data-ttu-id="201b9-117">所有页</span><span class="sxs-lookup"><span data-stu-id="201b9-117">All pages</span></span>  <br/> |<span data-ttu-id="201b9-118">**visDocPreviewScopeAllPages**</span><span class="sxs-lookup"><span data-stu-id="201b9-118">**visDocPreviewScopeAllPages**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="201b9-119">说明</span><span class="sxs-lookup"><span data-stu-id="201b9-119">Remarks</span></span>

<span data-ttu-id="201b9-120">您还可以在**属性**对话框中的**摘要**选项卡上设置此值 （单击**Office**按钮，单击**信息**选项卡，单击**文档属性**，然后单击**高级属性**）。</span><span class="sxs-lookup"><span data-stu-id="201b9-120">You can also set this value on the **Summary** tab in the **Properties** dialog box (click the **Office** button, click the **Info** tab, click **Document Properties**, and then click **Advanced Properties**).</span></span>
  
<span data-ttu-id="201b9-121">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 PreviewScope 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="201b9-121">To get a reference to the PreviewScope cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="201b9-122">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="201b9-122">Cell name:</span></span>  <br/> | <span data-ttu-id="201b9-123">PreviewScope</span><span class="sxs-lookup"><span data-stu-id="201b9-123">PreviewScope</span></span>  <br/> |
   
<span data-ttu-id="201b9-124">若要从某个程序按索引获取对 PreviewScope 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="201b9-124">To get a reference to the PreviewScope cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="201b9-125">内容索引：</span><span class="sxs-lookup"><span data-stu-id="201b9-125">Section index:</span></span>  <br/> |<span data-ttu-id="201b9-126">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="201b9-126">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="201b9-127">行索引：</span><span class="sxs-lookup"><span data-stu-id="201b9-127">Row index:</span></span>  <br/> |<span data-ttu-id="201b9-128">**visRowDoc**</span><span class="sxs-lookup"><span data-stu-id="201b9-128">**visRowDoc**</span></span> <br/> |
| <span data-ttu-id="201b9-129">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="201b9-129">Cell index:</span></span>  <br/> |<span data-ttu-id="201b9-130">**visDocPreviewScope**</span><span class="sxs-lookup"><span data-stu-id="201b9-130">**visDocPreviewScope**</span></span> <br/> |
   

