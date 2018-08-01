---
title: LangID 单元格（“Shape Data”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033771
localization_priority: Normal
ms.assetid: 6bd2781a-d4e7-136f-8996-62ebc5f890ab
description: 指示输入形状数据值所使用的语言。
ms.openlocfilehash: 696c42483390509474eb82bd8cc0046beee345e8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780543"
---
# <a name="langid-cell-shape-data-section"></a><span data-ttu-id="a8626-103">LangID 单元格（“Shape Data”部分）</span><span class="sxs-lookup"><span data-stu-id="a8626-103">LangID Cell (Shape Data Section)</span></span>

<span data-ttu-id="a8626-104">指示输入形状数据值所使用的语言。</span><span class="sxs-lookup"><span data-stu-id="a8626-104">Indicates the language in which the shape data value was entered.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="a8626-105">注解</span><span class="sxs-lookup"><span data-stu-id="a8626-105">Remarks</span></span>

<span data-ttu-id="a8626-106">有关 Microsoft Office 系统应用程序所支持的语言的列表，请参阅 [DocLangID](doclangid-cell-document-properties-section.md) 单元格（“Document Properties”内容）。</span><span class="sxs-lookup"><span data-stu-id="a8626-106">For a list of languages supported by Microsoft Office System applications, see the [DocLangID](doclangid-cell-document-properties-section.md) Cell (Document Properties Section).</span></span> 
  
<span data-ttu-id="a8626-107">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 LangID 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="a8626-107">To get a reference to the LangID cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="a8626-108">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="a8626-108">Cell name:</span></span>  <br/> | <span data-ttu-id="a8626-109">属性。 *名称*。LangID 其中属性。 *name*是行名称</span><span class="sxs-lookup"><span data-stu-id="a8626-109">Prop.  *name*  .LangID            where Prop.  *name*  is the row name</span></span>  <br/> |
   
<span data-ttu-id="a8626-110">若要从某个程序按索引获取对 LangID 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="a8626-110">To get a reference to the LangID cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="a8626-111">内容索引：</span><span class="sxs-lookup"><span data-stu-id="a8626-111">Section index:</span></span>  <br/> |<span data-ttu-id="a8626-112">**visSectionProp**</span><span class="sxs-lookup"><span data-stu-id="a8626-112">**visSectionProp**</span></span> <br/> |
| <span data-ttu-id="a8626-113">行索引：</span><span class="sxs-lookup"><span data-stu-id="a8626-113">Row index:</span></span>  <br/> |<span data-ttu-id="a8626-114">**visRowProp** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="a8626-114">**visRowProp** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="a8626-115">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="a8626-115">Cell index:</span></span>  <br/> |<span data-ttu-id="a8626-116">**visCustPropsLangID**</span><span class="sxs-lookup"><span data-stu-id="a8626-116">**visCustPropsLangID**</span></span> <br/> |
   

