---
title: BlockSizeY 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm110
localization_priority: Normal
ms.assetid: be51e18e-ea49-0788-1a17-866090afb9f4
description: 确定垂直块大小, 当您使用 "配置布局" 对话框 (在 "设计" 选项卡上的 "布局" 组中, 单击 "重新布局页面", 然后单击 "其他布局选项") 排放形状时, 绘图页上每个形状都必须符合的区域。
ms.openlocfilehash: 08f2012bb027267810c21ef253a0073bb42d3a96
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32297345"
---
# <a name="blocksizey-cell-page-layout-section"></a><span data-ttu-id="d2feb-103">BlockSizeY 单元格（“Page Layout”内容）</span><span class="sxs-lookup"><span data-stu-id="d2feb-103">BlockSizeY Cell (Page Layout Section)</span></span>

<span data-ttu-id="d2feb-104">确定垂直块大小, 当您使用 "**配置布局**" 对话框 (在 "**设计**" 选项卡上的 "布局" 组中的 "**布局**" 组中, 单击 "**重新布局页面**",, 然后单击 "**其他布局选项**"。</span><span class="sxs-lookup"><span data-stu-id="d2feb-104">Determines the vertical block size, the area in which each of your shapes must fit on the drawing page when you lay out shapes by using the **Configure Layout** dialog box (on the **Design** tab, in the **Layout** group, click **Re-Layout Page**, and then click **More Layout Options**).</span></span>
  
## <a name="remarks"></a><span data-ttu-id="d2feb-105">注解</span><span class="sxs-lookup"><span data-stu-id="d2feb-105">Remarks</span></span>

<span data-ttu-id="d2feb-106">您还可以在 **“布局与排列间距”** 对话框（在 **“设计”** 选项卡上，单击 **“页面设置”** 组中的箭头，单击 **“布局与排列”** 选项卡，然后单击 **“间距”**）中设置此值。</span><span class="sxs-lookup"><span data-stu-id="d2feb-106">You can also set this value in the **Layout and Routing Spacing** dialog box (on the **Design** tab, click the arrow in the **Page Setup** group, click the **Layout and Routing** tab, and then click **Spacing**).</span></span>
  
<span data-ttu-id="d2feb-107">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 BlockSizeY 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="d2feb-107">To get a reference to the BlockSizeY cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="d2feb-108">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="d2feb-108">Cell name:</span></span>  <br/> | <span data-ttu-id="d2feb-109">BlockSizeY</span><span class="sxs-lookup"><span data-stu-id="d2feb-109">BlockSizeY</span></span>  <br/> |
   
<span data-ttu-id="d2feb-110">若要从某个程序按索引获取对 BlockSizeY 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="d2feb-110">To get a reference to the BlockSizeY cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="d2feb-111">内容索引：</span><span class="sxs-lookup"><span data-stu-id="d2feb-111">Section index:</span></span>  <br/> |<span data-ttu-id="d2feb-112">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="d2feb-112">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="d2feb-113">行索引：</span><span class="sxs-lookup"><span data-stu-id="d2feb-113">Row index:</span></span>  <br/> |<span data-ttu-id="d2feb-114">**visRowPageLayout**</span><span class="sxs-lookup"><span data-stu-id="d2feb-114">**visRowPageLayout**</span></span> <br/> |
| <span data-ttu-id="d2feb-115">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="d2feb-115">Cell index:</span></span>  <br/> |<span data-ttu-id="d2feb-116">**visPLOBlockSizeY**</span><span class="sxs-lookup"><span data-stu-id="d2feb-116">**visPLOBlockSizeY**</span></span> <br/> |
   

