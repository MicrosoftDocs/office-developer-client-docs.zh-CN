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
ms.openlocfilehash: d00eb11ff1feffacf0d758bb25cdd56281e91327
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409011"
---
# <a name="gamma-cell-image-properties-section"></a><span data-ttu-id="75493-104">Gamma 单元格（“Image Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="75493-104">Gamma Cell (Image Properties Section)</span></span>

<span data-ttu-id="75493-p102">调整或校正图像的亮度，使之适合特定的输出设备，如监视器或扫描仪等。默认值为 1（不校正）。</span><span class="sxs-lookup"><span data-stu-id="75493-p102">Adjusts or corrects the intensity of an image for a particular output device, such as a monitor or scanner. The default value is 1 (no correction).</span></span>
  
## <a name="remarks"></a><span data-ttu-id="75493-107">备注</span><span class="sxs-lookup"><span data-stu-id="75493-107">Remarks</span></span>

<span data-ttu-id="75493-108">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Gamma 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="75493-108">To get a reference to the Gamma cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="75493-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="75493-109">Cell name:</span></span>  <br/> | <span data-ttu-id="75493-110">Gamma</span><span class="sxs-lookup"><span data-stu-id="75493-110">Gamma</span></span>  <br/> |
   
<span data-ttu-id="75493-111">要从某个程序按索引获取对 Gamma 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="75493-111">To get a reference to the Gamma cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="75493-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="75493-112">Section index:</span></span>  <br/> |<span data-ttu-id="75493-113">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="75493-113">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="75493-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="75493-114">Row index:</span></span>  <br/> |<span data-ttu-id="75493-115">**visRowImage**</span><span class="sxs-lookup"><span data-stu-id="75493-115">**visRowImage**</span></span> <br/> |
| <span data-ttu-id="75493-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="75493-116">Cell index:</span></span>  <br/> |<span data-ttu-id="75493-117">**visImageGamma**</span><span class="sxs-lookup"><span data-stu-id="75493-117">**visImageGamma**</span></span> <br/> |
   

