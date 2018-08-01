---
title: PlaceStyle 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 7dcd5a35-bd3d-447f-e4aa-986091d129de
description: 确定在“配置布局”对话框（在“设计”选项卡上的“布局”组中，单击“重新布局页面”，然后单击“其他布局选项”）中排放形状时如何在页面上放置这些形状。
ms.openlocfilehash: 251bee427c732fe782c85c4991df07a1deb2a4dc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780868"
---
# <a name="placestyle-cell-page-layout-section"></a><span data-ttu-id="e7b92-103">PlaceStyle 单元格（“Page Layout”部分）</span><span class="sxs-lookup"><span data-stu-id="e7b92-103">PlaceStyle Cell (Page Layout Section)</span></span>

<span data-ttu-id="e7b92-104">确定在 **“配置布局”** 对话框（在 **“设计”** 选项卡上的 **“布局”** 组中，单击 **“重新布局页面”**，然后单击 **“其他布局选项”**）中排放形状时如何在页面上放置这些形状。</span><span class="sxs-lookup"><span data-stu-id="e7b92-104">Determines how shapes are placed on the page when you are laying out shapes by using the **Configure Layout** dialog box (on the **Design** tab, in the **Layout** group, click **Re-Layout Page**, and then click **More Layout Options**).</span></span>
  
## <a name="remarks"></a><span data-ttu-id="e7b92-105">说明</span><span class="sxs-lookup"><span data-stu-id="e7b92-105">Remarks</span></span>

<span data-ttu-id="e7b92-106">还可以在 **“配置布局”** 对话框中设置此单元格的值。</span><span class="sxs-lookup"><span data-stu-id="e7b92-106">You can also set the value of this cell in the **Configure Layout** dialog box.</span></span> 
  
<span data-ttu-id="e7b92-107">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 PlaceStyle 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="e7b92-107">To get a reference to the PlaceStyle cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e7b92-108">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="e7b92-108">Cell name:</span></span>  <br/> |<span data-ttu-id="e7b92-109">PlaceStyle</span><span class="sxs-lookup"><span data-stu-id="e7b92-109">PlaceStyle</span></span>  <br/> |
   
<span data-ttu-id="e7b92-110">若要从某个程序按索引获取对 PlaceStyle 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="e7b92-110">To get a reference to the PlaceStyle cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e7b92-111">内容索引：</span><span class="sxs-lookup"><span data-stu-id="e7b92-111">Section index:</span></span>  <br/> |<span data-ttu-id="e7b92-112">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="e7b92-112">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="e7b92-113">行索引：</span><span class="sxs-lookup"><span data-stu-id="e7b92-113">Row index:</span></span>  <br/> |<span data-ttu-id="e7b92-114">**visRowPageLayout**</span><span class="sxs-lookup"><span data-stu-id="e7b92-114">**visRowPageLayout**</span></span> <br/> |
|<span data-ttu-id="e7b92-115">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="e7b92-115">Cell index:</span></span>  <br/> |<span data-ttu-id="e7b92-116">**visPLOPlaceStyle**</span><span class="sxs-lookup"><span data-stu-id="e7b92-116">**visPLOPlaceStyle**</span></span> <br/> |
   

