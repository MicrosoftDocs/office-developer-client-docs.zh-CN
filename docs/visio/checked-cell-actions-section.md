---
title: Checked 单元格（“Actions”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm155
localization_priority: Normal
ms.assetid: 50937e29-eaa1-0cd0-53cc-dc17e7793e55
description: 指示是否在快捷菜单或动作标记菜单上选取了某项。
ms.openlocfilehash: 870823f28d802e7cafa81efbe5617f27b6714885
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438328"
---
# <a name="checked-cell-actions-section"></a><span data-ttu-id="1a77c-103">Checked 单元格（“Actions”内容）</span><span class="sxs-lookup"><span data-stu-id="1a77c-103">Checked Cell (Actions Section)</span></span>

<span data-ttu-id="1a77c-104">指示是否在快捷菜单或动作标记菜单上选取了某项。</span><span class="sxs-lookup"><span data-stu-id="1a77c-104">Indicates whether an item is checked on the shortcut or action tag menu.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1a77c-105">在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。</span><span class="sxs-lookup"><span data-stu-id="1a77c-105">In previous versions of Microsoft Visio, action tags are called smart tags.</span></span> 
  
|<span data-ttu-id="1a77c-106">**值**</span><span class="sxs-lookup"><span data-stu-id="1a77c-106">**Value**</span></span>|<span data-ttu-id="1a77c-107">**说明**</span><span class="sxs-lookup"><span data-stu-id="1a77c-107">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1a77c-108">TRUE</span><span class="sxs-lookup"><span data-stu-id="1a77c-108">TRUE</span></span>  <br/> |<span data-ttu-id="1a77c-109">显示复选标记。</span><span class="sxs-lookup"><span data-stu-id="1a77c-109">Check mark is displayed.</span></span>  <br/> |
|<span data-ttu-id="1a77c-110">FALSE</span><span class="sxs-lookup"><span data-stu-id="1a77c-110">FALSE</span></span>  <br/> |<span data-ttu-id="1a77c-111">不显示复选标记（默认值）。</span><span class="sxs-lookup"><span data-stu-id="1a77c-111">Check mark is not displayed (the default).</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1a77c-112">说明</span><span class="sxs-lookup"><span data-stu-id="1a77c-112">Remarks</span></span>

<span data-ttu-id="1a77c-113">若要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Checked 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="1a77c-113">To get a reference to the Checked cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="1a77c-114">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="1a77c-114">Cell name:</span></span>  <br/> |<span data-ttu-id="1a77c-115">操作.</span><span class="sxs-lookup"><span data-stu-id="1a77c-115">Actions.</span></span> <span data-ttu-id="1a77c-116">*名称*。检查 where 操作。</span><span class="sxs-lookup"><span data-stu-id="1a77c-116">*name*  .Checked           where Actions.</span></span> <span data-ttu-id="1a77c-117">*name*是操作行的名称</span><span class="sxs-lookup"><span data-stu-id="1a77c-117">*name*  is the name of the Actions row</span></span>  <br/> |
   
<span data-ttu-id="1a77c-118">要从某个程序按索引获取对 Checked 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="1a77c-118">To get a reference to the Checked cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="1a77c-119">内容索引：</span><span class="sxs-lookup"><span data-stu-id="1a77c-119">Section index:</span></span>  <br/> |<span data-ttu-id="1a77c-120">**visSectionAction**</span><span class="sxs-lookup"><span data-stu-id="1a77c-120">**visSectionAction**</span></span> <br/> |
|<span data-ttu-id="1a77c-121">行索引：</span><span class="sxs-lookup"><span data-stu-id="1a77c-121">Row index:</span></span>  <br/> |<span data-ttu-id="1a77c-122">**visRowAction** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="1a77c-122">**visRowAction** +  *i*           where  *i*  = 0, 1, 2, ...</span></span>  <br/> |
|<span data-ttu-id="1a77c-123">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="1a77c-123">Cell index:</span></span>  <br/> |<span data-ttu-id="1a77c-124">**visActionChecked**</span><span class="sxs-lookup"><span data-stu-id="1a77c-124">**visActionChecked**</span></span> <br/> |
   

