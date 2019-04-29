---
title: DoubleULine 单元格（“Character”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm260
localization_priority: Normal
ms.assetid: c18955c8-d653-c29d-d3da-9d3cd0241e17
description: 确定文本范围下是否带有双下划线。
ms.openlocfilehash: 2708e7f55e1fd04d5fb902b3d382035790cbbcc2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438839"
---
# <a name="doubleuline-cell-character-section"></a><span data-ttu-id="fc2c7-103">DoubleULine 单元格（“Character”内容）</span><span class="sxs-lookup"><span data-stu-id="fc2c7-103">DoubleULine Cell (Character Section)</span></span>

<span data-ttu-id="fc2c7-104">确定文本范围下是否带有双下划线。</span><span class="sxs-lookup"><span data-stu-id="fc2c7-104">Determines whether the range of text has a double underline below it.</span></span>
  
|<span data-ttu-id="fc2c7-105">**值**</span><span class="sxs-lookup"><span data-stu-id="fc2c7-105">**Value**</span></span>|<span data-ttu-id="fc2c7-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="fc2c7-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fc2c7-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="fc2c7-107">TRUE</span></span>  <br/> |<span data-ttu-id="fc2c7-108">文本下带有双下划线。</span><span class="sxs-lookup"><span data-stu-id="fc2c7-108">Text has a double underline below it.</span></span>  <br/> |
|<span data-ttu-id="fc2c7-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="fc2c7-109">FALSE</span></span>  <br/> |<span data-ttu-id="fc2c7-110">文本下不带双下划线。</span><span class="sxs-lookup"><span data-stu-id="fc2c7-110">Text does not have a double underline below it.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="fc2c7-111">说明</span><span class="sxs-lookup"><span data-stu-id="fc2c7-111">Remarks</span></span>

<span data-ttu-id="fc2c7-p101">如果“Characters”内容包含多行，则 DoubleULine 单元格包含应用于某形状文本的一个子范围的格式设置信息。否则，它就包含该形状的所有文本的格式设置信息。</span><span class="sxs-lookup"><span data-stu-id="fc2c7-p101">The DoubleULine cell contains formatting information applied to a sub-range of a shape's text if the Characters section contains multiple rows. Otherwise, it contains formatting information for all of the shape's text.</span></span>
  
<span data-ttu-id="fc2c7-114">还可以使用 **“文本”** 对话框（在 **“开始”** 选项卡上单击 **“字体”**）设置此单元格的值。</span><span class="sxs-lookup"><span data-stu-id="fc2c7-114">You can also set the value of this cell by using the **Text** dialog box (click the **Font** arrow on the **Home** tab).</span></span> 
  
<span data-ttu-id="fc2c7-115">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 DoubleULine 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="fc2c7-115">To get a reference to the DoubleULine cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="fc2c7-116">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="fc2c7-116">Cell name:</span></span>  <br/> |<span data-ttu-id="fc2c7-117">DblUnderline [ *i* ] 其中*i* = <1>, 2, 3 .。。</span><span class="sxs-lookup"><span data-stu-id="fc2c7-117">Char.DblUnderline[ *i*  ]           where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="fc2c7-118">若要从某个程序按索引获取对 DoubleULine 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="fc2c7-118">To get a reference to the DoubleULine cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="fc2c7-119">内容索引：</span><span class="sxs-lookup"><span data-stu-id="fc2c7-119">Section index:</span></span>  <br/> |<span data-ttu-id="fc2c7-120">**visSectionCharacter**</span><span class="sxs-lookup"><span data-stu-id="fc2c7-120">**visSectionCharacter**</span></span> <br/> |
|<span data-ttu-id="fc2c7-121">行索引：</span><span class="sxs-lookup"><span data-stu-id="fc2c7-121">Row index:</span></span>  <br/> |<span data-ttu-id="fc2c7-122">**visRowCharacter** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="fc2c7-122">**visRowCharacter** +  *i*           where  *i*  = 0, 1, 2...</span></span>  <br/> |
|<span data-ttu-id="fc2c7-123">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="fc2c7-123">Cell index:</span></span>  <br/> |<span data-ttu-id="fc2c7-124">**visCharacterDblUnderline**</span><span class="sxs-lookup"><span data-stu-id="fc2c7-124">**visCharacterDblUnderline**</span></span> <br/> |
   

