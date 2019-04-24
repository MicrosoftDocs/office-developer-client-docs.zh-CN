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
ms.openlocfilehash: d8ef5bdb6e086be9657f51c66c10d578414e1deb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360590"
---
# <a name="doublestrikethrough-cell-character-section"></a><span data-ttu-id="2aa69-103">DoubleStrikethrough 单元格（“Character”内容）</span><span class="sxs-lookup"><span data-stu-id="2aa69-103">DoubleStrikethrough Cell (Character Section)</span></span>

<span data-ttu-id="2aa69-104">确定文本格式是否设置为带双删除线。</span><span class="sxs-lookup"><span data-stu-id="2aa69-104">Determines whether text is formatted as double strikethrough.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="2aa69-105">注解</span><span class="sxs-lookup"><span data-stu-id="2aa69-105">Remarks</span></span>

<span data-ttu-id="2aa69-106">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 DoubleStrikethrough 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="2aa69-106">To get a reference to the DoubleStrikethrough cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="2aa69-107">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="2aa69-107">Cell name:</span></span>  <br/> | <span data-ttu-id="2aa69-108">DoubleStrikethrough [ *i* ] 其中*i* = <1>, 2, 3 .。。</span><span class="sxs-lookup"><span data-stu-id="2aa69-108">Char.DoubleStrikethrough[  *i*  ]            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="2aa69-109">要从某个程序按索引获取对 DoubleStrikethrough 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="2aa69-109">To get a reference to the DoubleStrikethrough cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="2aa69-110">内容索引：</span><span class="sxs-lookup"><span data-stu-id="2aa69-110">Section index:</span></span>  <br/> |<span data-ttu-id="2aa69-111">**visSectionCharacter**</span><span class="sxs-lookup"><span data-stu-id="2aa69-111">**visSectionCharacter**</span></span> <br/> |
| <span data-ttu-id="2aa69-112">行索引：</span><span class="sxs-lookup"><span data-stu-id="2aa69-112">Row index:</span></span>  <br/> |<span data-ttu-id="2aa69-113">**visRowCharacter** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="2aa69-113">**visRowCharacter** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="2aa69-114">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="2aa69-114">Cell index:</span></span>  <br/> |<span data-ttu-id="2aa69-115">**visCharacterDoubleStrikethrough**</span><span class="sxs-lookup"><span data-stu-id="2aa69-115">**visCharacterDoubleStrikethrough**</span></span> <br/> |
   

