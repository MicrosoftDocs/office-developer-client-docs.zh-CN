---
title: PlaceStyle 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 7dcd5a35-bd3d-447f-e4aa-986091d129de
description: 确定在“配置布局”对话框（在“设计”选项卡上的“布局”组中，单击“重新布局页面”，然后单击“其他布局选项”）中排放形状时如何在页面上放置这些形状。
ms.openlocfilehash: b3159b765922d6656d12dd42a377322e4a91fc04
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420799"
---
# <a name="placestyle-cell-page-layout-section"></a><span data-ttu-id="ef5fc-103">PlaceStyle 单元格（“Page Layout”内容）</span><span class="sxs-lookup"><span data-stu-id="ef5fc-103">PlaceStyle Cell (Page Layout Section)</span></span>

<span data-ttu-id="ef5fc-104">确定在 **“配置布局”** 对话框（在 **“设计”** 选项卡上的 **“布局”** 组中，单击 **“重新布局页面”**，然后单击 **“其他布局选项”**）中排放形状时如何在页面上放置这些形状。</span><span class="sxs-lookup"><span data-stu-id="ef5fc-104">Determines how shapes are placed on the page when you are laying out shapes by using the **Configure Layout** dialog box (on the **Design** tab, in the **Layout** group, click **Re-Layout Page**, and then click **More Layout Options**).</span></span>
  
## <a name="remarks"></a><span data-ttu-id="ef5fc-105">说明</span><span class="sxs-lookup"><span data-stu-id="ef5fc-105">Remarks</span></span>

<span data-ttu-id="ef5fc-106">还可以在 **“配置布局”** 对话框中设置此单元格的值。</span><span class="sxs-lookup"><span data-stu-id="ef5fc-106">You can also set the value of this cell in the **Configure Layout** dialog box.</span></span> 
  
<span data-ttu-id="ef5fc-107">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 PlaceStyle 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="ef5fc-107">To get a reference to the PlaceStyle cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ef5fc-108">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="ef5fc-108">Cell name:</span></span>  <br/> |<span data-ttu-id="ef5fc-109">PlaceStyle</span><span class="sxs-lookup"><span data-stu-id="ef5fc-109">PlaceStyle</span></span>  <br/> |
   
<span data-ttu-id="ef5fc-110">若要从某个程序按索引获取对 PlaceStyle 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="ef5fc-110">To get a reference to the PlaceStyle cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ef5fc-111">内容索引：</span><span class="sxs-lookup"><span data-stu-id="ef5fc-111">Section index:</span></span>  <br/> |<span data-ttu-id="ef5fc-112">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="ef5fc-112">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="ef5fc-113">行索引：</span><span class="sxs-lookup"><span data-stu-id="ef5fc-113">Row index:</span></span>  <br/> |<span data-ttu-id="ef5fc-114">**visRowPageLayout**</span><span class="sxs-lookup"><span data-stu-id="ef5fc-114">**visRowPageLayout**</span></span> <br/> |
|<span data-ttu-id="ef5fc-115">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="ef5fc-115">Cell index:</span></span>  <br/> |<span data-ttu-id="ef5fc-116">**visPLOPlaceStyle**</span><span class="sxs-lookup"><span data-stu-id="ef5fc-116">**visPLOPlaceStyle**</span></span> <br/> |
   

