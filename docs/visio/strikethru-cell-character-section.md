---
title: Strikethru 单元格（“Character”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm975
localization_priority: Normal
ms.assetid: b03b4415-0b1a-eb03-2b5e-373b39a0f07a
description: 确定文本格式是否设置为带删除线。
ms.openlocfilehash: 2b25d1d9b00d062214c02c3fc7b14569b43a5110
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781454"
---
# <a name="strikethru-cell-character-section"></a><span data-ttu-id="5bde8-103">Strikethru 单元格（“Character”内容）</span><span class="sxs-lookup"><span data-stu-id="5bde8-103">Strikethru Cell (Character Section)</span></span>

<span data-ttu-id="5bde8-104">确定文本格式是否设置为带删除线。</span><span class="sxs-lookup"><span data-stu-id="5bde8-104">Determines whether the text is formatted as strikethrough.</span></span>
  
|<span data-ttu-id="5bde8-105">**值**</span><span class="sxs-lookup"><span data-stu-id="5bde8-105">**Value**</span></span>|<span data-ttu-id="5bde8-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="5bde8-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5bde8-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="5bde8-107">TRUE</span></span>  <br/> |<span data-ttu-id="5bde8-108">将文本格式设为带删除线。</span><span class="sxs-lookup"><span data-stu-id="5bde8-108">Text is formatted as strikethrough.</span></span>  <br/> |
|<span data-ttu-id="5bde8-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="5bde8-109">FALSE</span></span>  <br/> |<span data-ttu-id="5bde8-110">将文本格式设为不带删除线。</span><span class="sxs-lookup"><span data-stu-id="5bde8-110">Text is not formatted as strikethrough.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5bde8-111">注解</span><span class="sxs-lookup"><span data-stu-id="5bde8-111">Remarks</span></span>

<span data-ttu-id="5bde8-112">您还可以使用**文本**对话框来设置此单元格的值 （在**主页**选项卡上，单击**字体**箭头）。</span><span class="sxs-lookup"><span data-stu-id="5bde8-112">You can also set the value of this cell by using the **Text** dialog box (on the **Home** tab, click the **Font** arrow).</span></span> 
  
<span data-ttu-id="5bde8-113">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 Strikethru 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="5bde8-113">To get a reference to the Strikethru cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="5bde8-114">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="5bde8-114">Cell name:</span></span>  <br/> |<span data-ttu-id="5bde8-115">Char.Strikethru [ *i* ] 其中*i* = < 1 >，2，3...</span><span class="sxs-lookup"><span data-stu-id="5bde8-115">Char.Strikethru[ *i*  ] where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="5bde8-116">若要从某个程序按索引获取对 Strikethru 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="5bde8-116">To get a reference to the Strikethru cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="5bde8-117">内容索引：</span><span class="sxs-lookup"><span data-stu-id="5bde8-117">Section index:</span></span>  <br/> |<span data-ttu-id="5bde8-118">**visSectionCharacter**</span><span class="sxs-lookup"><span data-stu-id="5bde8-118">**visSectionCharacter**</span></span> <br/> |
|<span data-ttu-id="5bde8-119">行索引：</span><span class="sxs-lookup"><span data-stu-id="5bde8-119">Row index:</span></span>  <br/> |<span data-ttu-id="5bde8-120">**visRowCharacter** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="5bde8-120">**visRowCharacter** +  *i*  where  *i*  = 0, 1, 2...</span></span>  <br/> |
|<span data-ttu-id="5bde8-121">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="5bde8-121">Cell index:</span></span>  <br/> |<span data-ttu-id="5bde8-122">**visCharacterStrikethru**</span><span class="sxs-lookup"><span data-stu-id="5bde8-122">**visCharacterStrikethru**</span></span> <br/> |
   

