---
title: DirY / B 单元格（“Connection Points”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm240
localization_priority: Normal
ms.assetid: d951c57d-2c22-0289-35af-44e3c2877b2c
description: 确定匹配连接点所需的对齐向量的 y 分量。 它还用于确定动态连接线所附引线的方向。 此单元格采用浮点值。
ms.openlocfilehash: b0dc3c9f7e1a9e87b2ecdace21c8fa1658b1388d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417089"
---
# <a name="diry--b-cell-connection-points-section"></a><span data-ttu-id="8b14f-105">DirY / B 单元格（“Connection Points”内容）</span><span class="sxs-lookup"><span data-stu-id="8b14f-105">DirY / B Cell (Connection Points Section)</span></span>

<span data-ttu-id="8b14f-106">确定匹配连接点所需的对齐向量的  *y*  分量。</span><span class="sxs-lookup"><span data-stu-id="8b14f-106">Determines the  *y*  -component for the required alignment vector of a matching connection point.</span></span> <span data-ttu-id="8b14f-107">它还用于确定动态连接线所附引线的方向。</span><span class="sxs-lookup"><span data-stu-id="8b14f-107">It is also used to orient the attached leg of a dynamic connector.</span></span> <span data-ttu-id="8b14f-108">此单元格采用浮点值。</span><span class="sxs-lookup"><span data-stu-id="8b14f-108">This cell takes a floating point value.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="8b14f-109">备注</span><span class="sxs-lookup"><span data-stu-id="8b14f-109">Remarks</span></span>

<span data-ttu-id="8b14f-110">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 DirY / B 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="8b14f-110">To get a reference to the DirY / B cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="8b14f-111">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="8b14f-111">Cell name:</span></span>  <br/> |<span data-ttu-id="8b14f-112">Connections.DirY[ *i*  ] 其中  *i*  = <1>， 2， 3...</span><span class="sxs-lookup"><span data-stu-id="8b14f-112">Connections.DirY[ *i*  ]           where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="8b14f-113">要从某个程序按索引获取对 DirY / B 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="8b14f-113">To get a reference to the DirY / B cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="8b14f-114">内容索引：</span><span class="sxs-lookup"><span data-stu-id="8b14f-114">Section index:</span></span>  <br/> |<span data-ttu-id="8b14f-115">**visSectionConnectionPts**</span><span class="sxs-lookup"><span data-stu-id="8b14f-115">**visSectionConnectionPts**</span></span> <br/> |
|<span data-ttu-id="8b14f-116">行索引：</span><span class="sxs-lookup"><span data-stu-id="8b14f-116">Row index:</span></span>  <br/> |<span data-ttu-id="8b14f-117">**visRowConnectionPts**  +  *i* 其中 *i* = 0、1、2...</span><span class="sxs-lookup"><span data-stu-id="8b14f-117">**visRowConnectionPts** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
|<span data-ttu-id="8b14f-118">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="8b14f-118">Cell index:</span></span>  <br/> |<span data-ttu-id="8b14f-119">**visCnnctDirY** (          **visCnnctB**) 扩展行 (未扩展) </span><span class="sxs-lookup"><span data-stu-id="8b14f-119">**visCnnctDirY** (non-extended rows)           **visCnnctB** (extended rows)</span></span>  <br/> |
   
<span data-ttu-id="8b14f-120">有关扩展行和非扩展行的信息，请参见 Connection Points 行。</span><span class="sxs-lookup"><span data-stu-id="8b14f-120">For information about non-extended and extended rows, see Connection Points row.</span></span>
  

