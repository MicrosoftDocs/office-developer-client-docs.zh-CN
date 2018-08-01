---
title: DirX / A 单元格（“Connection Points”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251721
localization_priority: Normal
ms.assetid: 00d87b92-0da7-37d6-e7b5-23f350db0a9b
description: 确定 x-组件所需的对齐向量的匹配连接点。 DirX / A 单元格还用于确定动态连接线的附加的线路。 此单元格采用浮点数据点值。
ms.openlocfilehash: 49feba7cefbccc4efcbd04e8940c1f801563539e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780115"
---
# <a name="dirx--a-cell-connection-points-section"></a><span data-ttu-id="52380-105">DirX / A 单元格（“Connection Points”部分）</span><span class="sxs-lookup"><span data-stu-id="52380-105">DirX / A Cell (Connection Points Section)</span></span>

<span data-ttu-id="52380-106">确定*x* -组件所需的对齐向量的匹配连接点。</span><span class="sxs-lookup"><span data-stu-id="52380-106">Determines the  *x*  -component for the required alignment vector of a matching connection point.</span></span> <span data-ttu-id="52380-107">DirX / A 单元格还用于确定动态连接线的附加的线路。</span><span class="sxs-lookup"><span data-stu-id="52380-107">The DirX / A cell is also used to orient the attached leg of a dynamic connector.</span></span> <span data-ttu-id="52380-108">此单元格采用浮点数据点值。</span><span class="sxs-lookup"><span data-stu-id="52380-108">This cell takes a floating point value.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="52380-109">说明</span><span class="sxs-lookup"><span data-stu-id="52380-109">Remarks</span></span>

<span data-ttu-id="52380-110">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 DirX / A 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="52380-110">To get a reference to the DirX / A cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="52380-111">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="52380-111">Cell name:</span></span>  <br/> | <span data-ttu-id="52380-112">Connections.DirX [ *i* ] 其中*i* = < 1 >，2，3...</span><span class="sxs-lookup"><span data-stu-id="52380-112">Connections.DirX[  *i*  ]            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="52380-113">要从某个程序按索引获取对 DirX / A 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="52380-113">To get a reference to the DirX / A cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="52380-114">内容索引：</span><span class="sxs-lookup"><span data-stu-id="52380-114">Section index:</span></span>  <br/> |<span data-ttu-id="52380-115">**visSectionConnectionPts**</span><span class="sxs-lookup"><span data-stu-id="52380-115">**visSectionConnectionPts**</span></span> <br/> |
| <span data-ttu-id="52380-116">行索引：</span><span class="sxs-lookup"><span data-stu-id="52380-116">Row index:</span></span>  <br/> |<span data-ttu-id="52380-117">**visRowConnectionPts** +  *i*其中*i* = 0、 1、 2</span><span class="sxs-lookup"><span data-stu-id="52380-117">**visRowConnectionPts** +  *i*            where  *i*  = 0, 1, 2</span></span>  <br/> |
| <span data-ttu-id="52380-118">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="52380-118">Cell index:</span></span>  <br/> |<span data-ttu-id="52380-119">**visCnnctDirX**（非扩展行）          **visCnnctA**（扩展的行）</span><span class="sxs-lookup"><span data-stu-id="52380-119">**visCnnctDirX** (non-extended rows)           **visCnnctA** (extended rows)</span></span>  <br/> |
   
<span data-ttu-id="52380-120">有关扩展行和非扩展行的信息，请参见 Connection Points 行。</span><span class="sxs-lookup"><span data-stu-id="52380-120">For information about non-extended and extended rows, see Connection Points row.</span></span>
  

