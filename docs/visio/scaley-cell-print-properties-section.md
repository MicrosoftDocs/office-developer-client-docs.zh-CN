---
title: ScaleY 单元格（“Print Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033788
localization_priority: Normal
ms.assetid: 02835aff-455b-ffeb-d53b-28387b6ce361
description: 指定绘图页在打印纸上的比例百分比。
ms.openlocfilehash: 0f8e86675a039002b60438eac7df92f4a2b13b98
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406988"
---
# <a name="scaley-cell-print-properties-section"></a><span data-ttu-id="55288-103">ScaleY 单元格（“Print Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="55288-103">ScaleY Cell (Print Properties Section)</span></span>

<span data-ttu-id="55288-104">指定绘图页在打印纸上的比例百分比。</span><span class="sxs-lookup"><span data-stu-id="55288-104">Specifies the percentage of magnification of the drawing page on the printer page.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="55288-105">说明</span><span class="sxs-lookup"><span data-stu-id="55288-105">Remarks</span></span>

<span data-ttu-id="55288-106">只有在 OnPage 单元格的值为 FALSE 时才使用此值。</span><span class="sxs-lookup"><span data-stu-id="55288-106">This value is used only when the OnPage cell value is FALSE.</span></span> <span data-ttu-id="55288-107">ScaleX 和 ScaleY 单元格的值始终相同, 这与 "**页面设置**" 对话框 (在 "**设计**" 选项卡上, 单击 "**页面设置**" 箭头) 的 "**打印设置**" 选项卡上的 "**调整为**" 设置中的值相对应。</span><span class="sxs-lookup"><span data-stu-id="55288-107">The ScaleX and ScaleY cells always have the same value, which corresponds to the value in the **Adjust to** setting on the **Print Setup** tab in the **Page Setup** dialog box (on the **Design** tab, click the **Page Setup** arrow).</span></span> 
  
<span data-ttu-id="55288-108">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ScaleY 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="55288-108">To get a reference to the ScaleY cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="55288-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="55288-109">Cell name:</span></span>  <br/> |<span data-ttu-id="55288-110">ScaleY</span><span class="sxs-lookup"><span data-stu-id="55288-110">ScaleY</span></span>  <br/> |
   
<span data-ttu-id="55288-111">若要从某个程序按索引获取对 ScaleY 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="55288-111">To get a reference to the ScaleY cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="55288-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="55288-112">Section index:</span></span>  <br/> |<span data-ttu-id="55288-113">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="55288-113">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="55288-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="55288-114">Row index:</span></span>  <br/> |<span data-ttu-id="55288-115">**visRowPrintProperties**</span><span class="sxs-lookup"><span data-stu-id="55288-115">**visRowPrintProperties**</span></span> <br/> |
|<span data-ttu-id="55288-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="55288-116">Cell index:</span></span>  <br/> |<span data-ttu-id="55288-117">**visPrintPropertiesScaleY**</span><span class="sxs-lookup"><span data-stu-id="55288-117">**visPrintPropertiesScaleY**</span></span> <br/> |
   

