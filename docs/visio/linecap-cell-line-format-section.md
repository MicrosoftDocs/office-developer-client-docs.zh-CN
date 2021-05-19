---
title: LineCap 单元格（“Line Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251231
localization_priority: Normal
ms.assetid: 3519216b-b6cf-2e8c-e20f-adfa373c9028
description: 指示线端形状是圆形、方形还是扩展式。
ms.openlocfilehash: 44de4bff87fd3d121dfce9eec934ec39bc61065a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425195"
---
# <a name="linecap-cell-line-format-section"></a><span data-ttu-id="1adf7-103">LineCap 单元格（“Line Format”内容）</span><span class="sxs-lookup"><span data-stu-id="1adf7-103">LineCap Cell (Line Format Section)</span></span>

<span data-ttu-id="1adf7-104">指示线端形状是圆形、方形还是扩展式。</span><span class="sxs-lookup"><span data-stu-id="1adf7-104">Indicates whether a line has rounded, square, or extended line caps.</span></span>
  
|<span data-ttu-id="1adf7-105">**值**</span><span class="sxs-lookup"><span data-stu-id="1adf7-105">**Value**</span></span>|<span data-ttu-id="1adf7-106">**线端样式**</span><span class="sxs-lookup"><span data-stu-id="1adf7-106">**Line end style**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1adf7-107">0</span><span class="sxs-lookup"><span data-stu-id="1adf7-107">0</span></span>  <br/> |<span data-ttu-id="1adf7-108">四舍五入</span><span class="sxs-lookup"><span data-stu-id="1adf7-108">Rounded</span></span>  <br/> |
|<span data-ttu-id="1adf7-109">1</span><span class="sxs-lookup"><span data-stu-id="1adf7-109">1</span></span>  <br/> |<span data-ttu-id="1adf7-110">正方形</span><span class="sxs-lookup"><span data-stu-id="1adf7-110">Square</span></span>  <br/> |
|<span data-ttu-id="1adf7-111">2</span><span class="sxs-lookup"><span data-stu-id="1adf7-111">2</span></span>  <br/> |<span data-ttu-id="1adf7-112">扩展</span><span class="sxs-lookup"><span data-stu-id="1adf7-112">Extended</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1adf7-113">备注</span><span class="sxs-lookup"><span data-stu-id="1adf7-113">Remarks</span></span>

<span data-ttu-id="1adf7-114">您还可以在 **“线条”** 对话框中设置此单元格的值（在 **“开始”** 选项卡上的 **“形状”** 组中，单击 **“线条”**，指向 **“箭头”**，然后单击 **“其他箭头”**）。</span><span class="sxs-lookup"><span data-stu-id="1adf7-114">You can also set the value of this cell in the **Line** dialog box (on the **Home** tab, in the **Shape** group, click **Line**, point to **Arrows**, and then click **More Arrows**).</span></span>
  
<span data-ttu-id="1adf7-115">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 LineCap 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="1adf7-115">To get a reference to the LineCap cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="1adf7-116">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="1adf7-116">Cell name:</span></span>  <br/> |<span data-ttu-id="1adf7-117">LineCap</span><span class="sxs-lookup"><span data-stu-id="1adf7-117">LineCap</span></span>  <br/> |
   
<span data-ttu-id="1adf7-118">若要从某个程序按索引获取对 LineCap 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="1adf7-118">To get a reference to the LineCap cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="1adf7-119">内容索引：</span><span class="sxs-lookup"><span data-stu-id="1adf7-119">Section index:</span></span>  <br/> |<span data-ttu-id="1adf7-120">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="1adf7-120">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="1adf7-121">行索引：</span><span class="sxs-lookup"><span data-stu-id="1adf7-121">Row index:</span></span>  <br/> |<span data-ttu-id="1adf7-122">**visRowLine**</span><span class="sxs-lookup"><span data-stu-id="1adf7-122">**visRowLine**</span></span> <br/> |
|<span data-ttu-id="1adf7-123">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="1adf7-123">Cell index:</span></span>  <br/> |<span data-ttu-id="1adf7-124">**visLineEndCap**</span><span class="sxs-lookup"><span data-stu-id="1adf7-124">**visLineEndCap**</span></span> <br/> |
   

