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
ms.openlocfilehash: f5222836b29a26cc26ca8093576d0962f0592fae
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779904"
---
# <a name="comment-cell-miscellaneous-section"></a><span data-ttu-id="aa7ff-103">Comment 单元格（“Miscellaneous”部分）</span><span class="sxs-lookup"><span data-stu-id="aa7ff-103">Comment Cell (Miscellaneous Section)</span></span>

<span data-ttu-id="aa7ff-104">包含形状的字符串格式的注释文本。</span><span class="sxs-lookup"><span data-stu-id="aa7ff-104">Contains the comment text in string format for a shape.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="aa7ff-105">注解</span><span class="sxs-lookup"><span data-stu-id="aa7ff-105">Remarks</span></span>

<span data-ttu-id="aa7ff-106">也可以通过单击 **“审阅”** 选项卡上的 **“新建批注”** 插入批注。</span><span class="sxs-lookup"><span data-stu-id="aa7ff-106">You can also insert a comment by clicking **New Comment** on the **Review** tab.</span></span> 
  
<span data-ttu-id="aa7ff-107">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Comment 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="aa7ff-107">To get a reference to the Comment cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="aa7ff-108">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="aa7ff-108">Cell name:</span></span>  <br/> |<span data-ttu-id="aa7ff-109">Comment</span><span class="sxs-lookup"><span data-stu-id="aa7ff-109">Comment</span></span>  <br/> |
   
<span data-ttu-id="aa7ff-110">要从某个程序按索引获取对 Comment 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="aa7ff-110">To get a reference to the Comment cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="aa7ff-111">内容索引：</span><span class="sxs-lookup"><span data-stu-id="aa7ff-111">Section index:</span></span>  <br/> |<span data-ttu-id="aa7ff-112">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="aa7ff-112">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="aa7ff-113">行索引：</span><span class="sxs-lookup"><span data-stu-id="aa7ff-113">Row index:</span></span>  <br/> |<span data-ttu-id="aa7ff-114">**visRowMisc**</span><span class="sxs-lookup"><span data-stu-id="aa7ff-114">**visRowMisc**</span></span> <br/> |
|<span data-ttu-id="aa7ff-115">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="aa7ff-115">Cell index:</span></span>  <br/> |<span data-ttu-id="aa7ff-116">**visComment**</span><span class="sxs-lookup"><span data-stu-id="aa7ff-116">**visComment**</span></span> <br/> |
   

