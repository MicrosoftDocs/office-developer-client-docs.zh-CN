---
title: Overline 单元格（“Character”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251728
localization_priority: Normal
ms.assetid: 102cce17-43ee-e313-3412-a72d6ee18fe6
description: 确定在文本之上是否存在线条。
ms.openlocfilehash: 3ceb0f5bcb6f66098938e49ea5f176921d0c9808
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780815"
---
# <a name="overline-cell-character-section"></a><span data-ttu-id="813d7-103">Overline 单元格（“Character”部分）</span><span class="sxs-lookup"><span data-stu-id="813d7-103">Overline Cell (Character Section)</span></span>

<span data-ttu-id="813d7-104">确定在文本之上是否存在线条。</span><span class="sxs-lookup"><span data-stu-id="813d7-104">Determines whether the text has a line above it.</span></span>
  
|<span data-ttu-id="813d7-105">**值**</span><span class="sxs-lookup"><span data-stu-id="813d7-105">**Value**</span></span>|<span data-ttu-id="813d7-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="813d7-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="813d7-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="813d7-107">TRUE</span></span>  <br/> |<span data-ttu-id="813d7-108">文本之上存在线条。</span><span class="sxs-lookup"><span data-stu-id="813d7-108">Text has a line above it.</span></span>  <br/> |
|<span data-ttu-id="813d7-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="813d7-109">FALSE</span></span>  <br/> |<span data-ttu-id="813d7-110">文本之上没有线条。</span><span class="sxs-lookup"><span data-stu-id="813d7-110">Text does not have a line above it.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="813d7-111">注解</span><span class="sxs-lookup"><span data-stu-id="813d7-111">Remarks</span></span>

<span data-ttu-id="813d7-112">还可以使用 **“文本”** 对话框（在 **“开始”** 选项卡上，单击 **“字体”** 箭头）设置此单元格的值。</span><span class="sxs-lookup"><span data-stu-id="813d7-112">You can also set the value of this cell by using the **Text** dialog box (on the **Home** tab, click the **Font** arrow).</span></span> 
  
<span data-ttu-id="813d7-113">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Overline 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="813d7-113">To get a reference to the Overline cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="813d7-114">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="813d7-114">Cell name:</span></span>  <br/> |<span data-ttu-id="813d7-115">Char.Overline [ *i* ] 其中*i* = < 1 > 2。</span><span class="sxs-lookup"><span data-stu-id="813d7-115">Char.Overline[ *i*  ] where  *i*  = <1>, 2.</span></span> <span data-ttu-id="813d7-116">3...</span><span class="sxs-lookup"><span data-stu-id="813d7-116">3...</span></span>  <br/> |
   
<span data-ttu-id="813d7-117">若要从某个程序按索引获取对 Overline 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="813d7-117">To get a reference to the Overline cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="813d7-118">内容索引：</span><span class="sxs-lookup"><span data-stu-id="813d7-118">Section index:</span></span>  <br/> |<span data-ttu-id="813d7-119">**visSectionCharacter**</span><span class="sxs-lookup"><span data-stu-id="813d7-119">**visSectionCharacter**</span></span> <br/> |
|<span data-ttu-id="813d7-120">行索引：</span><span class="sxs-lookup"><span data-stu-id="813d7-120">Row index:</span></span>  <br/> |<span data-ttu-id="813d7-121">**visRowCharacter** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="813d7-121">**visRowCharacter** +  *i*  where  *i*  = 0, 1, 2...</span></span>  <br/> |
|<span data-ttu-id="813d7-122">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="813d7-122">Cell index:</span></span>  <br/> |<span data-ttu-id="813d7-123">**visCharacterOverline**</span><span class="sxs-lookup"><span data-stu-id="813d7-123">**visCharacterOverline**</span></span> <br/> |
   

