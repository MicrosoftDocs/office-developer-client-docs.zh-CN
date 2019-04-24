---
title: Description 单元格（“Action Tags”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60037
localization_priority: Normal
ms.assetid: feb29b91-0f6e-6353-3dd0-7a280843a517
description: 包含描述动作标记的字符串。当用户将鼠标指针悬停于动作标记上时，此字符串以工具提示的形式显示。
ms.openlocfilehash: 00c7a4c1547927b8d1a979b8ae074f96f26dc17c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360227"
---
# <a name="description-cell-action-tags-section"></a><span data-ttu-id="6dfb5-103">Description 单元格（“Action Tags”内容）</span><span class="sxs-lookup"><span data-stu-id="6dfb5-103">Description Cell (Action Tags Section)</span></span>

<span data-ttu-id="6dfb5-104">包含描述动作标记的字符串。当用户将鼠标指针悬停于动作标记上时，此字符串以工具提示的形式显示。</span><span class="sxs-lookup"><span data-stu-id="6dfb5-104">Contains a string that describes the action tag, which appears as a tool tip when users place their pointer over the tag.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="6dfb5-105">注解</span><span class="sxs-lookup"><span data-stu-id="6dfb5-105">Remarks</span></span>

<span data-ttu-id="6dfb5-106">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Description 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="6dfb5-106">To get a reference to the Description cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="6dfb5-107">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="6dfb5-107">Cell name:</span></span>  <br/> | <span data-ttu-id="6dfb5-108">SmartTags.</span><span class="sxs-lookup"><span data-stu-id="6dfb5-108">SmartTags.</span></span>  <span data-ttu-id="6dfb5-109">*名称*。智能标记的说明。</span><span class="sxs-lookup"><span data-stu-id="6dfb5-109">*name*  .Description           where SmartTags.</span></span> <span data-ttu-id="6dfb5-110">*name*是操作标记行的名称</span><span class="sxs-lookup"><span data-stu-id="6dfb5-110">*name*  is the name of the action tag row</span></span>  <br/> |
   
<span data-ttu-id="6dfb5-111">要从某个程序按索引获取对 Description 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="6dfb5-111">To get a reference to the Description cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="6dfb5-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="6dfb5-112">Section index:</span></span>  <br/> |<span data-ttu-id="6dfb5-113">**visSectionSmartTag**</span><span class="sxs-lookup"><span data-stu-id="6dfb5-113">**visSectionSmartTag**</span></span> <br/> |
| <span data-ttu-id="6dfb5-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="6dfb5-114">Row index:</span></span>  <br/> |<span data-ttu-id="6dfb5-115">**visRowSmartTag** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="6dfb5-115">**visRowSmartTag** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="6dfb5-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="6dfb5-116">Cell index:</span></span>  <br/> |<span data-ttu-id="6dfb5-117">**visSmartTagDescription**</span><span class="sxs-lookup"><span data-stu-id="6dfb5-117">**visSmartTagDescription**</span></span> <br/> |
   

