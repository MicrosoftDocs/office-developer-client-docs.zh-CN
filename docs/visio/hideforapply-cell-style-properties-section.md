---
title: HideForApply 单元格（“Style Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251698
localization_priority: Normal
ms.assetid: 62d87db9-b8ca-60b6-bf27-5168c718ec96
description: 确定其中 Microsoft Visio 用户界面中显示样式。
ms.openlocfilehash: 5b0221c54c17a3b9957cce5e890842def0ba7525
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780410"
---
# <a name="hideforapply-cell-style-properties-section"></a><span data-ttu-id="17376-103">HideForApply 单元格（“Style Properties”部分）</span><span class="sxs-lookup"><span data-stu-id="17376-103">HideForApply Cell (Style Properties Section)</span></span>

<span data-ttu-id="17376-104">确定其中 Microsoft Visio 用户界面中显示样式。</span><span class="sxs-lookup"><span data-stu-id="17376-104">Determines where a style is shown in the Microsoft Visio user interface.</span></span>
  
|<span data-ttu-id="17376-105">**值**</span><span class="sxs-lookup"><span data-stu-id="17376-105">**Value**</span></span>|<span data-ttu-id="17376-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="17376-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="17376-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="17376-107">TRUE</span></span>  <br/> | <span data-ttu-id="17376-108">
          仅在 **“绘图资源管理器”** 中显示样式。
</span><span class="sxs-lookup"><span data-stu-id="17376-108">Show the style only in the **Drawing Explorer**.</span></span>  <br/> |
| <span data-ttu-id="17376-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="17376-109">FALSE</span></span>  <br/> | <span data-ttu-id="17376-110">
          在 **“绘图资源管理器”** 中显示样式。
</span><span class="sxs-lookup"><span data-stu-id="17376-110">Show the style in the **Drawing Explorer**.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="17376-111">注解</span><span class="sxs-lookup"><span data-stu-id="17376-111">Remarks</span></span>

<span data-ttu-id="17376-112">如果您基于某个隐藏的样式创建新样式，则新样式并不会继承此属性。</span><span class="sxs-lookup"><span data-stu-id="17376-112">When you base a new style on a style that is hidden, the new style does not inherit this attribute.</span></span>
  
<span data-ttu-id="17376-113">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 HideForApply 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="17376-113">To get a reference to the HideForApply cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="17376-114">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="17376-114">Cell name:</span></span>  <br/> | <span data-ttu-id="17376-115">HideForApply</span><span class="sxs-lookup"><span data-stu-id="17376-115">HideForApply</span></span>  <br/> |
   
<span data-ttu-id="17376-116">若要从某个程序按索引获取对 HideForApply 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="17376-116">To get a reference to the HideForApply cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="17376-117">内容索引：</span><span class="sxs-lookup"><span data-stu-id="17376-117">Section index:</span></span>  <br/> |<span data-ttu-id="17376-118">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="17376-118">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="17376-119">行索引：</span><span class="sxs-lookup"><span data-stu-id="17376-119">Row index:</span></span>  <br/> |<span data-ttu-id="17376-120">**visRowStyle**</span><span class="sxs-lookup"><span data-stu-id="17376-120">**visRowStyle**</span></span> <br/> |
| <span data-ttu-id="17376-121">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="17376-121">Cell index:</span></span>  <br/> |<span data-ttu-id="17376-122">**visStyleHidden**</span><span class="sxs-lookup"><span data-stu-id="17376-122">**visStyleHidden**</span></span> <br/> |
   

