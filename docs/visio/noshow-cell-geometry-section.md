---
title: NoShow 单元格（“Geometry”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm735
localization_priority: Normal
ms.assetid: 831075ff-2875-b598-00bb-eb8481fee57b
description: 指明路径是否显示在绘图页上。
ms.openlocfilehash: ad4d9cf1aa3e541f512bc09ffc38cf03204b3c94
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780826"
---
# <a name="noshow-cell-geometry-section"></a><span data-ttu-id="4ec55-103">NoShow 单元格（“Geometry”内容）</span><span class="sxs-lookup"><span data-stu-id="4ec55-103">NoShow Cell (Geometry Section)</span></span>

<span data-ttu-id="4ec55-104">指明路径是否显示在绘图页上。</span><span class="sxs-lookup"><span data-stu-id="4ec55-104">Indicates whether a path is displayed on the drawing page.</span></span>
  
|<span data-ttu-id="4ec55-105">**值**</span><span class="sxs-lookup"><span data-stu-id="4ec55-105">**Value**</span></span>|<span data-ttu-id="4ec55-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="4ec55-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="4ec55-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="4ec55-107">TRUE</span></span>  <br/> | <span data-ttu-id="4ec55-108">隐藏本内容所表示的路径的划线和填充。</span><span class="sxs-lookup"><span data-stu-id="4ec55-108">The stroke and fill of the path represented by the section is hidden.</span></span>  <br/> |
| <span data-ttu-id="4ec55-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="4ec55-109">FALSE</span></span>  <br/> | <span data-ttu-id="4ec55-110">显示路径的划线和填充。</span><span class="sxs-lookup"><span data-stu-id="4ec55-110">The stroke and fill of the path is shown.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4ec55-111">注释</span><span class="sxs-lookup"><span data-stu-id="4ec55-111">Remarks</span></span>

<span data-ttu-id="4ec55-112">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 NoShow 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="4ec55-112">To get a reference to the NoShow cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="4ec55-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="4ec55-113">Cell name:</span></span>  <br/> | <span data-ttu-id="4ec55-114">Geometry *i* 。NoShow 其中*i* = < 1 >，2，3...</span><span class="sxs-lookup"><span data-stu-id="4ec55-114">Geometry  *i*  .NoShow            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="4ec55-115">若要从某个程序按索引获取对 NoShow 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="4ec55-115">To get a reference to the NoShow cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="4ec55-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="4ec55-116">Section index:</span></span>  <br/> |<span data-ttu-id="4ec55-117">**visSectionFirstComponent** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="4ec55-117">**visSectionFirstComponent** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="4ec55-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="4ec55-118">Row index:</span></span>  <br/> |<span data-ttu-id="4ec55-119">**visRowComponent**</span><span class="sxs-lookup"><span data-stu-id="4ec55-119">**visRowComponent**</span></span> <br/> |
| <span data-ttu-id="4ec55-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="4ec55-120">Cell index:</span></span>  <br/> |<span data-ttu-id="4ec55-121">**visCompNoShow**</span><span class="sxs-lookup"><span data-stu-id="4ec55-121">**visCompNoShow**</span></span> <br/> |
   

