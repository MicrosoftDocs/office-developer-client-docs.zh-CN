---
title: PinY 单元格（“Shape Transform”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm795
localization_priority: Normal
ms.assetid: 98b86b9d-9cc0-1169-1c44-ef1505bf92fa
description: 代表 y-形状的旋转中心点 （旋转中心） 相对于其父级的原点坐标。
ms.openlocfilehash: 7002415e813ae63dafb64f416079da2e6b170494
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780859"
---
# <a name="piny-cell-shape-transform-section"></a><span data-ttu-id="04598-103">PinY 单元格（“Shape Transform”部分）</span><span class="sxs-lookup"><span data-stu-id="04598-103">PinY Cell (Shape Transform Section)</span></span>

<span data-ttu-id="04598-104">代表*y* -形状的旋转中心点 （旋转中心） 相对于其父级的原点坐标。</span><span class="sxs-lookup"><span data-stu-id="04598-104">Represents the  *y*  -coordinate of the shape's pin (center of rotation) in relation to the origin of its parent.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="04598-105">说明</span><span class="sxs-lookup"><span data-stu-id="04598-105">Remarks</span></span>

<span data-ttu-id="04598-106">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 PinY 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="04598-106">To get a reference to the PinY cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="04598-107">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="04598-107">Cell name:</span></span>  <br/> | <span data-ttu-id="04598-108">PinY</span><span class="sxs-lookup"><span data-stu-id="04598-108">PinY</span></span>  <br/> |
   
<span data-ttu-id="04598-109">要从某个程序按索引获取对 PinY 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="04598-109">To get a reference to the PinY cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="04598-110">内容索引：</span><span class="sxs-lookup"><span data-stu-id="04598-110">Section index:</span></span>  <br/> |<span data-ttu-id="04598-111">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="04598-111">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="04598-112">行索引：</span><span class="sxs-lookup"><span data-stu-id="04598-112">Row index:</span></span>  <br/> |<span data-ttu-id="04598-113">**visRowXFormOut**</span><span class="sxs-lookup"><span data-stu-id="04598-113">**visRowXFormOut**</span></span> <br/> |
| <span data-ttu-id="04598-114">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="04598-114">Cell index:</span></span>  <br/> |<span data-ttu-id="04598-115">**visXFormPinY**</span><span class="sxs-lookup"><span data-stu-id="04598-115">**visXFormPinY**</span></span> <br/> |
   

