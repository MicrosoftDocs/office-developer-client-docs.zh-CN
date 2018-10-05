---
title: ButtonFace 单元格（“Action Tags”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60026
localization_priority: Normal
ms.assetid: 26f370e1-5193-f47d-7b60-3597975be650
description: 包含动作标记按钮上显示的按钮外表图像的 ID。
ms.openlocfilehash: e74b3281d894cebd8491112181198d427f0d337f
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25385478"
---
# <a name="buttonface-cell-action-tags-section"></a><span data-ttu-id="46ec5-103">ButtonFace 单元格（“Action Tags”部分）</span><span class="sxs-lookup"><span data-stu-id="46ec5-103">ButtonFace Cell (Action Tags Section)</span></span>

<span data-ttu-id="46ec5-104">包含动作标记按钮上显示的按钮外表图像的 ID。</span><span class="sxs-lookup"><span data-stu-id="46ec5-104">Contains the ID of the button face image that appears on the action tag button.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="46ec5-105">在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。</span><span class="sxs-lookup"><span data-stu-id="46ec5-105">In previous versions of Microsoft Visio, action tags are called smart tags.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="46ec5-106">注解</span><span class="sxs-lookup"><span data-stu-id="46ec5-106">Remarks</span></span>

<span data-ttu-id="46ec5-p101">ButtonFace 单元格中包含的字符串表示 Microsoft Office 按钮外表图像的 ID。值为 0（零）或空白时默认表示标准的动作标记“i”信息按钮</span><span class="sxs-lookup"><span data-stu-id="46ec5-p101">The string contained in the ButtonFace cell represents the ID of a Microsoft Office button face image. A value of 0 (zero) or blank defaults to the standard action tag "i" info button</span></span> ![标准的动作标记"i"info 按钮](media/InfoPS_ZA10180114.gif)<span data-ttu-id="46ec5-110">.</span><span class="sxs-lookup"><span data-stu-id="46ec5-110"></span></span>
  
<span data-ttu-id="46ec5-111">可在 ButtonFace 单元格的 Id 是与**CommandBarButton**对象的**FaceID**属性一起使用的 Id 相同。</span><span class="sxs-lookup"><span data-stu-id="46ec5-111">The IDs that can be used in the ButtonFace cell are the same as the IDs used with the **FaceID** property of a **CommandBarButton** object.</span></span> <span data-ttu-id="46ec5-112">关于这些 Id 的详细信息，请在 MSDN 上中搜索"命令栏按钮图像处理"。</span><span class="sxs-lookup"><span data-stu-id="46ec5-112">For more details about these IDs, search for "working with command bar button images" on MSDN.</span></span> 
  
<span data-ttu-id="46ec5-113">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取有关 ButtonFace 单元格的参考内容，请使用：</span><span class="sxs-lookup"><span data-stu-id="46ec5-113">To get a reference to the ButtonFace cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="46ec5-114">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="46ec5-114">Cell name:</span></span>  <br/> | <span data-ttu-id="46ec5-115">智能标记。</span><span class="sxs-lookup"><span data-stu-id="46ec5-115">SmartTags.</span></span>  <span data-ttu-id="46ec5-116">*名称*。ButtonFace 其中智能标记。</span><span class="sxs-lookup"><span data-stu-id="46ec5-116">*name*  .ButtonFace           where SmartTags.</span></span> <span data-ttu-id="46ec5-117">*name*是动作标记行的名称</span><span class="sxs-lookup"><span data-stu-id="46ec5-117">*name*  is the name of the action tag row</span></span>  <br/> |
   
<span data-ttu-id="46ec5-118">要从某个程序按索引获取有关 ButtonFace 单元格的参考内容，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="46ec5-118">To get a reference to the ButtonFace cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="46ec5-119">内容索引：</span><span class="sxs-lookup"><span data-stu-id="46ec5-119">Section index:</span></span>  <br/> |<span data-ttu-id="46ec5-120">**visSectionSmartTag**</span><span class="sxs-lookup"><span data-stu-id="46ec5-120">**visSectionSmartTag**</span></span> <br/> |
| <span data-ttu-id="46ec5-121">行索引：</span><span class="sxs-lookup"><span data-stu-id="46ec5-121">Row index:</span></span>  <br/> |<span data-ttu-id="46ec5-122">**visRowSmartTag** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="46ec5-122">**visRowSmartTag** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="46ec5-123">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="46ec5-123">Cell index:</span></span>  <br/> |<span data-ttu-id="46ec5-124">**visSmartTagButtonFace**</span><span class="sxs-lookup"><span data-stu-id="46ec5-124">**visSmartTagButtonFace**</span></span> <br/> |
   

