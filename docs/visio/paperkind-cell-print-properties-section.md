---
title: PaperKind 单元格（“Print Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60067
localization_priority: Normal
ms.assetid: b2c9616f-a144-eb99-54b6-b53745c7b4d6
description: 指定打印绘图页的纸张类型。
ms.openlocfilehash: 694aa1fb8b52f5ae323c47e9aab8715b4a48dfb0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408444"
---
# <a name="paperkind-cell-print-properties-section"></a><span data-ttu-id="4b3f3-103">PaperKind 单元格（“Print Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="4b3f3-103">PaperKind Cell (Print Properties Section)</span></span>

<span data-ttu-id="4b3f3-104">指定打印绘图页的纸张类型。</span><span class="sxs-lookup"><span data-stu-id="4b3f3-104">Specifies the type of paper on which to print the page.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="4b3f3-105">备注</span><span class="sxs-lookup"><span data-stu-id="4b3f3-105">Remarks</span></span>

<span data-ttu-id="4b3f3-106">此设置对应于"打印设置"对话框中的"纸张大小"设置 ("设计"选项卡上，单击"页面设置"箭头，然后在"打印设置"选项卡上单击"设置"按钮) 。   </span><span class="sxs-lookup"><span data-stu-id="4b3f3-106">This setting corresponds to the **Paper Size** setting in the **Print Setup** dialog box (on the **Design** tab, click the **Page Setup** arrow, and then on the **Print Setup** tab, click the **Setup** button).</span></span> 
  
<span data-ttu-id="4b3f3-107">此单元格中的数值映射到以 DMPAPER (为前缀) Microsoft Windows wingdi.h 文件中定义的常量。</span><span class="sxs-lookup"><span data-stu-id="4b3f3-107">The numeric values in this cell map to constants (prefixed with DMPAPER) defined for paper selections in the Microsoft Windows wingdi.h file.</span></span> 
  
<span data-ttu-id="4b3f3-108">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 PaperKind 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="4b3f3-108">To get a reference to the PaperKind cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="4b3f3-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="4b3f3-109">Cell name:</span></span>  <br/> |<span data-ttu-id="4b3f3-110">PaperKind</span><span class="sxs-lookup"><span data-stu-id="4b3f3-110">PaperKind</span></span>  <br/> |
   
<span data-ttu-id="4b3f3-111">若要从某个程序按索引获取对 PaperKind 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="4b3f3-111">To get a reference to the PaperKind cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="4b3f3-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="4b3f3-112">Section index:</span></span>  <br/> |<span data-ttu-id="4b3f3-113">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="4b3f3-113">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="4b3f3-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="4b3f3-114">Row index:</span></span>  <br/> |<span data-ttu-id="4b3f3-115">**visRowPrintProperties**</span><span class="sxs-lookup"><span data-stu-id="4b3f3-115">**visRowPrintProperties**</span></span> <br/> |
|<span data-ttu-id="4b3f3-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="4b3f3-116">Cell index:</span></span>  <br/> |<span data-ttu-id="4b3f3-117">**visPrintPropertiesPaperKind**</span><span class="sxs-lookup"><span data-stu-id="4b3f3-117">**visPrintPropertiesPaperKind**</span></span> <br/> |
   

