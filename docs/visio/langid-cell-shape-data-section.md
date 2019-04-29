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
ms.openlocfilehash: c5a0cca5f71bc5520337ad2bdcf354a2b4affe92
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420323"
---
# <a name="langid-cell-shape-data-section"></a><span data-ttu-id="2df11-103">LangID 单元格（“Shape Data”内容）</span><span class="sxs-lookup"><span data-stu-id="2df11-103">LangID Cell (Shape Data Section)</span></span>

<span data-ttu-id="2df11-104">指示输入形状数据值所使用的语言。</span><span class="sxs-lookup"><span data-stu-id="2df11-104">Indicates the language in which the shape data value was entered.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="2df11-105">说明</span><span class="sxs-lookup"><span data-stu-id="2df11-105">Remarks</span></span>

<span data-ttu-id="2df11-106">有关 Microsoft Office 系统应用程序所支持的语言的列表，请参阅 [DocLangID](doclangid-cell-document-properties-section.md) 单元格（“Document Properties”内容）。</span><span class="sxs-lookup"><span data-stu-id="2df11-106">For a list of languages supported by Microsoft Office System applications, see the [DocLangID](doclangid-cell-document-properties-section.md) Cell (Document Properties Section).</span></span> 
  
<span data-ttu-id="2df11-107">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 LangID 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="2df11-107">To get a reference to the LangID cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="2df11-108">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="2df11-108">Cell name:</span></span>  <br/> | <span data-ttu-id="2df11-109">片. *名称*。LangID 其中的一个。 *名称*是行名称</span><span class="sxs-lookup"><span data-stu-id="2df11-109">Prop.  *name*  .LangID            where Prop.  *name*  is the row name</span></span>  <br/> |
   
<span data-ttu-id="2df11-110">若要从某个程序按索引获取对 LangID 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="2df11-110">To get a reference to the LangID cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="2df11-111">内容索引：</span><span class="sxs-lookup"><span data-stu-id="2df11-111">Section index:</span></span>  <br/> |<span data-ttu-id="2df11-112">**visSectionProp**</span><span class="sxs-lookup"><span data-stu-id="2df11-112">**visSectionProp**</span></span> <br/> |
| <span data-ttu-id="2df11-113">行索引：</span><span class="sxs-lookup"><span data-stu-id="2df11-113">Row index:</span></span>  <br/> |<span data-ttu-id="2df11-114">**visRowProp** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="2df11-114">**visRowProp** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="2df11-115">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="2df11-115">Cell index:</span></span>  <br/> |<span data-ttu-id="2df11-116">**visCustPropsLangID**</span><span class="sxs-lookup"><span data-stu-id="2df11-116">**visCustPropsLangID**</span></span> <br/> |
   

