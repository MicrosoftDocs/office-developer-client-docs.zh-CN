---
title: DoubleStrikethrough 单元格（“Character”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033762
localization_priority: Normal
ms.assetid: c48a77e1-ea3c-7a6d-8c05-f9e0cb434cda
description: 确定文本格式是否设置为带双删除线。
ms.openlocfilehash: dcd7c7769da8298c1f6ab474d2b63fc982f479b1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780147"
---
# <a name="doublestrikethrough-cell-character-section"></a><span data-ttu-id="108eb-103">DoubleStrikethrough 单元格（“Character”内容）</span><span class="sxs-lookup"><span data-stu-id="108eb-103">DoubleStrikethrough Cell (Character Section)</span></span>

<span data-ttu-id="108eb-104">确定文本格式是否设置为带双删除线。</span><span class="sxs-lookup"><span data-stu-id="108eb-104">Determines whether text is formatted as double strikethrough.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="108eb-105">注释</span><span class="sxs-lookup"><span data-stu-id="108eb-105">Remarks</span></span>

<span data-ttu-id="108eb-106">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 DoubleStrikethrough 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="108eb-106">To get a reference to the DoubleStrikethrough cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="108eb-107">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="108eb-107">Cell name:</span></span>  <br/> | <span data-ttu-id="108eb-108">Char.DoubleStrikethrough [ *i* ] 其中*i* = < 1 >，2，3...</span><span class="sxs-lookup"><span data-stu-id="108eb-108">Char.DoubleStrikethrough[  *i*  ]            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="108eb-109">若要从某个程序按索引获取对 DoubleStrikethrough 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="108eb-109">To get a reference to the DoubleStrikethrough cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="108eb-110">内容索引：</span><span class="sxs-lookup"><span data-stu-id="108eb-110">Section index:</span></span>  <br/> |<span data-ttu-id="108eb-111">**visSectionCharacter**</span><span class="sxs-lookup"><span data-stu-id="108eb-111">**visSectionCharacter**</span></span> <br/> |
| <span data-ttu-id="108eb-112">行索引：</span><span class="sxs-lookup"><span data-stu-id="108eb-112">Row index:</span></span>  <br/> |<span data-ttu-id="108eb-113">**visRowCharacter** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="108eb-113">**visRowCharacter** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="108eb-114">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="108eb-114">Cell index:</span></span>  <br/> |<span data-ttu-id="108eb-115">**visCharacterDoubleStrikethrough**</span><span class="sxs-lookup"><span data-stu-id="108eb-115">**visCharacterDoubleStrikethrough**</span></span> <br/> |
   

