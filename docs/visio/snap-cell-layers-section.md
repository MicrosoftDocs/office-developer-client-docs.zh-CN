---
title: Snap 单元格（“Layers”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251355
localization_priority: Normal
ms.assetid: c1b24e45-6f08-686b-b53d-e85fb9087a50
description: 确定其他形状是否可以与分配给图层的形状对齐。分配给图层的形状可以和其他形状对齐，但其他形状不能与它们对齐。
ms.openlocfilehash: 7fc684afb67d0454ea5907c08f4f7644d97c7f74
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781383"
---
# <a name="snap-cell-layers-section"></a><span data-ttu-id="05617-104">Snap 单元格（“Layers”部分）</span><span class="sxs-lookup"><span data-stu-id="05617-104">Snap Cell (Layers Section)</span></span>

<span data-ttu-id="05617-p102">确定其他形状是否可以与分配给图层的形状对齐。分配给图层的形状可以和其他形状对齐，但其他形状不能与它们对齐。</span><span class="sxs-lookup"><span data-stu-id="05617-p102">Determines whether other shapes can snap to shapes assigned to the layer. Shapes assigned to the layer can snap to other shapes, but other shapes can't snap to them.</span></span>
  
|<span data-ttu-id="05617-107">**值**</span><span class="sxs-lookup"><span data-stu-id="05617-107">**Value**</span></span>|<span data-ttu-id="05617-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="05617-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="05617-109">TRUE</span><span class="sxs-lookup"><span data-stu-id="05617-109">TRUE</span></span>  <br/> |<span data-ttu-id="05617-110">其他形状可以和图层上的形状对齐。</span><span class="sxs-lookup"><span data-stu-id="05617-110">Other shapes can snap to shapes on the layer.</span></span>  <br/> |
|<span data-ttu-id="05617-111">FALSE</span><span class="sxs-lookup"><span data-stu-id="05617-111">FALSE</span></span>  <br/> |<span data-ttu-id="05617-112">其他形状不能和图层上的形状对齐。</span><span class="sxs-lookup"><span data-stu-id="05617-112">Other shapes cannot snap to shapes on the layer.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="05617-113">注解</span><span class="sxs-lookup"><span data-stu-id="05617-113">Remarks</span></span>

<span data-ttu-id="05617-114">还可以使用 **“图层属性”** 对话框（在 **“开始”** 选项卡上的 **“编辑”** 组中，单击 **“图层”**，然后单击 **“图层属性”**）中的 **“对齐”** 选项设置此单元格的值。</span><span class="sxs-lookup"><span data-stu-id="05617-114">You can also set the value of this cell using the **Snap** option in the **Layer Properties** dialog box (on the **Home** tab, in the **Editing** group, click **Layers**, and then click **Layer Properties**).</span></span>
  
<span data-ttu-id="05617-115">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Snap 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="05617-115">To get a reference to the Snap cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="05617-116">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="05617-116">Cell name:</span></span>  <br/> |<span data-ttu-id="05617-117">Layers.Snap [ *i* ] 其中*i* = < 1 >，2，3...</span><span class="sxs-lookup"><span data-stu-id="05617-117">Layers.Snap[ *i*  ] where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="05617-118">若要从某个程序按索引获取对 Snap 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="05617-118">To get a reference to the Snap cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="05617-119">内容索引：</span><span class="sxs-lookup"><span data-stu-id="05617-119">Section index:</span></span>  <br/> |<span data-ttu-id="05617-120">**visSectionLayer**</span><span class="sxs-lookup"><span data-stu-id="05617-120">**visSectionLayer**</span></span> <br/> |
|<span data-ttu-id="05617-121">行索引：</span><span class="sxs-lookup"><span data-stu-id="05617-121">Row index:</span></span>  <br/> |<span data-ttu-id="05617-122">**visRowLayer** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="05617-122">**visRowLayer** +  *i*  where  *i*  = 0, 1, 2...</span></span>  <br/> |
|<span data-ttu-id="05617-123">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="05617-123">Cell index:</span></span>  <br/> |<span data-ttu-id="05617-124">**visLayerSnap**</span><span class="sxs-lookup"><span data-stu-id="05617-124">**visLayerSnap**</span></span> <br/> |
   

