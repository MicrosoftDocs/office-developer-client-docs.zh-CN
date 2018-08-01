---
title: EndX 单元格（“1-D Endpoints”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm335
localization_priority: Normal
ms.assetid: 24261b77-e3e8-7434-a503-9f23798bdab1
description: 代表 x-一维形状相对于其父级原点的终结点的坐标。
ms.openlocfilehash: f7324d9d4df5c428f734da255e7dd65b24cb0cb0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780194"
---
# <a name="endx-cell-1-d-endpoints-section"></a><span data-ttu-id="ddd74-103">EndX 单元格（“1-D Endpoints”部分）</span><span class="sxs-lookup"><span data-stu-id="ddd74-103">EndX Cell (1-D Endpoints Section)</span></span>

<span data-ttu-id="ddd74-104">代表*x* -一维形状相对于其父级原点的终结点的坐标。</span><span class="sxs-lookup"><span data-stu-id="ddd74-104">Represents the  *x*  -coordinate of the endpoint of the 1-D shape, in relation to the origin of its parent.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="ddd74-105">说明</span><span class="sxs-lookup"><span data-stu-id="ddd74-105">Remarks</span></span>

<span data-ttu-id="ddd74-106">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 EndX 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="ddd74-106">To get a reference to the EndX cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="ddd74-107">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="ddd74-107">Cell name:</span></span>  <br/> | <span data-ttu-id="ddd74-108">EndX</span><span class="sxs-lookup"><span data-stu-id="ddd74-108">EndX</span></span>  <br/> |
   
<span data-ttu-id="ddd74-109">要从某个程序按索引获取对 EndX 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="ddd74-109">To get a reference to the EndX cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="ddd74-110">内容索引：</span><span class="sxs-lookup"><span data-stu-id="ddd74-110">Section index:</span></span>  <br/> |<span data-ttu-id="ddd74-111">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="ddd74-111">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="ddd74-112">行索引：</span><span class="sxs-lookup"><span data-stu-id="ddd74-112">Row index:</span></span>  <br/> |<span data-ttu-id="ddd74-113">**visRowXForm1D**</span><span class="sxs-lookup"><span data-stu-id="ddd74-113">**visRowXForm1D**</span></span> <br/> |
| <span data-ttu-id="ddd74-114">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="ddd74-114">Cell index:</span></span>  <br/> |<span data-ttu-id="ddd74-115">**vis1DEndX**</span><span class="sxs-lookup"><span data-stu-id="ddd74-115">**vis1DEndX**</span></span> <br/> |
   

