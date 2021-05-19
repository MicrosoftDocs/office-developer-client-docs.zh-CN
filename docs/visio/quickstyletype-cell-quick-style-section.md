---
title: 'QuickStyleType Cell (Quick Style Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: e7470417-0d70-433e-9496-604ca2eafee6
description: 确定形状继承 (二维、一维或) 快速样式类型。
ms.openlocfilehash: 95aced62c6397fc3229de29b98d3f18e5f69d05b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410502"
---
# <a name="quickstyletype-cell-quick-style-section"></a><span data-ttu-id="08977-103">QuickStyleType Cell (Quick Style Section) </span><span class="sxs-lookup"><span data-stu-id="08977-103">QuickStyleType Cell (Quick Style Section)</span></span>

<span data-ttu-id="08977-104">确定形状继承 (二维、一维或) 快速样式类型。</span><span class="sxs-lookup"><span data-stu-id="08977-104">Determines the type of Quick Style (2-dimensional, 1-dimensional, or connector) that the shape inherits.</span></span> 
  
|<span data-ttu-id="08977-105">**值**</span><span class="sxs-lookup"><span data-stu-id="08977-105">**Value**</span></span>|<span data-ttu-id="08977-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="08977-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="08977-107">0</span><span class="sxs-lookup"><span data-stu-id="08977-107">0</span></span>  <br/> |<span data-ttu-id="08977-108">Visio自动选择</span><span class="sxs-lookup"><span data-stu-id="08977-108">Visio chooses automatically</span></span>  <br/> |
|<span data-ttu-id="08977-109">1</span><span class="sxs-lookup"><span data-stu-id="08977-109">1</span></span>  <br/> |<span data-ttu-id="08977-110">一维</span><span class="sxs-lookup"><span data-stu-id="08977-110">1-dimensional</span></span>  <br/> |
|<span data-ttu-id="08977-111">2</span><span class="sxs-lookup"><span data-stu-id="08977-111">2</span></span>  <br/> |<span data-ttu-id="08977-112">二维</span><span class="sxs-lookup"><span data-stu-id="08977-112">2-dimensional</span></span>  <br/> |
|<span data-ttu-id="08977-113">3</span><span class="sxs-lookup"><span data-stu-id="08977-113">3</span></span>  <br/> |<span data-ttu-id="08977-114">连接器</span><span class="sxs-lookup"><span data-stu-id="08977-114">Connector</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="08977-115">备注</span><span class="sxs-lookup"><span data-stu-id="08977-115">Remarks</span></span>

<span data-ttu-id="08977-116">若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 **CellsU** 属性从某个程序按名称获取对 **QuickStyleType** 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="08977-116">To get a reference to the **QuickStyleType** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="08977-117">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="08977-117">Cell name:</span></span>  <br/> | <span data-ttu-id="08977-118">QuickStyleType</span><span class="sxs-lookup"><span data-stu-id="08977-118">QuickStyleType</span></span>  <br/> |
   
<span data-ttu-id="08977-119">若要从程序按索引获取对 **QuickStyleType** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="08977-119">To get a reference to the **QuickStyleType** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="08977-120">内容索引：</span><span class="sxs-lookup"><span data-stu-id="08977-120">Section index:</span></span>  <br/> |<span data-ttu-id="08977-121">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="08977-121">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="08977-122">行索引：</span><span class="sxs-lookup"><span data-stu-id="08977-122">Row index:</span></span>  <br/> |<span data-ttu-id="08977-123">**visRowQuickStyleProperties**</span><span class="sxs-lookup"><span data-stu-id="08977-123">**visRowQuickStyleProperties**</span></span> <br/> |
| <span data-ttu-id="08977-124">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="08977-124">Cell index:</span></span>  <br/> |<span data-ttu-id="08977-125">**visQuickStyleType**</span><span class="sxs-lookup"><span data-stu-id="08977-125">**visQuickStyleType**</span></span> <br/> |
   

