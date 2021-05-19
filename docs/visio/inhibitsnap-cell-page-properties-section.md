---
title: InhibitSnap 单元格（“Page Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251620
localization_priority: Normal
ms.assetid: ab9fcebc-1550-3b9e-e3b4-e8b92424390b
description: 确定前景页中的形状是否与该页中的其他对象和背景页中的形状对齐。
ms.openlocfilehash: 665130e9f9f938349028ffa1d1c06224e746de5d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426749"
---
# <a name="inhibitsnap-cell-page-properties-section"></a><span data-ttu-id="6637a-103">InhibitSnap 单元格（“Page Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="6637a-103">InhibitSnap Cell (Page Properties Section)</span></span>

<span data-ttu-id="6637a-104">确定前景页中的形状是否与该页中的其他对象和背景页中的形状对齐。</span><span class="sxs-lookup"><span data-stu-id="6637a-104">Determines whether the shapes on a foreground page snap to other objects on the page and shapes on the background page.</span></span>
  
|<span data-ttu-id="6637a-105">**值**</span><span class="sxs-lookup"><span data-stu-id="6637a-105">**Value**</span></span>|<span data-ttu-id="6637a-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="6637a-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="6637a-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="6637a-107">TRUE</span></span>  <br/> | <span data-ttu-id="6637a-108">除对齐标尺和网格外，不对齐该页中的任何对象。</span><span class="sxs-lookup"><span data-stu-id="6637a-108">Inhibit all snapping on the page, except for snapping to the ruler and grid.</span></span>  <br/> |
| <span data-ttu-id="6637a-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="6637a-109">FALSE</span></span>  <br/> | <span data-ttu-id="6637a-110">启用对齐。</span><span class="sxs-lookup"><span data-stu-id="6637a-110">Enable snapping.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6637a-111">备注</span><span class="sxs-lookup"><span data-stu-id="6637a-111">Remarks</span></span>

<span data-ttu-id="6637a-112">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 InhibitSnap 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="6637a-112">To get a reference to the InhibitSnap cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="6637a-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="6637a-113">Cell name:</span></span>  <br/> | <span data-ttu-id="6637a-114">InhibitSnap</span><span class="sxs-lookup"><span data-stu-id="6637a-114">InhibitSnap</span></span>  <br/> |
   
<span data-ttu-id="6637a-115">要从某个程序按索引获取对 InhibitSnap 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="6637a-115">To get a reference to the InhibitSnap cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="6637a-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="6637a-116">Section index:</span></span>  <br/> |<span data-ttu-id="6637a-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="6637a-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="6637a-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="6637a-118">Row index:</span></span>  <br/> |<span data-ttu-id="6637a-119">**visRowPage**</span><span class="sxs-lookup"><span data-stu-id="6637a-119">**visRowPage**</span></span> <br/> |
| <span data-ttu-id="6637a-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="6637a-120">Cell index:</span></span>  <br/> |<span data-ttu-id="6637a-121">**visPageInhibitSnap**</span><span class="sxs-lookup"><span data-stu-id="6637a-121">**visPageInhibitSnap**</span></span> <br/> |
   

