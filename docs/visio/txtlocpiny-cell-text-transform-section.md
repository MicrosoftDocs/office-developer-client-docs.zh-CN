---
title: TxtLocPinY 单元格（“Text Transform”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251276
localization_priority: Normal
ms.assetid: 3f46cfcf-7eac-4a37-e782-39f4e7f8fc43
description: 确定 y-文本块的相对于原点的文本块的旋转中心的坐标。 默认公式为：
ms.openlocfilehash: 7d43f63b8560df5fc5daf09a429ce30ec976d131
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781568"
---
# <a name="txtlocpiny-cell-text-transform-section"></a><span data-ttu-id="31ecd-104">TxtLocPinY 单元格（“Text Transform”内容）</span><span class="sxs-lookup"><span data-stu-id="31ecd-104">TxtLocPinY Cell (Text Transform Section)</span></span>

<span data-ttu-id="31ecd-105">确定*y* -文本块的相对于原点的文本块的旋转中心的坐标。</span><span class="sxs-lookup"><span data-stu-id="31ecd-105">Determines the  *y*  -coordinate of the text block's center of rotation relative to the origin of the text block.</span></span> <span data-ttu-id="31ecd-106">默认公式为：</span><span class="sxs-lookup"><span data-stu-id="31ecd-106">The default formula is:</span></span> 
  
<span data-ttu-id="31ecd-107">= TxtHeight \* 0.5</span><span class="sxs-lookup"><span data-stu-id="31ecd-107">= TxtHeight \* 0.5</span></span>
  
## <a name="remarks"></a><span data-ttu-id="31ecd-108">备注</span><span class="sxs-lookup"><span data-stu-id="31ecd-108">Remarks</span></span>

<span data-ttu-id="31ecd-109">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 TxtLocPinY 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="31ecd-109">To get a reference to the TxtLocPinY cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="31ecd-110">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="31ecd-110">Cell name:</span></span>  <br/> | <span data-ttu-id="31ecd-111">TxtLocPinY</span><span class="sxs-lookup"><span data-stu-id="31ecd-111">TxtLocPinY</span></span>  <br/> |
   
<span data-ttu-id="31ecd-112">若要从某个程序按索引获取对 TxtLocPinY 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="31ecd-112">To get a reference to the TxtLocPinY cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="31ecd-113">内容索引：</span><span class="sxs-lookup"><span data-stu-id="31ecd-113">Section index:</span></span>  <br/> |<span data-ttu-id="31ecd-114">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="31ecd-114">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="31ecd-115">行索引：</span><span class="sxs-lookup"><span data-stu-id="31ecd-115">Row index:</span></span>  <br/> |<span data-ttu-id="31ecd-116">**visRowTextXForm**</span><span class="sxs-lookup"><span data-stu-id="31ecd-116">**visRowTextXForm**</span></span> <br/> |
| <span data-ttu-id="31ecd-117">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="31ecd-117">Cell index:</span></span>  <br/> |<span data-ttu-id="31ecd-118">**visXFormLocPinY**</span><span class="sxs-lookup"><span data-stu-id="31ecd-118">**visXFormLocPinY**</span></span> <br/> |
   

