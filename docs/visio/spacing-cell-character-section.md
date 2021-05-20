---
title: Spacing 单元格（“Character”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm955
localization_priority: Normal
ms.assetid: 46feb136-01ac-1303-66ab-d772c0ec41a0
description: 控制两个或多个字符之间的空间量。空间量可以二十分之一磅为增量增加或减少。
ms.openlocfilehash: 927b6203b81af453411cdd13b6f8c8342507a61b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430061"
---
# <a name="spacing-cell-character-section"></a><span data-ttu-id="f2ba6-104">Spacing 单元格（“Character”内容）</span><span class="sxs-lookup"><span data-stu-id="f2ba6-104">Spacing Cell (Character Section)</span></span>

<span data-ttu-id="f2ba6-p102">控制两个或多个字符之间的空间量。空间量可以二十分之一磅为增量增加或减少。</span><span class="sxs-lookup"><span data-stu-id="f2ba6-p102">Controls the amount of space between two or more characters. Space can be added or subtracted in 1/20th point increments.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="f2ba6-107">备注</span><span class="sxs-lookup"><span data-stu-id="f2ba6-107">Remarks</span></span>

<span data-ttu-id="f2ba6-108">还可以使用 **“文本”** 对话框（在 **“开始”** 选项卡上，单击 **“字体”** 箭头）设置此单元格的值。</span><span class="sxs-lookup"><span data-stu-id="f2ba6-108">You can also set the value of this cell by using the **Text** dialog box (on the **Home** tab, click the **Font** arrow).</span></span> 
  
<span data-ttu-id="f2ba6-109">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Spacing 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="f2ba6-109">To get a reference to the Spacing cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f2ba6-110">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="f2ba6-110">Cell name:</span></span>  <br/> |<span data-ttu-id="f2ba6-111">Char.Letterspace[ *i*  ] 其中  *i*  = <1> 2， 3...</span><span class="sxs-lookup"><span data-stu-id="f2ba6-111">Char.Letterspace[ *i*  ] where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="f2ba6-112">若要从某个程序按索引获取对 Spacing 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="f2ba6-112">To get a reference to the Spacing cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f2ba6-113">内容索引：</span><span class="sxs-lookup"><span data-stu-id="f2ba6-113">Section index:</span></span>  <br/> |<span data-ttu-id="f2ba6-114">**visSectionCharacter**</span><span class="sxs-lookup"><span data-stu-id="f2ba6-114">**visSectionCharacter**</span></span> <br/> |
|<span data-ttu-id="f2ba6-115">行索引：</span><span class="sxs-lookup"><span data-stu-id="f2ba6-115">Row index:</span></span>  <br/> |<span data-ttu-id="f2ba6-116">**visRowCharacter**  +  *i* 其中 *i* = 0、1、2...</span><span class="sxs-lookup"><span data-stu-id="f2ba6-116">**visRowCharacter** +  *i*  where  *i*  = 0, 1, 2...</span></span>  <br/> |
|<span data-ttu-id="f2ba6-117">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="f2ba6-117">Cell index:</span></span>  <br/> |<span data-ttu-id="f2ba6-118">**visCharacterLetterspace**</span><span class="sxs-lookup"><span data-stu-id="f2ba6-118">**visCharacterLetterspace**</span></span> <br/> |
   

