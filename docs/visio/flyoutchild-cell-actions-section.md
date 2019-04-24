---
title: FlyoutChild 单元格（“Actions”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm80003
localization_priority: Normal
ms.assetid: b2405457-843c-0d46-5f4f-9c413826c3f1
description: 确定该行是否为不是弹出子菜单的上一行的弹出子菜单。
ms.openlocfilehash: 85524ea33258449f5c9ee0991ac9a64f8f0eebae
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346149"
---
# <a name="flyoutchild-cell-actions-section"></a><span data-ttu-id="954f8-103">FlyoutChild 单元格（“Actions”内容）</span><span class="sxs-lookup"><span data-stu-id="954f8-103">FlyoutChild Cell (Actions Section)</span></span>

<span data-ttu-id="954f8-104">确定该行是否为不是弹出子菜单的上一行的弹出子菜单。</span><span class="sxs-lookup"><span data-stu-id="954f8-104">Determines whether the row is a child flyout menu of the last row above it that is not a flyout child.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="954f8-105">注解</span><span class="sxs-lookup"><span data-stu-id="954f8-105">Remarks</span></span>

<span data-ttu-id="954f8-106">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 FlyoutChild 单元格的引用，请使用以下内容。</span><span class="sxs-lookup"><span data-stu-id="954f8-106">To get a reference to the FlyoutChild cell by name from another formula, or from a program by using the **CellsU** property, use the following.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="954f8-107">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="954f8-107">Cell name:</span></span>  <br/> |<span data-ttu-id="954f8-108">操作.</span><span class="sxs-lookup"><span data-stu-id="954f8-108">Actions.</span></span> <span data-ttu-id="954f8-109">*名称*。FlyoutChildwhere 操作。</span><span class="sxs-lookup"><span data-stu-id="954f8-109">*name*  .FlyoutChildwhere Actions.</span></span>  <span data-ttu-id="954f8-110">*name*是操作行的名称</span><span class="sxs-lookup"><span data-stu-id="954f8-110">*name*  is the name of the Actions row</span></span>  <br/> |
   
<span data-ttu-id="954f8-111">若要从某个程序按索引获取对 FlyoutChild 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="954f8-111">To get a reference to the FlyoutChild cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="954f8-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="954f8-112">Section index:</span></span>  <br/> |<span data-ttu-id="954f8-113">**visSectionAction**</span><span class="sxs-lookup"><span data-stu-id="954f8-113">**visSectionAction**</span></span> <br/> |
|<span data-ttu-id="954f8-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="954f8-114">Row index:</span></span>  <br/> |<span data-ttu-id="954f8-115">**visRowAction** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="954f8-115">**visRowAction** +  *i*  where  *i*  = 0, 1, 2...</span></span>  <br/> |
|<span data-ttu-id="954f8-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="954f8-116">Cell index:</span></span>  <br/> |<span data-ttu-id="954f8-117">**visActionFlyoutChild**</span><span class="sxs-lookup"><span data-stu-id="954f8-117">**visActionFlyoutChild**</span></span> <br/> |
   

