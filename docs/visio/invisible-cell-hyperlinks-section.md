---
title: Invisible 单元格（“Hyperlinks”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033755
localization_priority: Normal
ms.assetid: e67dcd83-4a88-a0f8-5c6a-dae51424edbd
description: 指示超链接是否出现在形状或页面的快捷菜单上。
ms.openlocfilehash: b52da8244bf31e75bacbb6f24f73eba6ee8c6e5f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348333"
---
# <a name="invisible-cell-hyperlinks-section"></a><span data-ttu-id="febbe-103">Invisible 单元格（“Hyperlinks”内容）</span><span class="sxs-lookup"><span data-stu-id="febbe-103">Invisible Cell (Hyperlinks Section)</span></span>

<span data-ttu-id="febbe-104">指示超链接是否出现在形状或页面的快捷菜单上。</span><span class="sxs-lookup"><span data-stu-id="febbe-104">Indicates whether a hyperlink appears on the shortcut menu for a shape or page.</span></span> 
  
|<span data-ttu-id="febbe-105">**Value**</span><span class="sxs-lookup"><span data-stu-id="febbe-105">**Value**</span></span>|<span data-ttu-id="febbe-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="febbe-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="febbe-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="febbe-107">TRUE</span></span>  <br/> |<span data-ttu-id="febbe-108">超链接不显示为快捷菜单上的菜单项。</span><span class="sxs-lookup"><span data-stu-id="febbe-108">The hyperlink does not appear as a menu item on the shortcut menu.</span></span>  <br/> |
|<span data-ttu-id="febbe-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="febbe-109">FALSE</span></span>  <br/> |<span data-ttu-id="febbe-110">超链接显示为快捷菜单上的菜单项（默认值）。</span><span class="sxs-lookup"><span data-stu-id="febbe-110">The hyperlink does appear as a menu item on the shortcut menu (the default).</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="febbe-111">注解</span><span class="sxs-lookup"><span data-stu-id="febbe-111">Remarks</span></span>

<span data-ttu-id="febbe-112">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Invisible 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="febbe-112">To get a reference to the Invisible cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="febbe-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="febbe-113">Cell name:</span></span>  <br/> |<span data-ttu-id="febbe-114">超链接。</span><span class="sxs-lookup"><span data-stu-id="febbe-114">Hyperlink.</span></span> <span data-ttu-id="febbe-115">*名称*。在超链接的位置不可见 *。 name*为行名称</span><span class="sxs-lookup"><span data-stu-id="febbe-115">*name*  .Invisible where Hyperlink  *.name*  is the row name</span></span>  <br/> |
   
<span data-ttu-id="febbe-116">若要从某个程序按索引获取对 Invisible 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="febbe-116">To get a reference to the Invisible cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="febbe-117">内容索引：</span><span class="sxs-lookup"><span data-stu-id="febbe-117">Section index:</span></span>  <br/> |<span data-ttu-id="febbe-118">**visSectionHyperlink**</span><span class="sxs-lookup"><span data-stu-id="febbe-118">**visSectionHyperlink**</span></span> <br/> |
|<span data-ttu-id="febbe-119">行索引：</span><span class="sxs-lookup"><span data-stu-id="febbe-119">Row index:</span></span>  <br/> |<span data-ttu-id="febbe-120">**visRow1stHyperlink** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="febbe-120">**visRow1stHyperlink** +  *i*  where  *i*  = 0, 1, 2...</span></span>  <br/> |
|<span data-ttu-id="febbe-121">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="febbe-121">Cell index:</span></span>  <br/> |<span data-ttu-id="febbe-122">**visHLinkInvisible**</span><span class="sxs-lookup"><span data-stu-id="febbe-122">**visHLinkInvisible**</span></span> <br/> |
   

