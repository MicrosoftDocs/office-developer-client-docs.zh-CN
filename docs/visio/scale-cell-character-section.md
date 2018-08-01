---
title: Scale 单元格（“Character”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm870
localization_priority: Normal
ms.assetid: d6fe2574-b719-f38e-b1f1-592a812f1682
description: 控制字体宽度。该单元格的默认值是 100%。
ms.openlocfilehash: fedbc0aec23320d03ca358f34babda56eaab31e4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781217"
---
# <a name="scale-cell-character-section"></a><span data-ttu-id="4b638-104">Scale 单元格（“Character”部分）</span><span class="sxs-lookup"><span data-stu-id="4b638-104">Scale Cell (Character Section)</span></span>

<span data-ttu-id="4b638-p102">控制字体宽度。该单元格的默认值是 100%。</span><span class="sxs-lookup"><span data-stu-id="4b638-p102">Controls the font width. The default value for this cell is 100%.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="4b638-107">注解</span><span class="sxs-lookup"><span data-stu-id="4b638-107">Remarks</span></span>

<span data-ttu-id="4b638-p103">将百分比设置为介于 1% 和 99% 之间，可减少字体宽度。将百分比设置为介于 101% 和 600% 之间，可增加字体宽度。</span><span class="sxs-lookup"><span data-stu-id="4b638-p103">Set the percentage between 1% and 99% to decrease the font width. Set it between 101% and 600% to increase the font width.</span></span>
  
<span data-ttu-id="4b638-110">还可以使用 **“文本”** 对话框（在 **“开始”** 选项卡上，单击 **“字体”** 箭头）设置此单元格的值。</span><span class="sxs-lookup"><span data-stu-id="4b638-110">You can also set the value of this cell by using the **Text** dialog box (on the **Home** tab, click the **Font** arrow).</span></span> 
  
<span data-ttu-id="4b638-111">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Scale 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="4b638-111">To get a reference to the Scale cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="4b638-112">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="4b638-112">Cell name:</span></span>  <br/> |<span data-ttu-id="4b638-113">Char.FontScale [ *i* ] 其中*i* = < 1 >，2，3...</span><span class="sxs-lookup"><span data-stu-id="4b638-113">Char.FontScale[ *i*  ] where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="4b638-114">若要从某个程序按索引获取对 Scale 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="4b638-114">To get a reference to the Scale cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="4b638-115">内容索引：</span><span class="sxs-lookup"><span data-stu-id="4b638-115">Section index:</span></span>  <br/> |<span data-ttu-id="4b638-116">**visSectionCharacter**</span><span class="sxs-lookup"><span data-stu-id="4b638-116">**visSectionCharacter**</span></span> <br/> |
|<span data-ttu-id="4b638-117">行索引：</span><span class="sxs-lookup"><span data-stu-id="4b638-117">Row index:</span></span>  <br/> |<span data-ttu-id="4b638-118">**visRowCharacter** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="4b638-118">**visRowCharacter** +  *i*  where  *i*  = 0, 1, 2...</span></span>  <br/> |
|<span data-ttu-id="4b638-119">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="4b638-119">Cell index:</span></span>  <br/> |<span data-ttu-id="4b638-120">**visCharacterFontScale**</span><span class="sxs-lookup"><span data-stu-id="4b638-120">**visCharacterFontScale**</span></span> <br/> |
   

