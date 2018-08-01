---
title: LangID 单元格（“Character”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033769
localization_priority: Normal
ms.assetid: c68289b8-ef45-9e1e-12ae-6613587e4990
description: 指示输入文本所使用的语言。
ms.openlocfilehash: e503abb2365635fa25a4dbec54b7fe3da4043fa8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780520"
---
# <a name="langid-cell-character-section"></a><span data-ttu-id="5a7b2-103">LangID 单元格（“Character”部分）</span><span class="sxs-lookup"><span data-stu-id="5a7b2-103">LangID Cell (Character Section)</span></span>

<span data-ttu-id="5a7b2-104">指示输入文本所使用的语言。</span><span class="sxs-lookup"><span data-stu-id="5a7b2-104">Indicates the language in which the text was entered.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="5a7b2-105">注解</span><span class="sxs-lookup"><span data-stu-id="5a7b2-105">Remarks</span></span>

<span data-ttu-id="5a7b2-106">有关 Microsoft Office 应用程序所支持的语言的列表，请参阅“[DocLangID](doclangid-cell-document-properties-section.md) 单元格（‘Document Properties’内容）”这一主题。</span><span class="sxs-lookup"><span data-stu-id="5a7b2-106">For a list of languages supported by Microsoft Office applications, see the [DocLangID](doclangid-cell-document-properties-section.md) Cell (Document Properties Section) topic.</span></span> 
  
<span data-ttu-id="5a7b2-107">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 LangID 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="5a7b2-107">To get a reference to the LangID cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="5a7b2-108">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="5a7b2-108">Cell name:</span></span>  <br/> | <span data-ttu-id="5a7b2-109">Char.LangID [ *i* ] 其中*i* = < 1 >，2，3...</span><span class="sxs-lookup"><span data-stu-id="5a7b2-109">Char.LangID[  *i*  ]            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="5a7b2-110">若要从某个程序按索引获取对 LangID 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="5a7b2-110">To get a reference to the LangID cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="5a7b2-111">内容索引：</span><span class="sxs-lookup"><span data-stu-id="5a7b2-111">Section index:</span></span>  <br/> |<span data-ttu-id="5a7b2-112">**visSectionCharacter**</span><span class="sxs-lookup"><span data-stu-id="5a7b2-112">**visSectionCharacter**</span></span> <br/> |
| <span data-ttu-id="5a7b2-113">行索引：</span><span class="sxs-lookup"><span data-stu-id="5a7b2-113">Row index:</span></span>  <br/> |<span data-ttu-id="5a7b2-114">**visRowCharacter** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="5a7b2-114">**visRowCharacter** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="5a7b2-115">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="5a7b2-115">Cell index:</span></span>  <br/> |<span data-ttu-id="5a7b2-116">**visCharacterLangID**</span><span class="sxs-lookup"><span data-stu-id="5a7b2-116">**visCharacterLangID**</span></span> <br/> |
   

