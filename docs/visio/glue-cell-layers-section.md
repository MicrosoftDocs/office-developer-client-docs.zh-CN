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
ms.openlocfilehash: 55886a7e96bd2c08966cb85f5edad6a7174e30cd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332807"
---
# <a name="glue-cell-layers-section"></a><span data-ttu-id="7ed9c-103">Glue 单元格（“Layers”内容）</span><span class="sxs-lookup"><span data-stu-id="7ed9c-103">Glue Cell (Layers Section)</span></span>

<span data-ttu-id="7ed9c-104">指定是否可粘附属于图层的形状。</span><span class="sxs-lookup"><span data-stu-id="7ed9c-104">Specifies whether shapes belonging to the layer can be glued.</span></span>
  
|<span data-ttu-id="7ed9c-105">**Value**</span><span class="sxs-lookup"><span data-stu-id="7ed9c-105">**Value**</span></span>|<span data-ttu-id="7ed9c-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="7ed9c-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7ed9c-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="7ed9c-107">TRUE</span></span>  <br/> |<span data-ttu-id="7ed9c-108">启用粘附。</span><span class="sxs-lookup"><span data-stu-id="7ed9c-108">Glue is enabled.</span></span>  <br/> |
|<span data-ttu-id="7ed9c-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="7ed9c-109">FALSE</span></span>  <br/> |<span data-ttu-id="7ed9c-110">禁用粘附。</span><span class="sxs-lookup"><span data-stu-id="7ed9c-110">Glue is disabled.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7ed9c-111">注解</span><span class="sxs-lookup"><span data-stu-id="7ed9c-111">Remarks</span></span>

<span data-ttu-id="7ed9c-112">此单元格对应于 "**图层属性**" 对话框 (在 "**开始**" 选项卡上的 "**编辑**" 组中, 单击 "**层**", 然后单击 "**图层属性**") 中的 "**粘附**" 选项。</span><span class="sxs-lookup"><span data-stu-id="7ed9c-112">This cell corresponds to the **Glue** option in the **Layer Properties** dialog box (on the **Home** tab, in the **Editing** group, click **Layers**, and then click **Layer Properties** ).</span></span> 
  
<span data-ttu-id="7ed9c-113">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Glue 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="7ed9c-113">To get a reference to the Glue cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="7ed9c-114">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="7ed9c-114">Cell name:</span></span>  <br/> |<span data-ttu-id="7ed9c-115">图: 粘附 [ *i* ] 其中*i* = <1>, 2, 3 .。。</span><span class="sxs-lookup"><span data-stu-id="7ed9c-115">Layers.Glue[  *i*  ] where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="7ed9c-116">若要从某个程序按索引获取对 Glue 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="7ed9c-116">To get a reference to the Glue cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="7ed9c-117">内容索引：</span><span class="sxs-lookup"><span data-stu-id="7ed9c-117">Section index:</span></span>  <br/> |<span data-ttu-id="7ed9c-118">**visSectionLayer**</span><span class="sxs-lookup"><span data-stu-id="7ed9c-118">**visSectionLayer**</span></span> <br/> |
|<span data-ttu-id="7ed9c-119">行索引：</span><span class="sxs-lookup"><span data-stu-id="7ed9c-119">Row index:</span></span>  <br/> |<span data-ttu-id="7ed9c-120">**visRowLayer** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="7ed9c-120">**visRowLayer** +  *i*  where  *i*  = 0, 1, 2...</span></span>  <br/> |
|<span data-ttu-id="7ed9c-121">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="7ed9c-121">Cell index:</span></span>  <br/> |<span data-ttu-id="7ed9c-122">**visLayerGlue**</span><span class="sxs-lookup"><span data-stu-id="7ed9c-122">**visLayerGlue**</span></span> <br/> |
   

