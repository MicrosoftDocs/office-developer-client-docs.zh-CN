---
title: Comment 单元格（“Annotation”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60033
localization_priority: Normal
ms.assetid: b367841a-f31c-4b55-4491-2abab5811dbe
description: 包含出现在注释中的文本。
ms.openlocfilehash: fd9dce2618c0b8c967b794b0beea8b772a231003
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415528"
---
# <a name="comment-cell-annotation-section"></a><span data-ttu-id="ead4b-103">Comment 单元格（“Annotation”内容）</span><span class="sxs-lookup"><span data-stu-id="ead4b-103">Comment Cell (Annotation Section)</span></span>

<span data-ttu-id="ead4b-104">包含出现在注释中的文本。</span><span class="sxs-lookup"><span data-stu-id="ead4b-104">Contains the text that appears in a comment.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ead4b-105">此单元格仅用于在 Microsoft Visio 2013 中打开 .vsd 文件或以 .vsd 文件格式保存 .vsdx 文件时跟踪注释。</span><span class="sxs-lookup"><span data-stu-id="ead4b-105">This cell is used for tracking comments only when opening a .vsd file in Microsoft Visio 2013 or when saving a .vsdx file in the .vsd file format.</span></span> <span data-ttu-id="ead4b-106">它不用于跟踪 2013 年 10 月 Visio中的注释。</span><span class="sxs-lookup"><span data-stu-id="ead4b-106">It is not used for tracking comments in .vsdx documents in Visio 2013.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="ead4b-107">备注</span><span class="sxs-lookup"><span data-stu-id="ead4b-107">Remarks</span></span>

<span data-ttu-id="ead4b-108">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Comment 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="ead4b-108">To get a reference to the Comment cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="ead4b-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="ead4b-109">Cell name:</span></span>  <br/> | <span data-ttu-id="ead4b-110">Annotation.Comment[  *i*  ] 其中  *i*  = <1>，2， 3...</span><span class="sxs-lookup"><span data-stu-id="ead4b-110">Annotation.Comment[  *i*  ]            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="ead4b-111">要从某个程序按索引获取对 Comment 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="ead4b-111">To get a reference to the Comment cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="ead4b-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="ead4b-112">Section index:</span></span>  <br/> |<span data-ttu-id="ead4b-113">**visSectionAnnotation**</span><span class="sxs-lookup"><span data-stu-id="ead4b-113">**visSectionAnnotation**</span></span> <br/> |
| <span data-ttu-id="ead4b-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="ead4b-114">Row index:</span></span>  <br/> |<span data-ttu-id="ead4b-115">**visRowAnnotation**  +  *i* 其中 *i* = 0、1、2...</span><span class="sxs-lookup"><span data-stu-id="ead4b-115">**visRowAnnotation** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="ead4b-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="ead4b-116">Cell index:</span></span>  <br/> |<span data-ttu-id="ead4b-117">**visAnnotationComment**</span><span class="sxs-lookup"><span data-stu-id="ead4b-117">**visAnnotationComment**</span></span> <br/> |
   

