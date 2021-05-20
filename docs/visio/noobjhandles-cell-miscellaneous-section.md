---
title: NoObjHandles 单元格（“Miscellaneous”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm730
localization_priority: Normal
ms.assetid: 8e1c8c8f-4ed0-0f53-f93f-3a264edc02bd
description: 切换选中形状的选择手柄的显示状态 - 显示或不显示。
ms.openlocfilehash: e46f19d77d1743fb7223b5f7d98f80a05d8f6b07
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428653"
---
# <a name="noobjhandles-cell-miscellaneous-section"></a><span data-ttu-id="762cd-103">NoObjHandles 单元格（“Miscellaneous”内容）</span><span class="sxs-lookup"><span data-stu-id="762cd-103">NoObjHandles Cell (Miscellaneous Section)</span></span>

<span data-ttu-id="762cd-104">切换选中形状的选择手柄的显示状态 - 显示或不显示。</span><span class="sxs-lookup"><span data-stu-id="762cd-104">Switches the display of selection handles on and off for the selected shape.</span></span>
  
|<span data-ttu-id="762cd-105">**值**</span><span class="sxs-lookup"><span data-stu-id="762cd-105">**Value**</span></span>|<span data-ttu-id="762cd-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="762cd-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="762cd-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="762cd-107">TRUE</span></span>  <br/> | <span data-ttu-id="762cd-108">选中形状后不显示选择手柄。</span><span class="sxs-lookup"><span data-stu-id="762cd-108">Selection handles are not displayed when a shape is selected.</span></span>  <br/> |
| <span data-ttu-id="762cd-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="762cd-109">FALSE</span></span>  <br/> | <span data-ttu-id="762cd-110">选中形状后显示选择手柄。</span><span class="sxs-lookup"><span data-stu-id="762cd-110">Selection handles are displayed when a shape is selected.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="762cd-111">备注</span><span class="sxs-lookup"><span data-stu-id="762cd-111">Remarks</span></span>

<span data-ttu-id="762cd-112">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 NoObjHandles 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="762cd-112">To get a reference to the NoObjHandles cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="762cd-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="762cd-113">Cell name:</span></span>  <br/> | <span data-ttu-id="762cd-114">NoObjHandles</span><span class="sxs-lookup"><span data-stu-id="762cd-114">NoObjHandles</span></span>  <br/> |
   
<span data-ttu-id="762cd-115">要从某个程序按索引获取对 NoObjHandles 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="762cd-115">To get a reference to the NoObjHandles cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="762cd-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="762cd-116">Section index:</span></span>  <br/> |<span data-ttu-id="762cd-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="762cd-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="762cd-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="762cd-118">Row index:</span></span>  <br/> |<span data-ttu-id="762cd-119">**visRowMisc**</span><span class="sxs-lookup"><span data-stu-id="762cd-119">**visRowMisc**</span></span> <br/> |
| <span data-ttu-id="762cd-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="762cd-120">Cell index:</span></span>  <br/> |<span data-ttu-id="762cd-121">**visNoObjHandles**</span><span class="sxs-lookup"><span data-stu-id="762cd-121">**visNoObjHandles**</span></span> <br/> |
   

