---
title: QuickStyleType 单元格（“Quick Style”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: e7470417-0d70-433e-9496-604ca2eafee6
description: 确定快速样式的类型 (二维、 一维或连接器) 形状继承的。
ms.openlocfilehash: 211074800eee601d2658edbc03bb95d028920e54
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781006"
---
# <a name="quickstyletype-cell-quick-style-section"></a><span data-ttu-id="afd3e-103">QuickStyleType 单元格（“Quick Style”部分）</span><span class="sxs-lookup"><span data-stu-id="afd3e-103">QuickStyleType Cell (Quick Style Section)</span></span>

<span data-ttu-id="afd3e-104">确定快速样式的类型 (二维、 一维或连接器) 形状继承的。</span><span class="sxs-lookup"><span data-stu-id="afd3e-104">Determines the type of Quick Style (2-dimensional, 1-dimensional, or connector) that the shape inherits.</span></span> 
  
|<span data-ttu-id="afd3e-105">**值**</span><span class="sxs-lookup"><span data-stu-id="afd3e-105">**Value**</span></span>|<span data-ttu-id="afd3e-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="afd3e-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="afd3e-107">0</span><span class="sxs-lookup"><span data-stu-id="afd3e-107">0</span></span>  <br/> |<span data-ttu-id="afd3e-108">Visio 自动选择</span><span class="sxs-lookup"><span data-stu-id="afd3e-108">Visio chooses automatically</span></span>  <br/> |
|<span data-ttu-id="afd3e-109">1</span><span class="sxs-lookup"><span data-stu-id="afd3e-109">1</span></span>  <br/> |<span data-ttu-id="afd3e-110">一维</span><span class="sxs-lookup"><span data-stu-id="afd3e-110">1-dimensional</span></span>  <br/> |
|<span data-ttu-id="afd3e-111">2</span><span class="sxs-lookup"><span data-stu-id="afd3e-111">2</span></span>  <br/> |<span data-ttu-id="afd3e-112">二维</span><span class="sxs-lookup"><span data-stu-id="afd3e-112">2-dimensional</span></span>  <br/> |
|<span data-ttu-id="afd3e-113">3</span><span class="sxs-lookup"><span data-stu-id="afd3e-113">3</span></span>  <br/> |<span data-ttu-id="afd3e-114">连接器</span><span class="sxs-lookup"><span data-stu-id="afd3e-114">Connector</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="afd3e-115">说明</span><span class="sxs-lookup"><span data-stu-id="afd3e-115">Remarks</span></span>

<span data-ttu-id="afd3e-116">要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**QuickStyleType**单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="afd3e-116">To get a reference to the **QuickStyleType** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="afd3e-117">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="afd3e-117">Cell name:</span></span>  <br/> | <span data-ttu-id="afd3e-118">QuickStyleType</span><span class="sxs-lookup"><span data-stu-id="afd3e-118">QuickStyleType</span></span>  <br/> |
   
<span data-ttu-id="afd3e-119">若要从某个程序按索引获取对**QuickStyleType**单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="afd3e-119">To get a reference to the **QuickStyleType** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="afd3e-120">内容索引：</span><span class="sxs-lookup"><span data-stu-id="afd3e-120">Section index:</span></span>  <br/> |<span data-ttu-id="afd3e-121">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="afd3e-121">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="afd3e-122">行索引：</span><span class="sxs-lookup"><span data-stu-id="afd3e-122">Row index:</span></span>  <br/> |<span data-ttu-id="afd3e-123">**visRowQuickStyleProperties**</span><span class="sxs-lookup"><span data-stu-id="afd3e-123">**visRowQuickStyleProperties**</span></span> <br/> |
| <span data-ttu-id="afd3e-124">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="afd3e-124">Cell index:</span></span>  <br/> |<span data-ttu-id="afd3e-125">**visQuickStyleType**</span><span class="sxs-lookup"><span data-stu-id="afd3e-125">**visQuickStyleType**</span></span> <br/> |
   

