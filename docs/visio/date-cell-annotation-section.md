---
title: Date 单元格（“Annotation”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60036
localization_priority: Normal
ms.assetid: f1f11803-614b-a40d-0a2d-131093e7609e
description: 包含最后编辑注释的日期和时间。
ms.openlocfilehash: 4b6e7ea70302b10728d82f36ad0db39077af9523
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780050"
---
# <a name="date-cell-annotation-section"></a><span data-ttu-id="4b866-103">Date 单元格（“Annotation”部分）</span><span class="sxs-lookup"><span data-stu-id="4b866-103">Date Cell (Annotation Section)</span></span>

<span data-ttu-id="4b866-104">包含最后编辑注释的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="4b866-104">Contains the date and time the comment was last edited.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="4b866-105">此单元格用于跟踪注释，仅当打开 Microsoft Visio 2013 中的.vsd 文件或.vsd 文件格式保存.vsdx 文件时。</span><span class="sxs-lookup"><span data-stu-id="4b866-105">This cell is used for tracking comments only when opening a .vsd file in Microsoft Visio 2013 or when saving a .vsdx file in the .vsd file format.</span></span> <span data-ttu-id="4b866-106">它不用于跟踪.vsdx Visio 2013 中的文档中的注释。</span><span class="sxs-lookup"><span data-stu-id="4b866-106">It is not used for tracking comments in .vsdx documents in Visio 2013.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="4b866-107">注释</span><span class="sxs-lookup"><span data-stu-id="4b866-107">Remarks</span></span>

<span data-ttu-id="4b866-108">该日期仅出现在用户界面的注释框中。</span><span class="sxs-lookup"><span data-stu-id="4b866-108">Only the date appears in the comment box in the user interface.</span></span>
  
<span data-ttu-id="4b866-109">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Date 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="4b866-109">To get a reference to the Date cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="4b866-110">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="4b866-110">Cell name:</span></span>  <br/> | <span data-ttu-id="4b866-111">Annotation.Date [ *i* ] 其中*i* = < 1 >，2，3...</span><span class="sxs-lookup"><span data-stu-id="4b866-111">Annotation.Date[  *i*  ]            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="4b866-112">要从某个程序按索引获取对 Date 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="4b866-112">To get a reference to the Date cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="4b866-113">内容索引：</span><span class="sxs-lookup"><span data-stu-id="4b866-113">Section index:</span></span>  <br/> |<span data-ttu-id="4b866-114">**visSectionAnnotation**</span><span class="sxs-lookup"><span data-stu-id="4b866-114">**visSectionAnnotation**</span></span> <br/> |
| <span data-ttu-id="4b866-115">行索引：</span><span class="sxs-lookup"><span data-stu-id="4b866-115">Row index:</span></span>  <br/> |<span data-ttu-id="4b866-116">**visRowAnnotation** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="4b866-116">**visRowAnnotation** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="4b866-117">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="4b866-117">Cell index:</span></span>  <br/> |<span data-ttu-id="4b866-118">**visAnnotationDate**</span><span class="sxs-lookup"><span data-stu-id="4b866-118">**visAnnotationDate**</span></span> <br/> |
   

