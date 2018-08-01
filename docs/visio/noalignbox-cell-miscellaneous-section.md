---
title: NoAlignBox 单元格（“Miscellaneous”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm700
localization_priority: Normal
ms.assetid: b2d51f4b-d64e-fd14-4ff1-ed67c69213bc
description: 切换选中形状的选择矩形的显示状态 - 显示或不显示。
ms.openlocfilehash: c8e5fe28197a72b4cdb5306732dd155dc8f4f810
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780785"
---
# <a name="noalignbox-cell-miscellaneous-section"></a><span data-ttu-id="01ba7-103">NoAlignBox 单元格（“Miscellaneous”部分）</span><span class="sxs-lookup"><span data-stu-id="01ba7-103">NoAlignBox Cell (Miscellaneous Section)</span></span>

<span data-ttu-id="01ba7-104">切换选中形状的选择矩形的显示状态 - 显示或不显示。</span><span class="sxs-lookup"><span data-stu-id="01ba7-104">Switches the display of the selection rectangle on and off for the selected shape.</span></span>
  
|<span data-ttu-id="01ba7-105">**值**</span><span class="sxs-lookup"><span data-stu-id="01ba7-105">**Value**</span></span>|<span data-ttu-id="01ba7-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="01ba7-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="01ba7-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="01ba7-107">TRUE</span></span>  <br/> | <span data-ttu-id="01ba7-108">选中形状后不显示选择矩形。</span><span class="sxs-lookup"><span data-stu-id="01ba7-108">Selection rectangle is not displayed when the shape is selected.</span></span>  <br/> |
| <span data-ttu-id="01ba7-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="01ba7-109">FALSE</span></span>  <br/> | <span data-ttu-id="01ba7-110">选中形状后显示选择矩形。</span><span class="sxs-lookup"><span data-stu-id="01ba7-110">Selection rectangle is displayed when the shape is selected.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="01ba7-111">注解</span><span class="sxs-lookup"><span data-stu-id="01ba7-111">Remarks</span></span>

<span data-ttu-id="01ba7-112">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 NoAlignBox 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="01ba7-112">To get a reference to the NoAlignBox cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="01ba7-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="01ba7-113">Cell name:</span></span>  <br/> | <span data-ttu-id="01ba7-114">NoAlignBox</span><span class="sxs-lookup"><span data-stu-id="01ba7-114">NoAlignBox</span></span>  <br/> |
   
<span data-ttu-id="01ba7-115">要从某个程序按索引获取对 NoAlignBox 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="01ba7-115">To get a reference to the NoAlignBox cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="01ba7-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="01ba7-116">Section index:</span></span>  <br/> |<span data-ttu-id="01ba7-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="01ba7-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="01ba7-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="01ba7-118">Row index:</span></span>  <br/> |<span data-ttu-id="01ba7-119">**visRowMisc**</span><span class="sxs-lookup"><span data-stu-id="01ba7-119">**visRowMisc**</span></span> <br/> |
| <span data-ttu-id="01ba7-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="01ba7-120">Cell index:</span></span>  <br/> |<span data-ttu-id="01ba7-121">**visNoAlignBox**</span><span class="sxs-lookup"><span data-stu-id="01ba7-121">**visNoAlignBox**</span></span> <br/> |
   

