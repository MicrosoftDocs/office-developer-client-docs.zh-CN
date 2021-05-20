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
description: 表示本地坐标中连接点的 x 坐标。
ms.openlocfilehash: 496e5af6ea5b7ba99730b23dcbb510db6af9b23b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436781"
---
# <a name="x-cell-connection-points-section"></a><span data-ttu-id="6003f-103">X 单元格（“Connection Points”内容）</span><span class="sxs-lookup"><span data-stu-id="6003f-103">X Cell (Connection Points Section)</span></span>

<span data-ttu-id="6003f-104">表示本地坐标中连接点的  *x*  坐标。</span><span class="sxs-lookup"><span data-stu-id="6003f-104">Represents the  *x*  -coordinate for a connection point in local coordinates.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="6003f-105">备注</span><span class="sxs-lookup"><span data-stu-id="6003f-105">Remarks</span></span>

<span data-ttu-id="6003f-106">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 X 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="6003f-106">To get a reference to the X cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="6003f-107">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="6003f-107">Cell name:</span></span>  <br/> | <span data-ttu-id="6003f-108">Connections.X  *i*            其中  *i*  = <1>、2、3...</span><span class="sxs-lookup"><span data-stu-id="6003f-108">Connections.X  *i*            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="6003f-109">要从某个程序按索引获取对 X 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="6003f-109">To get a reference to the X cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="6003f-110">内容索引：</span><span class="sxs-lookup"><span data-stu-id="6003f-110">Section index:</span></span>  <br/> |<span data-ttu-id="6003f-111">**visSectionConnectionPts**</span><span class="sxs-lookup"><span data-stu-id="6003f-111">**visSectionConnectionPts**</span></span> <br/> |
| <span data-ttu-id="6003f-112">行索引：</span><span class="sxs-lookup"><span data-stu-id="6003f-112">Row index:</span></span>  <br/> |<span data-ttu-id="6003f-113">**visRowConnectionPts**  +  *i* 其中 *i* = 0、1、2...</span><span class="sxs-lookup"><span data-stu-id="6003f-113">**visRowConnectionPts** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="6003f-114">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="6003f-114">Cell index:</span></span>  <br/> |<span data-ttu-id="6003f-115">**visX**</span><span class="sxs-lookup"><span data-stu-id="6003f-115">**visX**</span></span> <br/> |
   

