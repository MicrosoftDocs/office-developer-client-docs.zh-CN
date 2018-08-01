---
title: PaperSource 单元格（“PrintProperties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60068
localization_priority: Normal
ms.assetid: 771a2ab4-578d-51c3-fabd-138f7952bb11
description: 确定页面的纸张来源。
ms.openlocfilehash: f1dedf210dfe0dd8cac3d36fdec03fb497f6572c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780839"
---
# <a name="papersource-cell-printproperties-section"></a><span data-ttu-id="cea64-103">PaperSource 单元格（“PrintProperties”部分）</span><span class="sxs-lookup"><span data-stu-id="cea64-103">PaperSource Cell (PrintProperties Section)</span></span>

<span data-ttu-id="cea64-104">确定页面的纸张来源。</span><span class="sxs-lookup"><span data-stu-id="cea64-104">Determines the paper source for the page.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="cea64-105">注解</span><span class="sxs-lookup"><span data-stu-id="cea64-105">Remarks</span></span>

<span data-ttu-id="cea64-106">此设置对应于 **“打印设置”** 对话框中的 **“纸张来源”** 设置（在 **“设计”** 选项卡上，单击 **“页面设置”** 箭头，然后在 **“打印设置”** 选项卡上单击 **“设置”**）。</span><span class="sxs-lookup"><span data-stu-id="cea64-106">This setting corresponds to the **Paper Source** setting in the **Print Setup** dialog box (on the **Design** tab, click the **Page Setup** arrow, and then on the **Print Setup** tab, click **Setup**).</span></span>
  
<span data-ttu-id="cea64-107">此单元格映射到常数 （前缀为 dmbin） 中定义为 Microsoft Windows wingdi.h 文件; 中的数字值例如，值 7 代表 DMBIN_AUTO。</span><span class="sxs-lookup"><span data-stu-id="cea64-107">The numeric values in this cell map to constants (prefixed with DMBIN) defined for bin selections in the Microsoft Windows wingdi.h file; for example, the value 7 represents DMBIN_AUTO.</span></span> 
  
<span data-ttu-id="cea64-108">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 PaperSource 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="cea64-108">To get a reference to the PaperSource cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="cea64-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="cea64-109">Cell name:</span></span>  <br/> |<span data-ttu-id="cea64-110">PaperSource</span><span class="sxs-lookup"><span data-stu-id="cea64-110">PaperSource</span></span>  <br/> |
   
<span data-ttu-id="cea64-111">若要从某个程序按索引获取对 PaperSource 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="cea64-111">To get a reference to the PaperSource cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="cea64-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="cea64-112">Section index:</span></span>  <br/> |<span data-ttu-id="cea64-113">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="cea64-113">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="cea64-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="cea64-114">Row index:</span></span>  <br/> |<span data-ttu-id="cea64-115">**visRowPrintProperties**</span><span class="sxs-lookup"><span data-stu-id="cea64-115">**visRowPrintProperties**</span></span> <br/> |
|<span data-ttu-id="cea64-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="cea64-116">Cell index:</span></span>  <br/> |<span data-ttu-id="cea64-117">**visPrintPropertiesPaperSource**</span><span class="sxs-lookup"><span data-stu-id="cea64-117">**visPrintPropertiesPaperSource**</span></span> <br/> |
   

