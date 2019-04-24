---
title: LangID 单元格（“Miscellaneous”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60051
localization_priority: Normal
ms.assetid: 815e0df8-5ebf-ef1b-d620-bce8abb69f1a
description: 指示创建单元格公式所使用的语言。
ms.openlocfilehash: e1e5b92f01e97bc63003a4b195c159a50f61e77b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346499"
---
# <a name="langid-cell-miscellaneous-section"></a><span data-ttu-id="d3440-103">LangID 单元格（“Miscellaneous”内容）</span><span class="sxs-lookup"><span data-stu-id="d3440-103">LangID Cell (Miscellaneous Section)</span></span>

<span data-ttu-id="d3440-104">指示创建单元格公式所使用的语言。</span><span class="sxs-lookup"><span data-stu-id="d3440-104">Indicates the language in which cell formulas were created.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="d3440-105">注解</span><span class="sxs-lookup"><span data-stu-id="d3440-105">Remarks</span></span>

<span data-ttu-id="d3440-106">有关 Microsoft Office 应用程序所支持的语言的列表，请参阅“[DocLangID](doclangid-cell-document-properties-section.md) 单元格（‘Document Properties’内容）”这一主题。</span><span class="sxs-lookup"><span data-stu-id="d3440-106">For a list of languages supported by Microsoft Office applications, see the [DocLangID](doclangid-cell-document-properties-section.md) Cell (Document Properties Section) topic.</span></span> 
  
<span data-ttu-id="d3440-107">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 LangID 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="d3440-107">To get a reference to the LangID cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="d3440-108">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="d3440-108">Cell name:</span></span>  <br/> | <span data-ttu-id="d3440-109">LangID</span><span class="sxs-lookup"><span data-stu-id="d3440-109">LangID</span></span>  <br/> |
   
<span data-ttu-id="d3440-110">若要从某个程序按索引获取对 LangID 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="d3440-110">To get a reference to the LangID cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="d3440-111">内容索引：</span><span class="sxs-lookup"><span data-stu-id="d3440-111">Section index:</span></span>  <br/> |<span data-ttu-id="d3440-112">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="d3440-112">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="d3440-113">行索引：</span><span class="sxs-lookup"><span data-stu-id="d3440-113">Row index:</span></span>  <br/> |<span data-ttu-id="d3440-114">**visRowMisc**</span><span class="sxs-lookup"><span data-stu-id="d3440-114">**visRowMisc**</span></span> <br/> |
| <span data-ttu-id="d3440-115">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="d3440-115">Cell index:</span></span>  <br/> |<span data-ttu-id="d3440-116">**visObjLangID**</span><span class="sxs-lookup"><span data-stu-id="d3440-116">**visObjLangID**</span></span> <br/> |
   

