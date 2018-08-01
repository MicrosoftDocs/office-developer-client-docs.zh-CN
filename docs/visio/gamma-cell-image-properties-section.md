---
title: Gamma 单元格（“Image Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm410
localization_priority: Normal
ms.assetid: 3dcaee26-391c-0494-4380-890ee825dc47
description: 调整或校正图像的亮度，使之适合特定的输出设备，如监视器或扫描仪等。默认值为 1（不校正）。
ms.openlocfilehash: 060cb02aa8fd33e5a6c70a2c0236f16b9552aea0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780325"
---
# <a name="gamma-cell-image-properties-section"></a><span data-ttu-id="62752-104">Gamma 单元格（“Image Properties”部分）</span><span class="sxs-lookup"><span data-stu-id="62752-104">Gamma Cell (Image Properties Section)</span></span>

<span data-ttu-id="62752-p102">调整或校正图像的亮度，使之适合特定的输出设备，如监视器或扫描仪等。默认值为 1（不校正）。</span><span class="sxs-lookup"><span data-stu-id="62752-p102">Adjusts or corrects the intensity of an image for a particular output device, such as a monitor or scanner. The default value is 1 (no correction).</span></span>
  
## <a name="remarks"></a><span data-ttu-id="62752-107">注释</span><span class="sxs-lookup"><span data-stu-id="62752-107">Remarks</span></span>

<span data-ttu-id="62752-108">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Gamma 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="62752-108">To get a reference to the Gamma cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="62752-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="62752-109">Cell name:</span></span>  <br/> | <span data-ttu-id="62752-110">Gamma</span><span class="sxs-lookup"><span data-stu-id="62752-110">Gamma</span></span>  <br/> |
   
<span data-ttu-id="62752-111">要从某个程序按索引获取对 Gamma 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="62752-111">To get a reference to the Gamma cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="62752-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="62752-112">Section index:</span></span>  <br/> |<span data-ttu-id="62752-113">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="62752-113">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="62752-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="62752-114">Row index:</span></span>  <br/> |<span data-ttu-id="62752-115">**visRowImage**</span><span class="sxs-lookup"><span data-stu-id="62752-115">**visRowImage**</span></span> <br/> |
| <span data-ttu-id="62752-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="62752-116">Cell index:</span></span>  <br/> |<span data-ttu-id="62752-117">**visImageGamma**</span><span class="sxs-lookup"><span data-stu-id="62752-117">**visImageGamma**</span></span> <br/> |
   

