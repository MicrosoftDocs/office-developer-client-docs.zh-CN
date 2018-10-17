---
title: Active 单元格（“Layers”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm10
localization_priority: Normal
ms.assetid: 4c8e366f-9e9b-30ea-a89f-57c8d7a1168e
description: 指定图层是否处于活动状态。将形状拖到绘图页上时，未预先分配图层的形状将指定给活动图层。
ms.openlocfilehash: 81d3ec083e207a927c46dda99e2b7f42c0a7bd8e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779627"
---
# <a name="active-cell-layers-section"></a><span data-ttu-id="741e3-104">Active 单元格（“Layers”部分）</span><span class="sxs-lookup"><span data-stu-id="741e3-104">Active Cell (Layers Section)</span></span>

<span data-ttu-id="741e3-p102">指定图层是否处于活动状态。将形状拖到绘图页上时，未预先分配图层的形状将指定给活动图层。</span><span class="sxs-lookup"><span data-stu-id="741e3-p102">Specifies whether the layer is active. Shapes without pre-assigned layers are assigned to the active layer(s) when you drag them onto the drawing page.</span></span>
  
|<span data-ttu-id="741e3-107">**值**</span><span class="sxs-lookup"><span data-stu-id="741e3-107">**Value**</span></span>|<span data-ttu-id="741e3-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="741e3-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="741e3-109">TRUE</span><span class="sxs-lookup"><span data-stu-id="741e3-109">TRUE</span></span>  <br/> |<span data-ttu-id="741e3-110">
          图层是活动图层。
</span><span class="sxs-lookup"><span data-stu-id="741e3-110">Layer is active.</span></span>  <br/> |
|<span data-ttu-id="741e3-111">FALSE</span><span class="sxs-lookup"><span data-stu-id="741e3-111">FALSE</span></span>  <br/> |<span data-ttu-id="741e3-112">
          图层不是活动图层。
</span><span class="sxs-lookup"><span data-stu-id="741e3-112">Layer is not active.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="741e3-113">说明</span><span class="sxs-lookup"><span data-stu-id="741e3-113">Remarks</span></span>

<span data-ttu-id="741e3-114">此单元格中的值对应于 **“图层属性”** 对话框（在 **“开始”** 选项卡上的 **“编辑”** 组中，单击 **“图层”**，然后单击 **“图层属性”**）中的 **“活动”** 设置。</span><span class="sxs-lookup"><span data-stu-id="741e3-114">The value in this cell corresponds to the **Active** setting in the **Layer Properties** dialog box (in the **Editing** group on the **Home** tab, click **Layers**, and then click **Layer Properties**).</span></span>
  
<span data-ttu-id="741e3-115">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Active 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="741e3-115">To get a reference to the Active cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="741e3-116">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="741e3-116">Cell name:</span></span>  <br/> |<span data-ttu-id="741e3-117">Layers.Active [ *i* ] 其中*i* = < 1 >，2，3...</span><span class="sxs-lookup"><span data-stu-id="741e3-117">Layers.Active[ *i*  ]           where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="741e3-118">若要从某个程序按索引获取对 Active 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="741e3-118">To get a reference to the Active cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="741e3-119">内容索引：</span><span class="sxs-lookup"><span data-stu-id="741e3-119">Section index:</span></span>  <br/> |<span data-ttu-id="741e3-120">**visSectionLayer**</span><span class="sxs-lookup"><span data-stu-id="741e3-120">**visSectionLayer**</span></span> <br/> |
|<span data-ttu-id="741e3-121">行索引：</span><span class="sxs-lookup"><span data-stu-id="741e3-121">Row index:</span></span>  <br/> |<span data-ttu-id="741e3-122">**visRowLayer** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="741e3-122">**visRowLayer** +  *i*           where  *i*  = 0, 1, 2...</span></span>  <br/> |
|<span data-ttu-id="741e3-123">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="741e3-123">Cell index:</span></span>  <br/> |<span data-ttu-id="741e3-124">**visLayerActive**</span><span class="sxs-lookup"><span data-stu-id="741e3-124">**visLayerActive**</span></span> <br/> |
   
