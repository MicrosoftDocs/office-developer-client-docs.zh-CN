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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415759"
---
# <a name="description-cell-action-tags-section"></a><span data-ttu-id="64b90-103">Description 单元格（“Action Tags”内容）</span><span class="sxs-lookup"><span data-stu-id="64b90-103">Description Cell (Action Tags Section)</span></span>

<span data-ttu-id="64b90-104">包含描述动作标记的字符串。当用户将鼠标指针悬停于动作标记上时，此字符串以工具提示的形式显示。</span><span class="sxs-lookup"><span data-stu-id="64b90-104">Contains a string that describes the action tag, which appears as a tool tip when users place their pointer over the tag.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="64b90-105">说明</span><span class="sxs-lookup"><span data-stu-id="64b90-105">Remarks</span></span>

<span data-ttu-id="64b90-106">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Description 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="64b90-106">To get a reference to the Description cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="64b90-107">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="64b90-107">Cell name:</span></span>  <br/> | <span data-ttu-id="64b90-108">SmartTags.</span><span class="sxs-lookup"><span data-stu-id="64b90-108">SmartTags.</span></span>  <span data-ttu-id="64b90-109">*名称*。智能标记的说明。</span><span class="sxs-lookup"><span data-stu-id="64b90-109">*name*  .Description           where SmartTags.</span></span> <span data-ttu-id="64b90-110">*name*是操作标记行的名称</span><span class="sxs-lookup"><span data-stu-id="64b90-110">*name*  is the name of the action tag row</span></span>  <br/> |
   
<span data-ttu-id="64b90-111">要从某个程序按索引获取对 Description 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="64b90-111">To get a reference to the Description cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="64b90-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="64b90-112">Section index:</span></span>  <br/> |<span data-ttu-id="64b90-113">**visSectionSmartTag**</span><span class="sxs-lookup"><span data-stu-id="64b90-113">**visSectionSmartTag**</span></span> <br/> |
| <span data-ttu-id="64b90-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="64b90-114">Row index:</span></span>  <br/> |<span data-ttu-id="64b90-115">**visRowSmartTag** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="64b90-115">**visRowSmartTag** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="64b90-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="64b90-116">Cell index:</span></span>  <br/> |<span data-ttu-id="64b90-117">**visSmartTagDescription**</span><span class="sxs-lookup"><span data-stu-id="64b90-117">**visSmartTagDescription**</span></span> <br/> |
   

