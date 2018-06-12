---
title: Glue 单元格（“Layers”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm415
localization_priority: Normal
ms.assetid: 75f2ea45-52ac-ddfa-14ea-402933ae2449
description: 指定是否可粘附属于图层的形状。
ms.openlocfilehash: 81a54bebaa8ca68a8fbc8853c69f88efb34bbdb2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780340"
---
# <a name="glue-cell-layers-section"></a><span data-ttu-id="cea19-103">Glue 单元格（“Layers”内容）</span><span class="sxs-lookup"><span data-stu-id="cea19-103">Glue Cell (Layers Section)</span></span>

<span data-ttu-id="cea19-104">指定是否可粘附属于图层的形状。</span><span class="sxs-lookup"><span data-stu-id="cea19-104">Specifies whether shapes belonging to the layer can be glued.</span></span>
  
|<span data-ttu-id="cea19-105">**值**</span><span class="sxs-lookup"><span data-stu-id="cea19-105">**Value**</span></span>|<span data-ttu-id="cea19-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="cea19-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cea19-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="cea19-107">TRUE</span></span>  <br/> |<span data-ttu-id="cea19-108">启用粘附。</span><span class="sxs-lookup"><span data-stu-id="cea19-108">Glue is enabled.</span></span>  <br/> |
|<span data-ttu-id="cea19-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="cea19-109">FALSE</span></span>  <br/> |<span data-ttu-id="cea19-110">禁用粘附。</span><span class="sxs-lookup"><span data-stu-id="cea19-110">Glue is disabled.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="cea19-111">注解</span><span class="sxs-lookup"><span data-stu-id="cea19-111">Remarks</span></span>

<span data-ttu-id="cea19-112">此单元格对应于**图层属性**对话框中的**粘附**选项 （**主页**选项卡，在**编辑**组中，单击**图层**，，然后单击**图层属性**）。</span><span class="sxs-lookup"><span data-stu-id="cea19-112">This cell corresponds to the **Glue** option in the **Layer Properties** dialog box (on the **Home** tab, in the **Editing** group, click **Layers**, and then click **Layer Properties** ).</span></span> 
  
<span data-ttu-id="cea19-113">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 Glue 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="cea19-113">To get a reference to the Glue cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="cea19-114">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="cea19-114">Cell name:</span></span>  <br/> |<span data-ttu-id="cea19-115">Layers.Glue [ *i* ] 其中*i* = < 1 >，2，3...</span><span class="sxs-lookup"><span data-stu-id="cea19-115">Layers.Glue[  *i*  ] where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="cea19-116">若要从某个程序按索引获取对 Glue 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="cea19-116">To get a reference to the Glue cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="cea19-117">内容索引：</span><span class="sxs-lookup"><span data-stu-id="cea19-117">Section index:</span></span>  <br/> |<span data-ttu-id="cea19-118">**visSectionLayer**</span><span class="sxs-lookup"><span data-stu-id="cea19-118">**visSectionLayer**</span></span> <br/> |
|<span data-ttu-id="cea19-119">行索引：</span><span class="sxs-lookup"><span data-stu-id="cea19-119">Row index:</span></span>  <br/> |<span data-ttu-id="cea19-120">**visRowLayer** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="cea19-120">**visRowLayer** +  *i*  where  *i*  = 0, 1, 2...</span></span>  <br/> |
|<span data-ttu-id="cea19-121">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="cea19-121">Cell index:</span></span>  <br/> |<span data-ttu-id="cea19-122">**visLayerGlue**</span><span class="sxs-lookup"><span data-stu-id="cea19-122">**visLayerGlue**</span></span> <br/> |
   

