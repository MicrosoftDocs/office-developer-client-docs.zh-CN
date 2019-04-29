---
title: Font 单元格（“Character”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm390
localization_priority: Normal
ms.assetid: 935760a9-307e-90bc-c301-d04283d97427
description: 代表用于设置文本格式的字体编号。根据您的系统上安装的字体，字体编号会有所不同。编号 0 代表默认的字体，通常为 Arial。
ms.openlocfilehash: d9182932b8fa63c30473b93e420aa9efe30bf5eb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438664"
---
# <a name="font-cell-character-section"></a><span data-ttu-id="e1cbc-105">Font 单元格（“Character”内容）</span><span class="sxs-lookup"><span data-stu-id="e1cbc-105">Font Cell (Character Section)</span></span>

<span data-ttu-id="e1cbc-p102">代表用于设置文本格式的字体编号。根据您的系统上安装的字体，字体编号会有所不同。编号 0 代表默认的字体，通常为 Arial。</span><span class="sxs-lookup"><span data-stu-id="e1cbc-p102">Represents the number of the font used to format the text. Font numbers vary according to the fonts installed on your system. The number 0 represents the default font, which is typically Arial.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="e1cbc-109">说明</span><span class="sxs-lookup"><span data-stu-id="e1cbc-109">Remarks</span></span>

<span data-ttu-id="e1cbc-110">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Font 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="e1cbc-110">To get a reference to the Font cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="e1cbc-111">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="e1cbc-111">Cell name:</span></span>  <br/> | <span data-ttu-id="e1cbc-112">Char. Font [ *i* ] 其中*i* = <1>, 2, 3 .。。</span><span class="sxs-lookup"><span data-stu-id="e1cbc-112">Char.Font[  *i*  ]            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="e1cbc-113">要从某个程序按索引获取对 Font 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="e1cbc-113">To get a reference to the Font cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="e1cbc-114">内容索引：</span><span class="sxs-lookup"><span data-stu-id="e1cbc-114">Section index:</span></span>  <br/> |<span data-ttu-id="e1cbc-115">**visSectionCharacter**</span><span class="sxs-lookup"><span data-stu-id="e1cbc-115">**visSectionCharacter**</span></span> <br/> |
| <span data-ttu-id="e1cbc-116">行索引：</span><span class="sxs-lookup"><span data-stu-id="e1cbc-116">Row index:</span></span>  <br/> |<span data-ttu-id="e1cbc-117">**visRowCharacter** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="e1cbc-117">**visRowCharacter** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="e1cbc-118">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="e1cbc-118">Cell index:</span></span>  <br/> |<span data-ttu-id="e1cbc-119">**visCharacterFont**</span><span class="sxs-lookup"><span data-stu-id="e1cbc-119">**visCharacterFont**</span></span> <br/> |
   

