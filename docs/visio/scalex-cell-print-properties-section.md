---
title: ScaleX 单元格（“Print Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60072
localization_priority: Normal
ms.assetid: 5916eadc-37f8-47af-fe54-f6062aea318f
description: 在打印纸上指定百分比的绘图页的放大倍数。
ms.openlocfilehash: 1713e88f06dc93a2806e64cae3d7af20c9df1fc8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781220"
---
# <a name="scalex-cell-print-properties-section"></a><span data-ttu-id="b9b9b-103">ScaleX 单元格（“Print Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="b9b9b-103">ScaleX Cell (Print Properties Section)</span></span>

<span data-ttu-id="b9b9b-104">在打印纸上指定百分比的绘图页的放大倍数。</span><span class="sxs-lookup"><span data-stu-id="b9b9b-104">Specifies the percentage of magnification of the drawing page on the printer page.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="b9b9b-105">备注</span><span class="sxs-lookup"><span data-stu-id="b9b9b-105">Remarks</span></span>

<span data-ttu-id="b9b9b-106">仅当 OnPage 单元格的值为 FALSE 时，才使用此值。</span><span class="sxs-lookup"><span data-stu-id="b9b9b-106">This value is used only when the OnPage cell value is FALSE.</span></span> <span data-ttu-id="b9b9b-107">ScaleX 和 ScaleY 单元格始终具有相同的值，此名称对应于**页面设置**对话框中**打印设置**选项卡上的**调整为**设置中的值 （**设计**选项卡中，单击**页面设置**箭头）。</span><span class="sxs-lookup"><span data-stu-id="b9b9b-107">The ScaleX and ScaleY cells always have the same value, which corresponds to the value in the **Adjust to** setting on the **Print Setup** tab in the **Page Setup** dialog box (on the **Design** tab, click the **Page Setup** arrow).</span></span> 
  
<span data-ttu-id="b9b9b-108">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 ScaleX 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="b9b9b-108">To get a reference to the ScaleX cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="b9b9b-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="b9b9b-109">Cell name:</span></span>  <br/> |<span data-ttu-id="b9b9b-110">ScaleX</span><span class="sxs-lookup"><span data-stu-id="b9b9b-110">ScaleX</span></span>  <br/> |
   
<span data-ttu-id="b9b9b-111">若要从某个程序按索引获取对 ScaleX 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="b9b9b-111">To get a reference to the ScaleX cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="b9b9b-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="b9b9b-112">Section index:</span></span>  <br/> |<span data-ttu-id="b9b9b-113">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="b9b9b-113">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="b9b9b-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="b9b9b-114">Row index:</span></span>  <br/> |<span data-ttu-id="b9b9b-115">**visRowPrintProperties**</span><span class="sxs-lookup"><span data-stu-id="b9b9b-115">**visRowPrintProperties**</span></span> <br/> |
|<span data-ttu-id="b9b9b-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="b9b9b-116">Cell index:</span></span>  <br/> |<span data-ttu-id="b9b9b-117">**visPrintPropertiesScaleX**</span><span class="sxs-lookup"><span data-stu-id="b9b9b-117">**visPrintPropertiesScaleX**</span></span> <br/> |
   

