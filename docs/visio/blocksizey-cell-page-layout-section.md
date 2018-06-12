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
description: 确定垂直块大小，其中每个形状中的区域必须适合绘图页，使用配置布局对话框排放形状时 （在设计选项卡上的布局组中，单击重新布局页面，然后单击更多布局选项）。
ms.openlocfilehash: 283723bf902c07cfb044ab73107491df3c170a4d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779782"
---
# <a name="blocksizey-cell-page-layout-section"></a><span data-ttu-id="152f1-103">BlockSizeY 单元格（“Page Layout”内容）</span><span class="sxs-lookup"><span data-stu-id="152f1-103">BlockSizeY Cell (Page Layout Section)</span></span>

<span data-ttu-id="152f1-104">确定垂直块大小，其中每个形状中的区域必须适合绘图页，使用**配置布局**对话框排放形状时 （在**设计**选项卡的**布局**组中，单击**Re 布局页**上，然后单击**更多布局选项**)。</span><span class="sxs-lookup"><span data-stu-id="152f1-104">Determines the vertical block size, the area in which each of your shapes must fit on the drawing page when you lay out shapes by using the **Configure Layout** dialog box (on the **Design** tab, in the **Layout** group, click **Re-Layout Page**, and then click **More Layout Options**).</span></span>
  
## <a name="remarks"></a><span data-ttu-id="152f1-105">备注</span><span class="sxs-lookup"><span data-stu-id="152f1-105">Remarks</span></span>

<span data-ttu-id="152f1-106">您还可以在**布局与排列间距**对话框来设置此值 （**设计**选项卡中，单击**页面设置**组中的箭头，单击**布局和路由**选项卡，然后单击**间距**）。</span><span class="sxs-lookup"><span data-stu-id="152f1-106">You can also set this value in the **Layout and Routing Spacing** dialog box (on the **Design** tab, click the arrow in the **Page Setup** group, click the **Layout and Routing** tab, and then click **Spacing**).</span></span>
  
<span data-ttu-id="152f1-107">若要获取对 BlockSizeY 单元格的引用按名称从另一个公式或从程序使用**CellsU**属性，请使用：</span><span class="sxs-lookup"><span data-stu-id="152f1-107">To get a reference to the BlockSizeY cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="152f1-108">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="152f1-108">Cell name:</span></span>  <br/> | <span data-ttu-id="152f1-109">BlockSizeY</span><span class="sxs-lookup"><span data-stu-id="152f1-109">BlockSizeY</span></span>  <br/> |
   
<span data-ttu-id="152f1-110">若要从某个程序按索引获取对 BlockSizeY 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="152f1-110">To get a reference to the BlockSizeY cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="152f1-111">内容索引：</span><span class="sxs-lookup"><span data-stu-id="152f1-111">Section index:</span></span>  <br/> |<span data-ttu-id="152f1-112">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="152f1-112">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="152f1-113">行索引：</span><span class="sxs-lookup"><span data-stu-id="152f1-113">Row index:</span></span>  <br/> |<span data-ttu-id="152f1-114">**visRowPageLayout**</span><span class="sxs-lookup"><span data-stu-id="152f1-114">**visRowPageLayout**</span></span> <br/> |
| <span data-ttu-id="152f1-115">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="152f1-115">Cell index:</span></span>  <br/> |<span data-ttu-id="152f1-116">**visPLOBlockSizeY**</span><span class="sxs-lookup"><span data-stu-id="152f1-116">**visPLOBlockSizeY**</span></span> <br/> |
   

