---
title: X 单元格（“Connection Points”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251746
localization_priority: Normal
ms.assetid: 11c69600-4e1f-4c52-ff35-b6a7cc6c734c
description: 代表 x-在本地坐标系中的连接点的坐标。
ms.openlocfilehash: 27821f9aa94f97d8e019d7c7307c036549bf807b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781674"
---
# <a name="x-cell-connection-points-section"></a><span data-ttu-id="c9173-103">X 单元格（“Connection Points”内容）</span><span class="sxs-lookup"><span data-stu-id="c9173-103">X Cell (Connection Points Section)</span></span>

<span data-ttu-id="c9173-104">代表*x* -在本地坐标系中的连接点的坐标。</span><span class="sxs-lookup"><span data-stu-id="c9173-104">Represents the  *x*  -coordinate for a connection point in local coordinates.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="c9173-105">备注</span><span class="sxs-lookup"><span data-stu-id="c9173-105">Remarks</span></span>

<span data-ttu-id="c9173-106">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 X 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="c9173-106">To get a reference to the X cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="c9173-107">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="c9173-107">Cell name:</span></span>  <br/> | <span data-ttu-id="c9173-108">创建两个*i*其中*i* = < 1 >，2，3...</span><span class="sxs-lookup"><span data-stu-id="c9173-108">Connections.X  *i*            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="c9173-109">若要从某个程序按索引获取对 X 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="c9173-109">To get a reference to the X cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="c9173-110">内容索引：</span><span class="sxs-lookup"><span data-stu-id="c9173-110">Section index:</span></span>  <br/> |<span data-ttu-id="c9173-111">**visSectionConnectionPts**</span><span class="sxs-lookup"><span data-stu-id="c9173-111">**visSectionConnectionPts**</span></span> <br/> |
| <span data-ttu-id="c9173-112">行索引：</span><span class="sxs-lookup"><span data-stu-id="c9173-112">Row index:</span></span>  <br/> |<span data-ttu-id="c9173-113">**visRowConnectionPts** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="c9173-113">**visRowConnectionPts** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="c9173-114">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="c9173-114">Cell index:</span></span>  <br/> |<span data-ttu-id="c9173-115">**visX**</span><span class="sxs-lookup"><span data-stu-id="c9173-115">**visX**</span></span> <br/> |
   

