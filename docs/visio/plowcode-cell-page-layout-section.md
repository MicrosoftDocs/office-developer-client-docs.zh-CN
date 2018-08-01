---
title: PlowCode 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251660
localization_priority: Normal
ms.assetid: e43f3d29-7def-d36e-ac64-62f0a389d415
description: 确定在绘图页上将一个可放置形状放到另一个可放置形状旁边时，可放置形状是否移走。
ms.openlocfilehash: e180ce679f280cbccbda80b67170f2f26473bd8c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780896"
---
# <a name="plowcode-cell-page-layout-section"></a><span data-ttu-id="4baa5-103">PlowCode 单元格（“Page Layout”部分）</span><span class="sxs-lookup"><span data-stu-id="4baa5-103">PlowCode Cell (Page Layout Section)</span></span>

<span data-ttu-id="4baa5-104">确定在绘图页上将一个可放置形状放到另一个可放置形状旁边时，可放置形状是否移走。</span><span class="sxs-lookup"><span data-stu-id="4baa5-104">Determines whether placeable shapes move away when you drop a placeable shape near another placeable shape on the drawing page.</span></span>
  
|<span data-ttu-id="4baa5-105">**值**</span><span class="sxs-lookup"><span data-stu-id="4baa5-105">**Value**</span></span>|<span data-ttu-id="4baa5-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="4baa5-106">**Description**</span></span>|<span data-ttu-id="4baa5-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="4baa5-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4baa5-108">0</span><span class="sxs-lookup"><span data-stu-id="4baa5-108">0</span></span>  <br/> |<span data-ttu-id="4baa5-109">不移动形状</span><span class="sxs-lookup"><span data-stu-id="4baa5-109">Don't move shapes</span></span>  <br/> |<span data-ttu-id="4baa5-110">**visPLOPlowNone**</span><span class="sxs-lookup"><span data-stu-id="4baa5-110">**visPLOPlowNone**</span></span> <br/> |
|<span data-ttu-id="4baa5-111">1</span><span class="sxs-lookup"><span data-stu-id="4baa5-111">1</span></span>  <br/> |<span data-ttu-id="4baa5-112">移动形状</span><span class="sxs-lookup"><span data-stu-id="4baa5-112">Move shapes</span></span>  <br/> |<span data-ttu-id="4baa5-113">**visPLOPlowAll**</span><span class="sxs-lookup"><span data-stu-id="4baa5-113">**visPLOPlowAll**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4baa5-114">说明</span><span class="sxs-lookup"><span data-stu-id="4baa5-114">Remarks</span></span>

<span data-ttu-id="4baa5-115">您还可以在**页面设置**对话框中**布局和路由**选项卡上设置此单元格的值 （**设计**选项卡中，单击**页面设置**箭头） 通过使用**放下时移其他形状**复选框。</span><span class="sxs-lookup"><span data-stu-id="4baa5-115">You can also set the value of this cell on the **Layout and Routing** tab in the **Page Setup** dialog box (on the **Design** tab, click the **Page Setup** arrow) by using the **Move other shapes away on drop** check box.</span></span> 
  
<span data-ttu-id="4baa5-116">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 PlowCode 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="4baa5-116">To get a reference to the PlowCode cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="4baa5-117">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="4baa5-117">Cell name:</span></span>  <br/> |<span data-ttu-id="4baa5-118">PlowCode</span><span class="sxs-lookup"><span data-stu-id="4baa5-118">PlowCode</span></span>  <br/> |
   
<span data-ttu-id="4baa5-119">若要从某个程序按索引获取对 PlowCode 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="4baa5-119">To get a reference to the PlowCode cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="4baa5-120">内容索引：</span><span class="sxs-lookup"><span data-stu-id="4baa5-120">Section index:</span></span>  <br/> |<span data-ttu-id="4baa5-121">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="4baa5-121">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="4baa5-122">行索引：</span><span class="sxs-lookup"><span data-stu-id="4baa5-122">Row index:</span></span>  <br/> |<span data-ttu-id="4baa5-123">**visRowPageLayout**</span><span class="sxs-lookup"><span data-stu-id="4baa5-123">**visRowPageLayout**</span></span> <br/> |
|<span data-ttu-id="4baa5-124">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="4baa5-124">Cell index:</span></span>  <br/> |<span data-ttu-id="4baa5-125">**visPLOPlowCode**</span><span class="sxs-lookup"><span data-stu-id="4baa5-125">**visPLOPlowCode**</span></span> <br/> |
   

