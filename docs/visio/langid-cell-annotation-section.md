---
title: LangID 单元格（“Annotation”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60048
localization_priority: Normal
ms.assetid: b6f5ea5e-b350-0817-d631-f059b9b95c23
description: 指示输入注释所使用的语言。
ms.openlocfilehash: 0de5ed8136a3fb1bbdca9fea0ebb5894e62cf907
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780524"
---
# <a name="langid-cell-annotation-section"></a><span data-ttu-id="0fac5-103">LangID 单元格（“Annotation”部分）</span><span class="sxs-lookup"><span data-stu-id="0fac5-103">LangID Cell (Annotation Section)</span></span>

<span data-ttu-id="0fac5-104">指示输入注释所使用的语言。</span><span class="sxs-lookup"><span data-stu-id="0fac5-104">Indicates the language in which the comment was entered.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0fac5-105">此单元格用于跟踪注释，仅当打开 Microsoft Visio 2013 中的.vsd 文件或.vsd 文件格式保存.vsdx 文件时。</span><span class="sxs-lookup"><span data-stu-id="0fac5-105">This cell is used for tracking comments only when opening a .vsd file in Microsoft Visio 2013 or when saving a .vsdx file in the .vsd file format.</span></span> <span data-ttu-id="0fac5-106">它不用于跟踪.vsdx Visio 2013 中的文档中的注释。</span><span class="sxs-lookup"><span data-stu-id="0fac5-106">It is not used for tracking comments in .vsdx documents in Visio 2013.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="0fac5-107">说明</span><span class="sxs-lookup"><span data-stu-id="0fac5-107">Remarks</span></span>

<span data-ttu-id="0fac5-p102">此值是输入注释时在语言栏上激活的语言的区域设置 ID (LCID)。有关 Microsoft Office 应用程序所支持的语言的列表，请参阅“[DocLangID](doclangid-cell-document-properties-section.md) 单元格（‘Document Properties’内容）”这一主题。</span><span class="sxs-lookup"><span data-stu-id="0fac5-p102">This value is the locale ID (LCID) of the language that is active on the language bar when the comment was entered. For a list of languages supported by Microsoft Office applications, see the [DocLangID](doclangid-cell-document-properties-section.md) Cell (Document Properties Section) topic.</span></span> 
  
<span data-ttu-id="0fac5-110">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 LangID 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="0fac5-110">To get a reference to the LangID cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="0fac5-111">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="0fac5-111">Cell name:</span></span>  <br/> | <span data-ttu-id="0fac5-112">Annotation.LangID [ *i* ] 其中*i* = < 1 >，2，3...</span><span class="sxs-lookup"><span data-stu-id="0fac5-112">Annotation.LangID[  *i*  ]            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="0fac5-113">若要从某个程序按索引获取对 LangID 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="0fac5-113">To get a reference to the LangID cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="0fac5-114">内容索引：</span><span class="sxs-lookup"><span data-stu-id="0fac5-114">Section index:</span></span>  <br/> |<span data-ttu-id="0fac5-115">**visSectionAnnotation**</span><span class="sxs-lookup"><span data-stu-id="0fac5-115">**visSectionAnnotation**</span></span> <br/> |
| <span data-ttu-id="0fac5-116">行索引：</span><span class="sxs-lookup"><span data-stu-id="0fac5-116">Row index:</span></span>  <br/> |<span data-ttu-id="0fac5-117">**visRowAnnotation** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="0fac5-117">**visRowAnnotation** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="0fac5-118">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="0fac5-118">Cell index:</span></span>  <br/> |<span data-ttu-id="0fac5-119">**visAnnotationLangID**</span><span class="sxs-lookup"><span data-stu-id="0fac5-119">**visAnnotationLangID**</span></span> <br/> |
   

