---
title: ImgHeight 单元格（“Foreign Image Info”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm445
localization_priority: Normal
ms.assetid: decb86a4-b711-35e1-b9dc-744a84ee177c
description: 确定对象的图像在其边框内的高度。 默认公式为：
ms.openlocfilehash: 956bc478604fd19d8dfdbb7079e092e9e8a16e7b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411195"
---
# <a name="imgheight-cell-foreign-image-info-section"></a><span data-ttu-id="ddad3-104">ImgHeight 单元格（“Foreign Image Info”内容）</span><span class="sxs-lookup"><span data-stu-id="ddad3-104">ImgHeight Cell (Foreign Image Info Section)</span></span>

<span data-ttu-id="ddad3-105">确定对象的图像在其边框内的高度。</span><span class="sxs-lookup"><span data-stu-id="ddad3-105">Determines the height of the object's image within its border.</span></span> <span data-ttu-id="ddad3-106">默认公式为：</span><span class="sxs-lookup"><span data-stu-id="ddad3-106">The default formula is:</span></span>
  
<span data-ttu-id="ddad3-107">= Height \* 1</span><span class="sxs-lookup"><span data-stu-id="ddad3-107">= Height \* 1</span></span>
  
## <a name="remarks"></a><span data-ttu-id="ddad3-108">说明</span><span class="sxs-lookup"><span data-stu-id="ddad3-108">Remarks</span></span>

<span data-ttu-id="ddad3-109">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 ImgHeight 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="ddad3-109">To get a reference to the ImgHeight cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="ddad3-110">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="ddad3-110">Cell name:</span></span>  <br/> | <span data-ttu-id="ddad3-111">ImgHeight</span><span class="sxs-lookup"><span data-stu-id="ddad3-111">ImgHeight</span></span>  <br/> |
   
<span data-ttu-id="ddad3-112">要从某个程序按索引获取对 ImgHeight 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="ddad3-112">To get a reference to the ImgHeight cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="ddad3-113">内容索引：</span><span class="sxs-lookup"><span data-stu-id="ddad3-113">Section index:</span></span>  <br/> |<span data-ttu-id="ddad3-114">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="ddad3-114">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="ddad3-115">行索引：</span><span class="sxs-lookup"><span data-stu-id="ddad3-115">Row index:</span></span>  <br/> |<span data-ttu-id="ddad3-116">**visRowForeign**</span><span class="sxs-lookup"><span data-stu-id="ddad3-116">**visRowForeign**</span></span> <br/> |
| <span data-ttu-id="ddad3-117">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="ddad3-117">Cell index:</span></span>  <br/> |<span data-ttu-id="ddad3-118">**visFrgnImgHeight**</span><span class="sxs-lookup"><span data-stu-id="ddad3-118">**visFrgnImgHeight**</span></span> <br/> |
   

