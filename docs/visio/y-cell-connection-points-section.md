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
description: 表示连接点在本地坐标系中的 y 坐标。
ms.openlocfilehash: b408dc3c07e7bd28c0530b09f649453b4f08c770
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360128"
---
# <a name="y-cell-connection-points-section"></a><span data-ttu-id="1ebcf-103">Y 单元格（“Connection Points”内容）</span><span class="sxs-lookup"><span data-stu-id="1ebcf-103">Y Cell (Connection Points Section)</span></span>

<span data-ttu-id="1ebcf-104">表示连接点在本地坐标系中的*y*坐标。</span><span class="sxs-lookup"><span data-stu-id="1ebcf-104">Represents the  *y*  -coordinate for a connection point in local coordinates.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="1ebcf-105">注解</span><span class="sxs-lookup"><span data-stu-id="1ebcf-105">Remarks</span></span>

<span data-ttu-id="1ebcf-106">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Y 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="1ebcf-106">To get a reference to the Y cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="1ebcf-107">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="1ebcf-107">Cell name:</span></span>  <br/> | <span data-ttu-id="1ebcf-108">连接。 Y *i*其中*i* = <1>, 2, 3 .。。</span><span class="sxs-lookup"><span data-stu-id="1ebcf-108">Connections.Y  *i*            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="1ebcf-109">要从某个程序按索引获取对 Y 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="1ebcf-109">To get a reference to the Y cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="1ebcf-110">内容索引：</span><span class="sxs-lookup"><span data-stu-id="1ebcf-110">Section index:</span></span>  <br/> |<span data-ttu-id="1ebcf-111">**visSectionConnectionPts**</span><span class="sxs-lookup"><span data-stu-id="1ebcf-111">**visSectionConnectionPts**</span></span> <br/> |
| <span data-ttu-id="1ebcf-112">行索引：</span><span class="sxs-lookup"><span data-stu-id="1ebcf-112">Row index:</span></span>  <br/> |<span data-ttu-id="1ebcf-113">**visRowConnectionPts** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="1ebcf-113">**visRowConnectionPts** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="1ebcf-114">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="1ebcf-114">Cell index:</span></span>  <br/> |<span data-ttu-id="1ebcf-115">**visY**</span><span class="sxs-lookup"><span data-stu-id="1ebcf-115">**visY**</span></span> <br/> |
   

