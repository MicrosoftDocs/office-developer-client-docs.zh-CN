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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32337534"
---
# <a name="buttonface-cell-action-tags-section"></a><span data-ttu-id="cac9f-103">ButtonFace 单元格（“Action Tags”内容）</span><span class="sxs-lookup"><span data-stu-id="cac9f-103">ButtonFace Cell (Action Tags Section)</span></span>

<span data-ttu-id="cac9f-104">包含动作标记按钮上显示的按钮外表图像的 ID。</span><span class="sxs-lookup"><span data-stu-id="cac9f-104">Contains the ID of the button face image that appears on the action tag button.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="cac9f-105">在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。</span><span class="sxs-lookup"><span data-stu-id="cac9f-105">In previous versions of Microsoft Visio, action tags are called smart tags.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="cac9f-106">注解</span><span class="sxs-lookup"><span data-stu-id="cac9f-106">Remarks</span></span>

<span data-ttu-id="cac9f-107">ButtonFace 单元格中包含的字符串表示 Microsoft Office 按钮外表图像的 ID。</span><span class="sxs-lookup"><span data-stu-id="cac9f-107">The string contained in the ButtonFace cell represents the ID of a Microsoft Office button face image.</span></span> <span data-ttu-id="cac9f-108">值为 0 (零) 或空白默认值为标准操作标记 "i" 信息按钮</span><span class="sxs-lookup"><span data-stu-id="cac9f-108">A value of 0 (zero) or blank defaults to the standard action tag "i" info button</span></span> ![标准操作标记 "i" 信息按钮](media/InfoPS_ZA10180114.gif)<span data-ttu-id="cac9f-110">.</span><span class="sxs-lookup"><span data-stu-id="cac9f-110"></span></span>
  
<span data-ttu-id="cac9f-111">ButtonFace 单元格中可以使用的 ID 与用于 **CommandBarButton** 对象的 **FaceID** 属性的 ID 相同。</span><span class="sxs-lookup"><span data-stu-id="cac9f-111">The IDs that can be used in the ButtonFace cell are the same as the IDs used with the **FaceID** property of a **CommandBarButton** object.</span></span> <span data-ttu-id="cac9f-112">有关这些 id 的更多详细信息, 请在 MSDN 上搜索 "使用命令栏按钮图像"。</span><span class="sxs-lookup"><span data-stu-id="cac9f-112">For more details about these IDs, search for "working with command bar button images" on MSDN.</span></span> 
  
<span data-ttu-id="cac9f-113">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取有关 ButtonFace 单元格的参考内容，请使用：</span><span class="sxs-lookup"><span data-stu-id="cac9f-113">To get a reference to the ButtonFace cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="cac9f-114">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="cac9f-114">Cell name:</span></span>  <br/> | <span data-ttu-id="cac9f-115">SmartTags.</span><span class="sxs-lookup"><span data-stu-id="cac9f-115">SmartTags.</span></span>  <span data-ttu-id="cac9f-116">*名称*。ButtonFace 其中的智能标记。</span><span class="sxs-lookup"><span data-stu-id="cac9f-116">*name*  .ButtonFace           where SmartTags.</span></span> <span data-ttu-id="cac9f-117">*name*是操作标记行的名称</span><span class="sxs-lookup"><span data-stu-id="cac9f-117">*name*  is the name of the action tag row</span></span>  <br/> |
   
<span data-ttu-id="cac9f-118">要从某个程序按索引获取有关 ButtonFace 单元格的参考内容，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="cac9f-118">To get a reference to the ButtonFace cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="cac9f-119">内容索引：</span><span class="sxs-lookup"><span data-stu-id="cac9f-119">Section index:</span></span>  <br/> |<span data-ttu-id="cac9f-120">**visSectionSmartTag**</span><span class="sxs-lookup"><span data-stu-id="cac9f-120">**visSectionSmartTag**</span></span> <br/> |
| <span data-ttu-id="cac9f-121">行索引：</span><span class="sxs-lookup"><span data-stu-id="cac9f-121">Row index:</span></span>  <br/> |<span data-ttu-id="cac9f-122">**visRowSmartTag** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="cac9f-122">**visRowSmartTag** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="cac9f-123">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="cac9f-123">Cell index:</span></span>  <br/> |<span data-ttu-id="cac9f-124">**visSmartTagButtonFace**</span><span class="sxs-lookup"><span data-stu-id="cac9f-124">**visSmartTagButtonFace**</span></span> <br/> |
   

