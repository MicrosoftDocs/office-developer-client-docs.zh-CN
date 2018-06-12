---
title: AvoidPageBreaks 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm80000
localization_priority: Normal
ms.assetid: 7d2ec869-7ffa-3b41-8126-3f4889501e0c
description: 确定当形状是增量对齐和/或增量间距时是否可以将其放在分页符上。
ms.openlocfilehash: 045ceca430c6c285ad4e454b9d17f9dbd7492a4c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779659"
---
# <a name="avoidpagebreaks-cell-page-layout-section"></a><span data-ttu-id="0daba-103">AvoidPageBreaks 单元格（“Page Layout”内容）</span><span class="sxs-lookup"><span data-stu-id="0daba-103">AvoidPageBreaks Cell (Page Layout Section)</span></span>

<span data-ttu-id="0daba-104">确定当形状是增量对齐和/或增量间距时是否可以将其放在分页符上。</span><span class="sxs-lookup"><span data-stu-id="0daba-104">Determines whether shapes can be placed over page breaks when the shapes are incrementally aligned, incrementally spaced, or both.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="0daba-105">备注</span><span class="sxs-lookup"><span data-stu-id="0daba-105">Remarks</span></span>

<span data-ttu-id="0daba-106">若要获取对 AvoidPageBreaks 单元格的引用按名称从另一个公式或从程序使用**CellsU**属性，请使用以下内容。</span><span class="sxs-lookup"><span data-stu-id="0daba-106">To get a reference to the AvoidPageBreaks cell by name from another formula, or from a program by using the **CellsU** property, use the following.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="0daba-107">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="0daba-107">Cell name:</span></span>  <br/> |<span data-ttu-id="0daba-108">AvoidPageBreaks</span><span class="sxs-lookup"><span data-stu-id="0daba-108">AvoidPageBreaks</span></span>  <br/> |
   
<span data-ttu-id="0daba-109">若要从某个程序按索引获取对 AvoidPageBreaks 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="0daba-109">To get a reference to the AvoidPageBreaks cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="0daba-110">内容索引：</span><span class="sxs-lookup"><span data-stu-id="0daba-110">Section index:</span></span>  <br/> |<span data-ttu-id="0daba-111">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="0daba-111">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="0daba-112">行索引：</span><span class="sxs-lookup"><span data-stu-id="0daba-112">Row index:</span></span>  <br/> |<span data-ttu-id="0daba-113">**visRowPageLayout**</span><span class="sxs-lookup"><span data-stu-id="0daba-113">**visRowPageLayout**</span></span> <br/> |
|<span data-ttu-id="0daba-114">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="0daba-114">Cell index:</span></span>  <br/> |<span data-ttu-id="0daba-115">**visPLOAvoidPageBreaks**</span><span class="sxs-lookup"><span data-stu-id="0daba-115">**visPLOAvoidPageBreaks**</span></span> <br/> |
   

