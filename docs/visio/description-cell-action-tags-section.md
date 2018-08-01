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
ms.openlocfilehash: 3c365d24170f912624a2abdeeadd75140bea9a85
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780092"
---
# <a name="description-cell-action-tags-section"></a><span data-ttu-id="9c085-103">Description 单元格（“Action Tags”部分）</span><span class="sxs-lookup"><span data-stu-id="9c085-103">Description Cell (Action Tags Section)</span></span>

<span data-ttu-id="9c085-104">包含描述动作标记的字符串。当用户将鼠标指针悬停于动作标记上时，此字符串以工具提示的形式显示。</span><span class="sxs-lookup"><span data-stu-id="9c085-104">Contains a string that describes the action tag, which appears as a tool tip when users place their pointer over the tag.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="9c085-105">注解</span><span class="sxs-lookup"><span data-stu-id="9c085-105">Remarks</span></span>

<span data-ttu-id="9c085-106">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Description 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="9c085-106">To get a reference to the Description cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="9c085-107">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="9c085-107">Cell name:</span></span>  <br/> | <span data-ttu-id="9c085-108">智能标记。</span><span class="sxs-lookup"><span data-stu-id="9c085-108">SmartTags.</span></span>  <span data-ttu-id="9c085-109">*名称*。说明其中智能标记。</span><span class="sxs-lookup"><span data-stu-id="9c085-109">*name*  .Description           where SmartTags.</span></span> <span data-ttu-id="9c085-110">*name*是动作标记行的名称</span><span class="sxs-lookup"><span data-stu-id="9c085-110">*name*  is the name of the action tag row</span></span>  <br/> |
   
<span data-ttu-id="9c085-111">要从某个程序按索引获取对 Description 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="9c085-111">To get a reference to the Description cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="9c085-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="9c085-112">Section index:</span></span>  <br/> |<span data-ttu-id="9c085-113">**visSectionSmartTag**</span><span class="sxs-lookup"><span data-stu-id="9c085-113">**visSectionSmartTag**</span></span> <br/> |
| <span data-ttu-id="9c085-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="9c085-114">Row index:</span></span>  <br/> |<span data-ttu-id="9c085-115">**visRowSmartTag** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="9c085-115">**visRowSmartTag** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="9c085-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="9c085-116">Cell index:</span></span>  <br/> |<span data-ttu-id="9c085-117">**visSmartTagDescription**</span><span class="sxs-lookup"><span data-stu-id="9c085-117">**visSmartTagDescription**</span></span> <br/> |
   

