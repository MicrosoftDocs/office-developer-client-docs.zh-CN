---
title: Print 单元格（“Layers”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm825
localization_priority: Normal
ms.assetid: 9c76bf02-7269-65bb-2fd2-920243d962ef
description: 指定是否可打印属于该图层的形状。
ms.openlocfilehash: f9a1dca6d45b53c02ff0ed29f921c352fc947630
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435213"
---
# <a name="print-cell-layers-section"></a><span data-ttu-id="267d9-103">Print 单元格（“Layers”内容）</span><span class="sxs-lookup"><span data-stu-id="267d9-103">Print Cell (Layers Section)</span></span>

<span data-ttu-id="267d9-104">指定是否可打印属于该图层的形状。</span><span class="sxs-lookup"><span data-stu-id="267d9-104">Specifies whether shapes belonging to the layer can be printed.</span></span>
  
|<span data-ttu-id="267d9-105">**值**</span><span class="sxs-lookup"><span data-stu-id="267d9-105">**Value**</span></span>|<span data-ttu-id="267d9-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="267d9-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="267d9-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="267d9-107">TRUE</span></span>  <br/> |<span data-ttu-id="267d9-108">能够打印形状。</span><span class="sxs-lookup"><span data-stu-id="267d9-108">Shapes can be printed.</span></span>  <br/> |
|<span data-ttu-id="267d9-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="267d9-109">FALSE</span></span>  <br/> |<span data-ttu-id="267d9-110">不能打印形状。</span><span class="sxs-lookup"><span data-stu-id="267d9-110">Shapes cannot be printed.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="267d9-111">说明</span><span class="sxs-lookup"><span data-stu-id="267d9-111">Remarks</span></span>

<span data-ttu-id="267d9-112">还可以使用 **“图层属性”** 对话框（在 **“开始”** 选项卡上的 **“编辑”** 组中，单击 **“图层”**，然后单击 **“图层属性”**）中的 **“打印”** 选项设置此值。</span><span class="sxs-lookup"><span data-stu-id="267d9-112">You can also set this value by using the **Print** option in the **Layer Properties** dialog box (on the **Home** tab, in the **Editing** group, click **Layers**, and then click **Layer Properties**).</span></span>
  
<span data-ttu-id="267d9-113">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Print 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="267d9-113">To get a reference to the Print cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="267d9-114">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="267d9-114">Cell name:</span></span>  <br/> |<span data-ttu-id="267d9-115">"打印层" [ *i* ] 其中*i* = <1>, 2, 3 .。。</span><span class="sxs-lookup"><span data-stu-id="267d9-115">Layers.Print[ *i*  ] where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="267d9-116">若要从某个程序按索引获取对 Print 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="267d9-116">To get a reference to the Print cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="267d9-117">内容索引：</span><span class="sxs-lookup"><span data-stu-id="267d9-117">Section index:</span></span>  <br/> |<span data-ttu-id="267d9-118">**visSectionLayer**</span><span class="sxs-lookup"><span data-stu-id="267d9-118">**visSectionLayer**</span></span> <br/> |
|<span data-ttu-id="267d9-119">行索引：</span><span class="sxs-lookup"><span data-stu-id="267d9-119">Row index:</span></span>  <br/> |<span data-ttu-id="267d9-120">**visRowLayer** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="267d9-120">**visRowLayer** +  *i*  where  *i*  = 0, 1, 2...</span></span>  <br/> |
|<span data-ttu-id="267d9-121">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="267d9-121">Cell index:</span></span>  <br/> |<span data-ttu-id="267d9-122">**visDocPreviewScope**</span><span class="sxs-lookup"><span data-stu-id="267d9-122">**visDocPreviewScope**</span></span> <br/> |
   

