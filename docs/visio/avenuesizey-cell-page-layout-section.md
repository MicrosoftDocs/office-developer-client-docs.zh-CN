---
title: AvenueSizeY 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm70
localization_priority: Normal
ms.assetid: 9ff2893c-afe5-505e-0b55-48ec1de08a5f
description: 确定使用 "配置布局" 对话框 (在 "设计" 选项卡上的 "布局" 组中, 单击 "重新布局页面", 然后单击 "其他布局选项") 排放形状时, 绘图页上的形状之间的垂直间距量。
ms.openlocfilehash: 283de8925e34c470fd1f9e78b8ae58882be8b7fc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338421"
---
# <a name="avenuesizey-cell-page-layout-section"></a><span data-ttu-id="d190c-103">AvenueSizeY 单元格（“Page Layout”内容）</span><span class="sxs-lookup"><span data-stu-id="d190c-103">AvenueSizeY Cell (Page Layout Section)</span></span>

<span data-ttu-id="d190c-104">确定使用 "**配置布局**" 对话框 (在 "**设计**" 选项卡上的 "**布局**" 组中, 单击 "**重新布局**页面", 然后单击 "其他") 排放形状时, 绘图页上形状之间的垂直间距量。 **布局选项**)。</span><span class="sxs-lookup"><span data-stu-id="d190c-104">Determines the amount of vertical space between shapes on the drawing page when you lay out shapes by using the **Configure Layout** dialog box (on the **Design** tab, in the **Layout** group, click **Re-Layout** Page, and then click **More Layout Options**).</span></span>
  
## <a name="remarks"></a><span data-ttu-id="d190c-105">注解</span><span class="sxs-lookup"><span data-stu-id="d190c-105">Remarks</span></span>

<span data-ttu-id="d190c-106">您还可以在 **“布局与排列间距”** 对话框（在 **“设计”** 选项卡上，单击 **“页面设置”** 组中的箭头，单击 **“布局与排列”** 选项卡，然后单击 **“间距”**）中设置此值。</span><span class="sxs-lookup"><span data-stu-id="d190c-106">You can also set this value in the **Layout and Routing Spacing** dialog box (on the **Design** tab, click the arrow in the **Page Setup** group, click the **Layout and Routing** tab, and then click **Spacing**).</span></span>
  
<span data-ttu-id="d190c-p101">当只可计算一个形状的垂直间距时，动态网格会使用 AvenueSizeY 单元格中的该设置。若要使用动态网格，请在 **“视图”** 选项卡上的 **“视觉帮助”** 组中选择 **“动态网格”**。</span><span class="sxs-lookup"><span data-stu-id="d190c-p101">The dynamic grid uses the setting in the AvenueSizeY cell when only one shape is available for calculating vertical spacing. To use the dynamic grid, on the **View** tab, in the **Visual Aids** group, select **Dynamic Grid**.</span></span>
  
<span data-ttu-id="d190c-109">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 AvenueSizeY 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="d190c-109">To get a reference to the AvenueSizeY cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="d190c-110">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="d190c-110">Cell name:</span></span>  <br/> | <span data-ttu-id="d190c-111">AvenueSizeY</span><span class="sxs-lookup"><span data-stu-id="d190c-111">AvenueSizeY</span></span>  <br/> |
   
<span data-ttu-id="d190c-112">若要从某个程序按索引获取对 AvenueSizeY 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="d190c-112">To get a reference to the AvenueSizeY cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="d190c-113">内容索引：</span><span class="sxs-lookup"><span data-stu-id="d190c-113">Section index:</span></span>  <br/> |<span data-ttu-id="d190c-114">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="d190c-114">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="d190c-115">行索引：</span><span class="sxs-lookup"><span data-stu-id="d190c-115">Row index:</span></span>  <br/> |<span data-ttu-id="d190c-116">**visRowPageLayout**</span><span class="sxs-lookup"><span data-stu-id="d190c-116">**visRowPageLayout**</span></span> <br/> |
| <span data-ttu-id="d190c-117">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="d190c-117">Cell index:</span></span>  <br/> |<span data-ttu-id="d190c-118">**visPLOAvenueSizeY**</span><span class="sxs-lookup"><span data-stu-id="d190c-118">**visPLOAvenueSizeY**</span></span> <br/> |
   

