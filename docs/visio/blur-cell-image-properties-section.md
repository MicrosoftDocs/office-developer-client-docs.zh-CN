---
title: Blur 单元格（“Image Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm115
localization_priority: Normal
ms.assetid: 8b077cdb-6036-4f77-dc20-a476bb75b0f7
description: 虚化或柔化位图图像。默认值是 0%。
ms.openlocfilehash: 14a50f2015b2b24d7e41f5d11018a749d089fc37
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779785"
---
# <a name="blur-cell-image-properties-section"></a><span data-ttu-id="a2c07-104">Blur 单元格（“Image Properties”部分）</span><span class="sxs-lookup"><span data-stu-id="a2c07-104">Blur Cell (Image Properties Section)</span></span>

<span data-ttu-id="a2c07-p102">虚化或柔化位图图像。默认值是 0%。</span><span class="sxs-lookup"><span data-stu-id="a2c07-p102">Blurs or softens a bitmap image. The default value is 0%.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="a2c07-107">注释</span><span class="sxs-lookup"><span data-stu-id="a2c07-107">Remarks</span></span>

<span data-ttu-id="a2c07-108">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Blur 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="a2c07-108">To get a reference to the Blur cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="a2c07-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="a2c07-109">Cell name:</span></span>  <br/> | <span data-ttu-id="a2c07-110">Blur</span><span class="sxs-lookup"><span data-stu-id="a2c07-110">Blur</span></span>  <br/> |
   
<span data-ttu-id="a2c07-111">要从某个程序按索引获取对 Blur 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="a2c07-111">To get a reference to the Blur cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="a2c07-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="a2c07-112">Section index:</span></span>  <br/> |<span data-ttu-id="a2c07-113">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="a2c07-113">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="a2c07-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="a2c07-114">Row index:</span></span>  <br/> |<span data-ttu-id="a2c07-115">**visRowImage**</span><span class="sxs-lookup"><span data-stu-id="a2c07-115">**visRowImage**</span></span> <br/> |
| <span data-ttu-id="a2c07-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="a2c07-116">Cell index:</span></span>  <br/> |<span data-ttu-id="a2c07-117">**visImageBlur**</span><span class="sxs-lookup"><span data-stu-id="a2c07-117">**visImageBlur**</span></span> <br/> |
   

