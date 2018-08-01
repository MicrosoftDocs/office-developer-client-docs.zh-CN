---
title: ShdwForegndTrans 单元格（“Fill Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82253253
localization_priority: Normal
ms.assetid: c42d4d2e-f8f0-bc5b-6018-4bb4ffa81b64
description: 确定用于形状的投影填充图案的前景（划线）颜色的透明度级别。
ms.openlocfilehash: 5fd385fc2f46f1ff8eedc961833813ec16ba7b73
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781317"
---
# <a name="shdwforegndtrans-cell-fill-format-section"></a><span data-ttu-id="acf25-103">ShdwForegndTrans 单元格（“Fill Format”部分）</span><span class="sxs-lookup"><span data-stu-id="acf25-103">ShdwForegndTrans Cell (Fill Format Section)</span></span>

<span data-ttu-id="acf25-104">确定用于形状的投影填充图案的前景（划线）颜色的透明度级别。</span><span class="sxs-lookup"><span data-stu-id="acf25-104">Determines the transparency level for the color used for the foreground (stroke) of the shape's drop shadow fill pattern.</span></span>
  
|<span data-ttu-id="acf25-105">**值**</span><span class="sxs-lookup"><span data-stu-id="acf25-105">**Value**</span></span>|<span data-ttu-id="acf25-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="acf25-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="acf25-107">
          0 - 100
</span><span class="sxs-lookup"><span data-stu-id="acf25-107">0 - 100</span></span>  <br/> |<span data-ttu-id="acf25-p101">表示透明度的百分比。默认值为 0%（完全不透明）。</span><span class="sxs-lookup"><span data-stu-id="acf25-p101">Represents the percentage of transparency. The default is 0% (completely opaque).</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="acf25-110">注解</span><span class="sxs-lookup"><span data-stu-id="acf25-110">Remarks</span></span>

<span data-ttu-id="acf25-111">值将四舍五入到最接近半百分比。</span><span class="sxs-lookup"><span data-stu-id="acf25-111">Values are rounded to the nearest half percent.</span></span> <span data-ttu-id="acf25-112">值为 100%是完全透明的。</span><span class="sxs-lookup"><span data-stu-id="acf25-112">A value of 100% is completely transparent.</span></span> <span data-ttu-id="acf25-113">虽然具有完全透明填充阴影显示在绘图页上相同为阴影没有填充，它与交互页上的其他对象中的相同方式透明度当作 0%。</span><span class="sxs-lookup"><span data-stu-id="acf25-113">Although a shadow that has a completely transparent fill appears the same on the drawing page as a shadow that has no fill, it interacts with other objects on the page in the same ways as if its transparency were 0%.</span></span>
  
<span data-ttu-id="acf25-p103">您还可以使用 **“阴影”** 对话框（在 **“开始”** 选项卡上的 **“形状”** 组中，单击 **“阴影”**，然后单击 **“阴影选项”**）中的滑块控件设置此值。此值同时控制背景和前景阴影透明度的值。若要单独设置上述值，必须在 ShapeSheet 窗口中输入它们。</span><span class="sxs-lookup"><span data-stu-id="acf25-p103">You can also set this value by using the slider control in the **Shadow** dialog box (on the **Home** tab, in the **Shape** group, click **Shadow**, and then click **Shadow Options**). This value controls the value of both the background and foreground shadow transparencies. To set these values independently, you must enter them in the ShapeSheet window.</span></span>
  
<span data-ttu-id="acf25-117">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ShdwForegndTrans 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="acf25-117">To get a reference to the ShdwForegndTrans cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="acf25-118">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="acf25-118">Cell name:</span></span>  <br/> |<span data-ttu-id="acf25-119">ShdwForegndTrans</span><span class="sxs-lookup"><span data-stu-id="acf25-119">ShdwForegndTrans</span></span>  <br/> |
   
<span data-ttu-id="acf25-120">若要从某个程序按索引获取对 ShdwForegndTrans 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="acf25-120">To get a reference to the ShdwForegndTrans cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="acf25-121">内容索引：</span><span class="sxs-lookup"><span data-stu-id="acf25-121">Section index:</span></span>  <br/> |<span data-ttu-id="acf25-122">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="acf25-122">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="acf25-123">行索引：</span><span class="sxs-lookup"><span data-stu-id="acf25-123">Row index:</span></span>  <br/> |<span data-ttu-id="acf25-124">**visRowFill**</span><span class="sxs-lookup"><span data-stu-id="acf25-124">**visRowFill**</span></span> <br/> |
|<span data-ttu-id="acf25-125">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="acf25-125">Cell index:</span></span>  <br/> |<span data-ttu-id="acf25-126">**visFillShdwForegndTrans**</span><span class="sxs-lookup"><span data-stu-id="acf25-126">**visFillShdwForegndTrans**</span></span> <br/> |
   

