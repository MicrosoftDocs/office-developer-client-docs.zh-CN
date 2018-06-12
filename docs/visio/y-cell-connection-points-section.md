---
title: Y 单元格（“Connection Points”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_SDR.chm1175
localization_priority: Normal
ms.assetid: 3af6c949-d6a0-9560-54d7-b01a2ad99960
description: 代表 y-在本地坐标系中的连接点的坐标。
ms.openlocfilehash: 270ae98789e29ca170f260aa70e951d4b2af2962
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781688"
---
# <a name="y-cell-connection-points-section"></a><span data-ttu-id="7bde0-103">Y 单元格（“Connection Points”内容）</span><span class="sxs-lookup"><span data-stu-id="7bde0-103">Y Cell (Connection Points Section)</span></span>

<span data-ttu-id="7bde0-104">代表*y* -在本地坐标系中的连接点的坐标。</span><span class="sxs-lookup"><span data-stu-id="7bde0-104">Represents the  *y*  -coordinate for a connection point in local coordinates.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="7bde0-105">备注</span><span class="sxs-lookup"><span data-stu-id="7bde0-105">Remarks</span></span>

<span data-ttu-id="7bde0-106">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 Y 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="7bde0-106">To get a reference to the Y cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="7bde0-107">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="7bde0-107">Cell name:</span></span>  <br/> | <span data-ttu-id="7bde0-108">Connections.Y *i*其中*i* = < 1 >，2，3...</span><span class="sxs-lookup"><span data-stu-id="7bde0-108">Connections.Y  *i*            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="7bde0-109">若要从某个程序按索引获取对 Y 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="7bde0-109">To get a reference to the Y cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="7bde0-110">内容索引：</span><span class="sxs-lookup"><span data-stu-id="7bde0-110">Section index:</span></span>  <br/> |<span data-ttu-id="7bde0-111">**visSectionConnectionPts**</span><span class="sxs-lookup"><span data-stu-id="7bde0-111">**visSectionConnectionPts**</span></span> <br/> |
| <span data-ttu-id="7bde0-112">行索引：</span><span class="sxs-lookup"><span data-stu-id="7bde0-112">Row index:</span></span>  <br/> |<span data-ttu-id="7bde0-113">**visRowConnectionPts** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="7bde0-113">**visRowConnectionPts** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="7bde0-114">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="7bde0-114">Cell index:</span></span>  <br/> |<span data-ttu-id="7bde0-115">**visY**</span><span class="sxs-lookup"><span data-stu-id="7bde0-115">**visY**</span></span> <br/> |
   

