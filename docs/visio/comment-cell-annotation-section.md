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
ms.openlocfilehash: 443a229058a9ca910ba5b38b093706c9c2e3e95b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779897"
---
# <a name="comment-cell-annotation-section"></a><span data-ttu-id="a2c60-103">Comment 单元格（“Annotation”内容）</span><span class="sxs-lookup"><span data-stu-id="a2c60-103">Comment Cell (Annotation Section)</span></span>

<span data-ttu-id="a2c60-104">包含出现在注释中的文本。</span><span class="sxs-lookup"><span data-stu-id="a2c60-104">Contains the text that appears in a comment.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a2c60-105">此单元格用于跟踪注释，仅当打开 Microsoft Visio 2013 中的.vsd 文件或.vsd 文件格式保存.vsdx 文件时。</span><span class="sxs-lookup"><span data-stu-id="a2c60-105">This cell is used for tracking comments only when opening a .vsd file in Microsoft Visio 2013 or when saving a .vsdx file in the .vsd file format.</span></span> <span data-ttu-id="a2c60-106">它不用于跟踪.vsdx Visio 2013 中的文档中的注释。</span><span class="sxs-lookup"><span data-stu-id="a2c60-106">It is not used for tracking comments in .vsdx documents in Visio 2013.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="a2c60-107">备注</span><span class="sxs-lookup"><span data-stu-id="a2c60-107">Remarks</span></span>

<span data-ttu-id="a2c60-108">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 Comment 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="a2c60-108">To get a reference to the Comment cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="a2c60-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="a2c60-109">Cell name:</span></span>  <br/> | <span data-ttu-id="a2c60-110">Annotation.Comment [ *i* ] 其中*i* = < 1 >，2，3...</span><span class="sxs-lookup"><span data-stu-id="a2c60-110">Annotation.Comment[  *i*  ]            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="a2c60-111">若要从某个程序按索引获取对 Comment 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="a2c60-111">To get a reference to the Comment cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="a2c60-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="a2c60-112">Section index:</span></span>  <br/> |<span data-ttu-id="a2c60-113">**visSectionAnnotation**</span><span class="sxs-lookup"><span data-stu-id="a2c60-113">**visSectionAnnotation**</span></span> <br/> |
| <span data-ttu-id="a2c60-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="a2c60-114">Row index:</span></span>  <br/> |<span data-ttu-id="a2c60-115">**visRowAnnotation** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="a2c60-115">**visRowAnnotation** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="a2c60-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="a2c60-116">Cell index:</span></span>  <br/> |<span data-ttu-id="a2c60-117">**visAnnotationComment**</span><span class="sxs-lookup"><span data-stu-id="a2c60-117">**visAnnotationComment**</span></span> <br/> |
   

