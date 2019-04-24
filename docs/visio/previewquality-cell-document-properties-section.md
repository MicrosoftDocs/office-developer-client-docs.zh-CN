---
title: PreviewQuality 单元格（“Document Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm815
localization_priority: Normal
ms.assetid: b7d90666-a1bb-f0de-32da-b2855977f648
description: 确定是以草稿质量显示绘图预览还是以详细视图显示绘图预览。
ms.openlocfilehash: 9db2d3e1eb829bfd2ad787fcfc94cd9ba5abaf9e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356033"
---
# <a name="previewquality-cell-document-properties-section"></a><span data-ttu-id="eb494-103">PreviewQuality 单元格（“Document Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="eb494-103">PreviewQuality Cell (Document Properties Section)</span></span>

<span data-ttu-id="eb494-104">确定是以草稿质量显示绘图预览还是以详细视图显示绘图预览。</span><span class="sxs-lookup"><span data-stu-id="eb494-104">Determines whether the drawing preview is draft quality or detailed.</span></span>
  
|<span data-ttu-id="eb494-105">**值**</span><span class="sxs-lookup"><span data-stu-id="eb494-105">**Value**</span></span>|<span data-ttu-id="eb494-106">**预览质量**</span><span class="sxs-lookup"><span data-stu-id="eb494-106">**Preview quality**</span></span>|<span data-ttu-id="eb494-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="eb494-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="eb494-108">0</span><span class="sxs-lookup"><span data-stu-id="eb494-108">0</span></span>  <br/> | <span data-ttu-id="eb494-109">Draft</span><span class="sxs-lookup"><span data-stu-id="eb494-109">Draft</span></span>  <br/> |<span data-ttu-id="eb494-110">**visDocPreviewQualityDraft**</span><span class="sxs-lookup"><span data-stu-id="eb494-110">**visDocPreviewQualityDraft**</span></span> <br/> |
| <span data-ttu-id="eb494-111">1</span><span class="sxs-lookup"><span data-stu-id="eb494-111">1</span></span>  <br/> | <span data-ttu-id="eb494-112">具体</span><span class="sxs-lookup"><span data-stu-id="eb494-112">Detailed</span></span>  <br/> |<span data-ttu-id="eb494-113">**visDocPreviewQualityDetailed**</span><span class="sxs-lookup"><span data-stu-id="eb494-113">**visDocPreviewQualityDetailed**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="eb494-114">注解</span><span class="sxs-lookup"><span data-stu-id="eb494-114">Remarks</span></span>

<span data-ttu-id="eb494-115">您还可以在 "**属性**" 对话框中的 "**摘要**" 选项卡 (单击 " **Office** " 按钮, 依次单击 "**信息**" 选项卡、"**文档属性**" 和 "**高级属性**") 中设置此值。</span><span class="sxs-lookup"><span data-stu-id="eb494-115">You can also set this value on the **Summary** tab in the **Properties** dialog box (click the **Office** button, click the **Info** tab, click **Document Properties**, and then click **Advanced Properties**).</span></span>
  
<span data-ttu-id="eb494-116">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 PreviewQuality 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="eb494-116">To get a reference to the PreviewQuality cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="eb494-117">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="eb494-117">Cell name:</span></span>  <br/> | <span data-ttu-id="eb494-118">PreviewQuality</span><span class="sxs-lookup"><span data-stu-id="eb494-118">PreviewQuality</span></span>  <br/> |
   
<span data-ttu-id="eb494-119">若要从某个程序按索引获取对 PreviewQuality 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="eb494-119">To get a reference to the PreviewQuality cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="eb494-120">内容索引：</span><span class="sxs-lookup"><span data-stu-id="eb494-120">Section index:</span></span>  <br/> |<span data-ttu-id="eb494-121">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="eb494-121">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="eb494-122">行索引：</span><span class="sxs-lookup"><span data-stu-id="eb494-122">Row index:</span></span>  <br/> |<span data-ttu-id="eb494-123">**visRowDoc**</span><span class="sxs-lookup"><span data-stu-id="eb494-123">**visRowDoc**</span></span> <br/> |
| <span data-ttu-id="eb494-124">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="eb494-124">Cell index:</span></span>  <br/> |<span data-ttu-id="eb494-125">**visDocPreviewQuality**</span><span class="sxs-lookup"><span data-stu-id="eb494-125">**visDocPreviewQuality**</span></span> <br/> |
   

