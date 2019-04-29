---
title: Disabled 单元格（“Actions”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251337
localization_priority: Normal
ms.assetid: ebf66729-d794-a398-268a-84d761bf06b6
description: 指示快捷菜单或动作标记菜单上的某项是否被禁用。
ms.openlocfilehash: ddf55f40056d7df7a2403e500bb4bae335930433
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431349"
---
# <a name="disabled-cell-actions-section"></a><span data-ttu-id="f3100-103">Disabled 单元格（“Actions”内容）</span><span class="sxs-lookup"><span data-stu-id="f3100-103">Disabled Cell (Actions Section)</span></span>

<span data-ttu-id="f3100-104">指示快捷菜单或动作标记菜单上的某项是否被禁用。</span><span class="sxs-lookup"><span data-stu-id="f3100-104">Indicates whether an item on a shortcut or action tag menu is disabled.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f3100-105">在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。</span><span class="sxs-lookup"><span data-stu-id="f3100-105">In previous versions of Microsoft Visio, action tags are called smart tags.</span></span> 
  
|<span data-ttu-id="f3100-106">**值**</span><span class="sxs-lookup"><span data-stu-id="f3100-106">**Value**</span></span>|<span data-ttu-id="f3100-107">**说明**</span><span class="sxs-lookup"><span data-stu-id="f3100-107">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f3100-108">TRUE</span><span class="sxs-lookup"><span data-stu-id="f3100-108">TRUE</span></span>  <br/> |<span data-ttu-id="f3100-109">禁用（灰显）命令名。</span><span class="sxs-lookup"><span data-stu-id="f3100-109">Disable (dim) command name.</span></span>  <br/> |
|<span data-ttu-id="f3100-110">FALSE</span><span class="sxs-lookup"><span data-stu-id="f3100-110">FALSE</span></span>  <br/> |<span data-ttu-id="f3100-111">启用命令名（默认值）。</span><span class="sxs-lookup"><span data-stu-id="f3100-111">Enable the command name (the default).</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f3100-112">说明</span><span class="sxs-lookup"><span data-stu-id="f3100-112">Remarks</span></span>

<span data-ttu-id="f3100-113">若要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Disabled 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="f3100-113">To get a reference to the Disabled cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f3100-114">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="f3100-114">Cell name:</span></span>  <br/> |<span data-ttu-id="f3100-115">操作.</span><span class="sxs-lookup"><span data-stu-id="f3100-115">Actions.</span></span> <span data-ttu-id="f3100-116">*名称*。在操作中禁用。</span><span class="sxs-lookup"><span data-stu-id="f3100-116">*name*  .Disabled           where Actions.</span></span> <span data-ttu-id="f3100-117">*name*是操作行的名称</span><span class="sxs-lookup"><span data-stu-id="f3100-117">*name*  is the name of the Actions row</span></span>  <br/> |
   
<span data-ttu-id="f3100-118">要从某个程序按索引获取对 Disabled 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="f3100-118">To get a reference to the Disabled cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f3100-119">内容索引：</span><span class="sxs-lookup"><span data-stu-id="f3100-119">Section index:</span></span>  <br/> |<span data-ttu-id="f3100-120">**visSectionAction**</span><span class="sxs-lookup"><span data-stu-id="f3100-120">**visSectionAction**</span></span> <br/> |
|<span data-ttu-id="f3100-121">行索引：</span><span class="sxs-lookup"><span data-stu-id="f3100-121">Row index:</span></span>  <br/> |<span data-ttu-id="f3100-122">**visRowAction** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="f3100-122">**visRowAction** +  *i*           where  *i*  = 0, 1, 2...</span></span>  <br/> |
|<span data-ttu-id="f3100-123">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="f3100-123">Cell index:</span></span>  <br/> |<span data-ttu-id="f3100-124">**visActionDisabled**</span><span class="sxs-lookup"><span data-stu-id="f3100-124">**visActionDisabled**</span></span> <br/> |
   

