---
title: Comment 单元格（“Miscellaneous”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm170
localization_priority: Normal
ms.assetid: 6f52ed60-d58b-86e6-f7e2-2ef19d4afa75
description: 包含形状的字符串格式的注释文本。
ms.openlocfilehash: e6f21875928bce31dc2004d88f2d281e31265d65
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357111"
---
# <a name="comment-cell-miscellaneous-section"></a><span data-ttu-id="4ea04-103">Comment 单元格（“Miscellaneous”内容）</span><span class="sxs-lookup"><span data-stu-id="4ea04-103">Comment Cell (Miscellaneous Section)</span></span>

<span data-ttu-id="4ea04-104">包含形状的字符串格式的注释文本。</span><span class="sxs-lookup"><span data-stu-id="4ea04-104">Contains the comment text in string format for a shape.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="4ea04-105">注解</span><span class="sxs-lookup"><span data-stu-id="4ea04-105">Remarks</span></span>

<span data-ttu-id="4ea04-106">也可以通过单击 **“审阅”** 选项卡上的 **“新建批注”** 插入批注。</span><span class="sxs-lookup"><span data-stu-id="4ea04-106">You can also insert a comment by clicking **New Comment** on the **Review** tab.</span></span> 
  
<span data-ttu-id="4ea04-107">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Comment 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="4ea04-107">To get a reference to the Comment cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="4ea04-108">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="4ea04-108">Cell name:</span></span>  <br/> |<span data-ttu-id="4ea04-109">Comment</span><span class="sxs-lookup"><span data-stu-id="4ea04-109">Comment</span></span>  <br/> |
   
<span data-ttu-id="4ea04-110">要从某个程序按索引获取对 Comment 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="4ea04-110">To get a reference to the Comment cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="4ea04-111">内容索引：</span><span class="sxs-lookup"><span data-stu-id="4ea04-111">Section index:</span></span>  <br/> |<span data-ttu-id="4ea04-112">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="4ea04-112">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="4ea04-113">行索引：</span><span class="sxs-lookup"><span data-stu-id="4ea04-113">Row index:</span></span>  <br/> |<span data-ttu-id="4ea04-114">**visRowMisc**</span><span class="sxs-lookup"><span data-stu-id="4ea04-114">**visRowMisc**</span></span> <br/> |
|<span data-ttu-id="4ea04-115">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="4ea04-115">Cell index:</span></span>  <br/> |<span data-ttu-id="4ea04-116">**visComment**</span><span class="sxs-lookup"><span data-stu-id="4ea04-116">**visComment**</span></span> <br/> |
   

