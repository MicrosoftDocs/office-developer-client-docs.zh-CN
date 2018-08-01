---
title: Visible 单元格（“Layers”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm1110
localization_priority: Normal
ms.assetid: 02048012-a814-410b-f26e-56fcfbe106e6
description: 指定属于该图层的形状在绘图页上是否显示出来。
ms.openlocfilehash: 9a025403b1f5b46d2f439805a15954eaeeab2686
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781632"
---
# <a name="visible-cell-layers-section"></a><span data-ttu-id="7b07a-103">Visible 单元格（“Layers”部分）</span><span class="sxs-lookup"><span data-stu-id="7b07a-103">Visible Cell (Layers Section)</span></span>

<span data-ttu-id="7b07a-104">指定属于该图层的形状在绘图页上是否显示出来。</span><span class="sxs-lookup"><span data-stu-id="7b07a-104">Specifies whether shapes belonging to the layer are visible on the drawing page.</span></span>
  
|<span data-ttu-id="7b07a-105">**值**</span><span class="sxs-lookup"><span data-stu-id="7b07a-105">**Value**</span></span>|<span data-ttu-id="7b07a-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="7b07a-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7b07a-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="7b07a-107">TRUE</span></span>  <br/> |<span data-ttu-id="7b07a-108">形状显示出来。</span><span class="sxs-lookup"><span data-stu-id="7b07a-108">Shapes are visible.</span></span>  <br/> |
|<span data-ttu-id="7b07a-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="7b07a-109">FALSE</span></span>  <br/> |<span data-ttu-id="7b07a-110">形状隐藏起来。</span><span class="sxs-lookup"><span data-stu-id="7b07a-110">Shapes are hidden.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7b07a-111">注解</span><span class="sxs-lookup"><span data-stu-id="7b07a-111">Remarks</span></span>

<span data-ttu-id="7b07a-112">此单元格对应于**图层属性**对话框中的**可见**选项 （**主页**选项卡，在**编辑**组中，单击**图层**，，然后单击**图层属性**）。</span><span class="sxs-lookup"><span data-stu-id="7b07a-112">This cell corresponds to the **Visible** option in the **Layer Properties** dialog box (on the **Home** tab, in the **Editing** group, click **Layers**, and then click **Layer Properties** ).</span></span> 
  
<span data-ttu-id="7b07a-113">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Visible 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="7b07a-113">To get a reference to the Visible cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="7b07a-114">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="7b07a-114">Cell name:</span></span>  <br/> |<span data-ttu-id="7b07a-115">Layers.Visible [ *i* ] 其中*i* = < 1 >，2，3...</span><span class="sxs-lookup"><span data-stu-id="7b07a-115">Layers.Visible[ *i*  ] where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="7b07a-116">若要从某个程序按索引获取对 Visible 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="7b07a-116">To get a reference to the Visible cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="7b07a-117">内容索引：</span><span class="sxs-lookup"><span data-stu-id="7b07a-117">Section index:</span></span>  <br/> |<span data-ttu-id="7b07a-118">**visSectionLayer**</span><span class="sxs-lookup"><span data-stu-id="7b07a-118">**visSectionLayer**</span></span> <br/> |
|<span data-ttu-id="7b07a-119">行索引：</span><span class="sxs-lookup"><span data-stu-id="7b07a-119">Row index:</span></span>  <br/> |<span data-ttu-id="7b07a-120">**visRowLayer** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="7b07a-120">**visRowLayer** +  *i*  where  *i*  = 0, 1, 2...</span></span>  <br/> |
|<span data-ttu-id="7b07a-121">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="7b07a-121">Cell index:</span></span>  <br/> |<span data-ttu-id="7b07a-122">**visLayerVisible**</span><span class="sxs-lookup"><span data-stu-id="7b07a-122">**visLayerVisible**</span></span> <br/> |
   

