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
ms.openlocfilehash: b3b2cba3d0a04f75ef2d87f0ee8dcd1f8115e15e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422255"
---
# <a name="langid-cell-annotation-section"></a><span data-ttu-id="19fd6-103">LangID 单元格（“Annotation”内容）</span><span class="sxs-lookup"><span data-stu-id="19fd6-103">LangID Cell (Annotation Section)</span></span>

<span data-ttu-id="19fd6-104">指示输入注释所使用的语言。</span><span class="sxs-lookup"><span data-stu-id="19fd6-104">Indicates the language in which the comment was entered.</span></span>
  
> [!NOTE]
> <span data-ttu-id="19fd6-105">此单元格仅用于在 Microsoft Visio 2013 中打开 .vsd 文件或以 .vsd 文件格式保存 .vsdx 文件时跟踪注释。</span><span class="sxs-lookup"><span data-stu-id="19fd6-105">This cell is used for tracking comments only when opening a .vsd file in Microsoft Visio 2013 or when saving a .vsdx file in the .vsd file format.</span></span> <span data-ttu-id="19fd6-106">它不用于跟踪 2013 年 10 月 Visio中的注释。</span><span class="sxs-lookup"><span data-stu-id="19fd6-106">It is not used for tracking comments in .vsdx documents in Visio 2013.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="19fd6-107">备注</span><span class="sxs-lookup"><span data-stu-id="19fd6-107">Remarks</span></span>

<span data-ttu-id="19fd6-p102">此值是输入注释时在语言栏上激活的语言的区域设置 ID (LCID)。有关 Microsoft Office 应用程序所支持的语言的列表，请参阅“[DocLangID](doclangid-cell-document-properties-section.md) 单元格（‘Document Properties’内容）”这一主题。</span><span class="sxs-lookup"><span data-stu-id="19fd6-p102">This value is the locale ID (LCID) of the language that is active on the language bar when the comment was entered. For a list of languages supported by Microsoft Office applications, see the [DocLangID](doclangid-cell-document-properties-section.md) Cell (Document Properties Section) topic.</span></span> 
  
<span data-ttu-id="19fd6-110">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 LangID 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="19fd6-110">To get a reference to the LangID cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="19fd6-111">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="19fd6-111">Cell name:</span></span>  <br/> | <span data-ttu-id="19fd6-112">Annotation.LangID[  *i*  ] 其中  *i*  = <1> 2， 3...</span><span class="sxs-lookup"><span data-stu-id="19fd6-112">Annotation.LangID[  *i*  ]            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="19fd6-113">若要从某个程序按索引获取对 LangID 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="19fd6-113">To get a reference to the LangID cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="19fd6-114">内容索引：</span><span class="sxs-lookup"><span data-stu-id="19fd6-114">Section index:</span></span>  <br/> |<span data-ttu-id="19fd6-115">**visSectionAnnotation**</span><span class="sxs-lookup"><span data-stu-id="19fd6-115">**visSectionAnnotation**</span></span> <br/> |
| <span data-ttu-id="19fd6-116">行索引：</span><span class="sxs-lookup"><span data-stu-id="19fd6-116">Row index:</span></span>  <br/> |<span data-ttu-id="19fd6-117">**visRowAnnotation**  +  *i* 其中 *i* = 0、1、2...</span><span class="sxs-lookup"><span data-stu-id="19fd6-117">**visRowAnnotation** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="19fd6-118">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="19fd6-118">Cell index:</span></span>  <br/> |<span data-ttu-id="19fd6-119">**visAnnotationLangID**</span><span class="sxs-lookup"><span data-stu-id="19fd6-119">**visAnnotationLangID**</span></span> <br/> |
   

