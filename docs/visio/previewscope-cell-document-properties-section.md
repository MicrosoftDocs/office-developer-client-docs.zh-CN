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
ms.openlocfilehash: 34dbc9ac02032b2cb5cb6373c3c6361e3d822312
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426504"
---
# <a name="previewscope-cell-document-properties-section"></a><span data-ttu-id="068de-104">PreviewScope 单元格（“Document Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="068de-104">PreviewScope Cell (Document Properties Section)</span></span>

<span data-ttu-id="068de-p102">确定您的绘图是否包含预览。如果绘图中确实包含预览，则确定该预览是只显示绘图中的第一页还是显示所有页。</span><span class="sxs-lookup"><span data-stu-id="068de-p102">Determines whether your drawing includes a preview. If your drawing does include a preview, it determines whether the preview shows the first page only or all of the pages in the drawing.</span></span>
  
|<span data-ttu-id="068de-107">**值**</span><span class="sxs-lookup"><span data-stu-id="068de-107">**Value**</span></span>|<span data-ttu-id="068de-108">**预览范围**</span><span class="sxs-lookup"><span data-stu-id="068de-108">**Preview scope**</span></span>|<span data-ttu-id="068de-109">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="068de-109">**Automation constant**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="068de-110">0</span><span class="sxs-lookup"><span data-stu-id="068de-110">0</span></span>  <br/> | <span data-ttu-id="068de-111">第一页</span><span class="sxs-lookup"><span data-stu-id="068de-111">First page</span></span>  <br/> |<span data-ttu-id="068de-112">**visDocPreviewScope1stPage**</span><span class="sxs-lookup"><span data-stu-id="068de-112">**visDocPreviewScope1stPage**</span></span> <br/> |
| <span data-ttu-id="068de-113">1</span><span class="sxs-lookup"><span data-stu-id="068de-113">1</span></span>  <br/> | <span data-ttu-id="068de-114">无</span><span class="sxs-lookup"><span data-stu-id="068de-114">None</span></span>  <br/> |<span data-ttu-id="068de-115">**visDocPreviewScopeNone**</span><span class="sxs-lookup"><span data-stu-id="068de-115">**visDocPreviewScopeNone**</span></span> <br/> |
| <span data-ttu-id="068de-116">2</span><span class="sxs-lookup"><span data-stu-id="068de-116">2</span></span>  <br/> | <span data-ttu-id="068de-117">所有页</span><span class="sxs-lookup"><span data-stu-id="068de-117">All pages</span></span>  <br/> |<span data-ttu-id="068de-118">**visDocPreviewScopeAllPages**</span><span class="sxs-lookup"><span data-stu-id="068de-118">**visDocPreviewScopeAllPages**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="068de-119">备注</span><span class="sxs-lookup"><span data-stu-id="068de-119">Remarks</span></span>

<span data-ttu-id="068de-120">您还可以在"属性"对话框的"摘要"选项卡上设置此值 (单击 **"Office"** 按钮，单击"信息"选项卡，单击"文档属性"，然后单击"高级属性) "。 </span><span class="sxs-lookup"><span data-stu-id="068de-120">You can also set this value on the **Summary** tab in the **Properties** dialog box (click the **Office** button, click the **Info** tab, click **Document Properties**, and then click **Advanced Properties**).</span></span>
  
<span data-ttu-id="068de-121">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 PreviewScope 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="068de-121">To get a reference to the PreviewScope cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="068de-122">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="068de-122">Cell name:</span></span>  <br/> | <span data-ttu-id="068de-123">PreviewScope</span><span class="sxs-lookup"><span data-stu-id="068de-123">PreviewScope</span></span>  <br/> |
   
<span data-ttu-id="068de-124">若要从某个程序按索引获取对 PreviewScope 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="068de-124">To get a reference to the PreviewScope cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="068de-125">内容索引：</span><span class="sxs-lookup"><span data-stu-id="068de-125">Section index:</span></span>  <br/> |<span data-ttu-id="068de-126">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="068de-126">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="068de-127">行索引：</span><span class="sxs-lookup"><span data-stu-id="068de-127">Row index:</span></span>  <br/> |<span data-ttu-id="068de-128">**visRowDoc**</span><span class="sxs-lookup"><span data-stu-id="068de-128">**visRowDoc**</span></span> <br/> |
| <span data-ttu-id="068de-129">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="068de-129">Cell index:</span></span>  <br/> |<span data-ttu-id="068de-130">**visDocPreviewScope**</span><span class="sxs-lookup"><span data-stu-id="068de-130">**visDocPreviewScope**</span></span> <br/> |
   

