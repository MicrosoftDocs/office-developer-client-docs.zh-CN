---
title: Invisible 单元格（“Shape Data”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251341
localization_priority: Normal
ms.assetid: 5f368c2e-2a40-38ee-3568-ed5c57633345
description: 指定形状数据项在“形状数据”窗口中是否可见。
ms.openlocfilehash: 2cd3fcad5db7b1752c55055354f1ec842bff4899
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780461"
---
# <a name="invisible-cell-shape-data-section"></a><span data-ttu-id="9a3e6-103">Invisible 单元格（“Shape Data”部分）</span><span class="sxs-lookup"><span data-stu-id="9a3e6-103">Invisible Cell (Shape Data Section)</span></span>

<span data-ttu-id="9a3e6-104">指定形状数据项在 **“形状数据”** 窗口中是否可见。</span><span class="sxs-lookup"><span data-stu-id="9a3e6-104">Specifies whether the shape data item is visible in the **Shape Data** window.</span></span> 
  
|<span data-ttu-id="9a3e6-105">**值**</span><span class="sxs-lookup"><span data-stu-id="9a3e6-105">**Value**</span></span>|<span data-ttu-id="9a3e6-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="9a3e6-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="9a3e6-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="9a3e6-107">TRUE</span></span>  <br/> | <span data-ttu-id="9a3e6-108">形状数据项不可见。</span><span class="sxs-lookup"><span data-stu-id="9a3e6-108">Shape data item is not visible.</span></span>  <br/> |
| <span data-ttu-id="9a3e6-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="9a3e6-109">FALSE</span></span>  <br/> | <span data-ttu-id="9a3e6-110">形状数据项可见。</span><span class="sxs-lookup"><span data-stu-id="9a3e6-110">Shape data item is visible.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="9a3e6-111">注解</span><span class="sxs-lookup"><span data-stu-id="9a3e6-111">Remarks</span></span>

<span data-ttu-id="9a3e6-112">此单元格中的值对应于 **“定义形状数据”** 对话框（右键单击形状，指向 **“数据”**，然后单击 **“定义形状数据”**）中的 **“隐藏”** 复选框。</span><span class="sxs-lookup"><span data-stu-id="9a3e6-112">The value in this cell corresponds to the **Hidden** check box in the **Define Shape Data** dialog box (right-click the shape, point to **Data**, and then click **Define Shape Data**).</span></span>
  
<span data-ttu-id="9a3e6-113">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Invisible 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="9a3e6-113">To get a reference to the Invisible cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="9a3e6-114">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="9a3e6-114">Cell name:</span></span>  <br/> | <span data-ttu-id="9a3e6-115">属性。 *名称*。不可见的位置的属性。 *name*是行名称</span><span class="sxs-lookup"><span data-stu-id="9a3e6-115">Prop.  *name*  .Invisible where Prop.  *name*  is the row name</span></span>  <br/> |
   
<span data-ttu-id="9a3e6-116">若要从某个程序按索引获取对 Invisible 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="9a3e6-116">To get a reference to the Invisible cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="9a3e6-117">内容索引：</span><span class="sxs-lookup"><span data-stu-id="9a3e6-117">Section index:</span></span>  <br/> |<span data-ttu-id="9a3e6-118">**visSectionProp**</span><span class="sxs-lookup"><span data-stu-id="9a3e6-118">**visSectionProp**</span></span> <br/> |
| <span data-ttu-id="9a3e6-119">行索引：</span><span class="sxs-lookup"><span data-stu-id="9a3e6-119">Row index:</span></span>  <br/> |<span data-ttu-id="9a3e6-120">**visRowProp** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="9a3e6-120">**visRowProp** +  *i*  where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="9a3e6-121">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="9a3e6-121">Cell index:</span></span>  <br/> |<span data-ttu-id="9a3e6-122">**visCustPropsInvis**</span><span class="sxs-lookup"><span data-stu-id="9a3e6-122">**visCustPropsInvis**</span></span> <br/> |
   

