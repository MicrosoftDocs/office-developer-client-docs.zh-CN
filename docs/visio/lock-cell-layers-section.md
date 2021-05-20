---
title: Lock 单元格（“Layers”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm590
localization_priority: Normal
ms.assetid: 47bb268f-acdd-7369-716c-bd51a32b8a49
description: 指定是否锁定属于该图层的形状，以免选取或编辑这些形状。
ms.openlocfilehash: d548a6f0fe0cac10d80d73c904739b2979ecf27f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438825"
---
# <a name="lock-cell-layers-section"></a><span data-ttu-id="e37a7-103">Lock 单元格（“Layers”内容）</span><span class="sxs-lookup"><span data-stu-id="e37a7-103">Lock Cell (Layers Section)</span></span>

<span data-ttu-id="e37a7-104">指定是否锁定属于该图层的形状，以免选取或编辑这些形状。</span><span class="sxs-lookup"><span data-stu-id="e37a7-104">Specifies whether shapes belonging to the layer are locked against being selected or edited.</span></span>
  
|<span data-ttu-id="e37a7-105">**值**</span><span class="sxs-lookup"><span data-stu-id="e37a7-105">**Value**</span></span>|<span data-ttu-id="e37a7-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="e37a7-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e37a7-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="e37a7-107">TRUE</span></span>  <br/> |<span data-ttu-id="e37a7-108">锁定形状。</span><span class="sxs-lookup"><span data-stu-id="e37a7-108">Shapes are locked.</span></span>  <br/> |
|<span data-ttu-id="e37a7-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="e37a7-109">FALSE</span></span>  <br/> |<span data-ttu-id="e37a7-110">不锁定形状。</span><span class="sxs-lookup"><span data-stu-id="e37a7-110">Shapes are not locked.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e37a7-111">备注</span><span class="sxs-lookup"><span data-stu-id="e37a7-111">Remarks</span></span>

<span data-ttu-id="e37a7-112">还可以通过在 **“图层属性”** 对话框（在 **“开始”** 选项卡上的 **“编辑”** 组中，单击 **“图层”**，然后单击 **“图层属性”**）中选择 **“锁定”** 来设置此值。</span><span class="sxs-lookup"><span data-stu-id="e37a7-112">You can also set this value by selecting **Lock** in the **Layer Properties** dialog box (on the **Home** tab, in the **Editing** group, click **Layers**, and then click **Layer Properties**).</span></span>
  
<span data-ttu-id="e37a7-113">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Lock 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="e37a7-113">To get a reference to the Lock cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e37a7-114">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="e37a7-114">Cell name:</span></span>  <br/> |<span data-ttu-id="e37a7-115">Layers.Locked[ *i*  ] 其中  *i*  = <1> 2， 3...</span><span class="sxs-lookup"><span data-stu-id="e37a7-115">Layers.Locked[ *i*  ] where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="e37a7-116">若要从某个程序按索引获取对 Lock 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="e37a7-116">To get a reference to the Lock cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e37a7-117">内容索引：</span><span class="sxs-lookup"><span data-stu-id="e37a7-117">Section index:</span></span>  <br/> |<span data-ttu-id="e37a7-118">**visSectionLayer**</span><span class="sxs-lookup"><span data-stu-id="e37a7-118">**visSectionLayer**</span></span> <br/> |
|<span data-ttu-id="e37a7-119">行索引：</span><span class="sxs-lookup"><span data-stu-id="e37a7-119">Row index:</span></span>  <br/> |<span data-ttu-id="e37a7-120">**visRowLayer**  +  *i* 其中 *i* = 0、1、2...</span><span class="sxs-lookup"><span data-stu-id="e37a7-120">**visRowLayer** +  *i*  where  *i*  = 0, 1, 2...</span></span>  <br/> |
|<span data-ttu-id="e37a7-121">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="e37a7-121">Cell index:</span></span>  <br/> |<span data-ttu-id="e37a7-122">**visLayerLock**</span><span class="sxs-lookup"><span data-stu-id="e37a7-122">**visLayerLock**</span></span> <br/> |
   

