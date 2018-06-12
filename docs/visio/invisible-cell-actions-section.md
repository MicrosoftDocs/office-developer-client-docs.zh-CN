---
title: Invisible 单元格（“Actions”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60046
localization_priority: Normal
ms.assetid: 070b4468-c907-b201-1633-1d3e10ecc2b2
description: 指示动作标记或快捷菜单上是否显示动作。
ms.openlocfilehash: 8749b7d6db4a932b97c68ab5cf30b879a57d28f2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780462"
---
# <a name="invisible-cell-actions-section"></a><span data-ttu-id="e6ee4-103">Invisible 单元格（“Actions”内容）</span><span class="sxs-lookup"><span data-stu-id="e6ee4-103">Invisible Cell (Actions Section)</span></span>

<span data-ttu-id="e6ee4-104">指示动作标记或快捷菜单上是否显示动作。</span><span class="sxs-lookup"><span data-stu-id="e6ee4-104">Indicates whether the action is visible on the action tag or shortcut menu.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="e6ee4-105">在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。</span><span class="sxs-lookup"><span data-stu-id="e6ee4-105">In previous versions of Microsoft Visio, action tags are called smart tags.</span></span> 
  
|<span data-ttu-id="e6ee4-106">**值**</span><span class="sxs-lookup"><span data-stu-id="e6ee4-106">**Value**</span></span>|<span data-ttu-id="e6ee4-107">**说明**</span><span class="sxs-lookup"><span data-stu-id="e6ee4-107">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e6ee4-108">TRUE</span><span class="sxs-lookup"><span data-stu-id="e6ee4-108">TRUE</span></span>  <br/> |<span data-ttu-id="e6ee4-109">菜单上不显示动作。</span><span class="sxs-lookup"><span data-stu-id="e6ee4-109">The action is not visible on the menu.</span></span>  <br/> |
|<span data-ttu-id="e6ee4-110">FALSE</span><span class="sxs-lookup"><span data-stu-id="e6ee4-110">FALSE</span></span>  <br/> |<span data-ttu-id="e6ee4-111">菜单上显示动作（默认值）。</span><span class="sxs-lookup"><span data-stu-id="e6ee4-111">The action is visible on the menu (the default).</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e6ee4-112">注解</span><span class="sxs-lookup"><span data-stu-id="e6ee4-112">Remarks</span></span>

<span data-ttu-id="e6ee4-113">若要获取对 Invisible 单元格的引用按名称从另一个公式或从程序使用**CellsU**属性，请使用：</span><span class="sxs-lookup"><span data-stu-id="e6ee4-113">To get a reference to the Invisible cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e6ee4-114">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="e6ee4-114">Cell name:</span></span>  <br/> |<span data-ttu-id="e6ee4-115">操作。</span><span class="sxs-lookup"><span data-stu-id="e6ee4-115">Actions.</span></span> <span data-ttu-id="e6ee4-116">*名称*。Invisiblewhere 操作。</span><span class="sxs-lookup"><span data-stu-id="e6ee4-116">*name*  .Invisiblewhere Actions.</span></span>  <span data-ttu-id="e6ee4-117">*name*是 Actions 行的名称</span><span class="sxs-lookup"><span data-stu-id="e6ee4-117">*name*  is the name of the Actions row</span></span>  <br/> |
   
<span data-ttu-id="e6ee4-118">若要从某个程序按索引获取对 Invisible 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="e6ee4-118">To get a reference to the Invisible cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e6ee4-119">内容索引：</span><span class="sxs-lookup"><span data-stu-id="e6ee4-119">Section index:</span></span>  <br/> |<span data-ttu-id="e6ee4-120">**visSectionAction**</span><span class="sxs-lookup"><span data-stu-id="e6ee4-120">**visSectionAction**</span></span> <br/> |
|<span data-ttu-id="e6ee4-121">行索引：</span><span class="sxs-lookup"><span data-stu-id="e6ee4-121">Row index:</span></span>  <br/> |<span data-ttu-id="e6ee4-122">**visRowAction** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="e6ee4-122">**visRowAction** +  *i*  where  *i*  = 0, 1, 2...</span></span>  <br/> |
|<span data-ttu-id="e6ee4-123">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="e6ee4-123">Cell index:</span></span>  <br/> |<span data-ttu-id="e6ee4-124">**visActionInvisible**</span><span class="sxs-lookup"><span data-stu-id="e6ee4-124">**visActionInvisible**</span></span> <br/> |
   

