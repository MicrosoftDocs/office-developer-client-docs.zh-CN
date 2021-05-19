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
ms.openlocfilehash: 599810d126c853e37552045d0ef83cb580606ae2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427904"
---
# <a name="blur-cell-image-properties-section"></a><span data-ttu-id="97e22-104">Blur 单元格（“Image Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="97e22-104">Blur Cell (Image Properties Section)</span></span>

<span data-ttu-id="97e22-p102">虚化或柔化位图图像。默认值是 0%。</span><span class="sxs-lookup"><span data-stu-id="97e22-p102">Blurs or softens a bitmap image. The default value is 0%.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="97e22-107">备注</span><span class="sxs-lookup"><span data-stu-id="97e22-107">Remarks</span></span>

<span data-ttu-id="97e22-108">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Blur 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="97e22-108">To get a reference to the Blur cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="97e22-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="97e22-109">Cell name:</span></span>  <br/> | <span data-ttu-id="97e22-110">Blur</span><span class="sxs-lookup"><span data-stu-id="97e22-110">Blur</span></span>  <br/> |
   
<span data-ttu-id="97e22-111">要从某个程序按索引获取对 Blur 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="97e22-111">To get a reference to the Blur cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="97e22-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="97e22-112">Section index:</span></span>  <br/> |<span data-ttu-id="97e22-113">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="97e22-113">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="97e22-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="97e22-114">Row index:</span></span>  <br/> |<span data-ttu-id="97e22-115">**visRowImage**</span><span class="sxs-lookup"><span data-stu-id="97e22-115">**visRowImage**</span></span> <br/> |
| <span data-ttu-id="97e22-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="97e22-116">Cell index:</span></span>  <br/> |<span data-ttu-id="97e22-117">**visImageBlur**</span><span class="sxs-lookup"><span data-stu-id="97e22-117">**visImageBlur**</span></span> <br/> |
   

