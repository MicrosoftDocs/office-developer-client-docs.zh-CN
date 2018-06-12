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
description: 确定使用配置布局对话框排放形状时在绘图页上的形状之间的垂直空间量 （在设计选项卡上的布局组中，单击重新布局页面，然后单击更多布局选项）。
ms.openlocfilehash: af4089a3b215efaf49b8a45929ca94799fffcba5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779668"
---
# <a name="avenuesizey-cell-page-layout-section"></a><span data-ttu-id="a9105-103">AvenueSizeY 单元格（“Page Layout”内容）</span><span class="sxs-lookup"><span data-stu-id="a9105-103">AvenueSizeY Cell (Page Layout Section)</span></span>

<span data-ttu-id="a9105-104">确定使用**配置布局**对话框排放形状时在绘图页上的形状之间的垂直空间量 （**设计**选项卡上，在**布局**组中，单击**重新布局**页面，然后单击**更多布局选项**)。</span><span class="sxs-lookup"><span data-stu-id="a9105-104">Determines the amount of vertical space between shapes on the drawing page when you lay out shapes by using the **Configure Layout** dialog box (on the **Design** tab, in the **Layout** group, click **Re-Layout** Page, and then click **More Layout Options**).</span></span>
  
## <a name="remarks"></a><span data-ttu-id="a9105-105">备注</span><span class="sxs-lookup"><span data-stu-id="a9105-105">Remarks</span></span>

<span data-ttu-id="a9105-106">您还可以在**布局与排列间距**对话框来设置此值 （**设计**选项卡中，单击**页面设置**组中的箭头，单击**布局和路由**选项卡，然后单击**间距**）。</span><span class="sxs-lookup"><span data-stu-id="a9105-106">You can also set this value in the **Layout and Routing Spacing** dialog box (on the **Design** tab, click the arrow in the **Page Setup** group, click the **Layout and Routing** tab, and then click **Spacing**).</span></span>
  
<span data-ttu-id="a9105-107">只有一个形状时可用于计算垂直间距，动态网格 AvenueSizeY 单元格中使用的设置。</span><span class="sxs-lookup"><span data-stu-id="a9105-107">The dynamic grid uses the setting in the AvenueSizeY cell when only one shape is available for calculating vertical spacing.</span></span> <span data-ttu-id="a9105-108">在**视图**选项卡上的**视觉帮助**组中，使用动态网格中，选择**动态网格**。</span><span class="sxs-lookup"><span data-stu-id="a9105-108">To use the dynamic grid, on the **View** tab, in the **Visual Aids** group, select **Dynamic Grid**.</span></span>
  
<span data-ttu-id="a9105-109">若要获取对 AvenueSizeY 单元格的引用按名称从另一个公式或从程序使用**CellsU**属性，请使用：</span><span class="sxs-lookup"><span data-stu-id="a9105-109">To get a reference to the AvenueSizeY cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="a9105-110">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="a9105-110">Cell name:</span></span>  <br/> | <span data-ttu-id="a9105-111">AvenueSizeY</span><span class="sxs-lookup"><span data-stu-id="a9105-111">AvenueSizeY</span></span>  <br/> |
   
<span data-ttu-id="a9105-112">若要从某个程序按索引获取对 AvenueSizeY 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="a9105-112">To get a reference to the AvenueSizeY cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="a9105-113">内容索引：</span><span class="sxs-lookup"><span data-stu-id="a9105-113">Section index:</span></span>  <br/> |<span data-ttu-id="a9105-114">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="a9105-114">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="a9105-115">行索引：</span><span class="sxs-lookup"><span data-stu-id="a9105-115">Row index:</span></span>  <br/> |<span data-ttu-id="a9105-116">**visRowPageLayout**</span><span class="sxs-lookup"><span data-stu-id="a9105-116">**visRowPageLayout**</span></span> <br/> |
| <span data-ttu-id="a9105-117">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="a9105-117">Cell index:</span></span>  <br/> |<span data-ttu-id="a9105-118">**visPLOAvenueSizeY**</span><span class="sxs-lookup"><span data-stu-id="a9105-118">**visPLOAvenueSizeY**</span></span> <br/> |
   

