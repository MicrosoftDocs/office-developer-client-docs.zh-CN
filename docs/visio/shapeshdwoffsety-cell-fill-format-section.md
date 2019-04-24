---
title: ShapeShdwOffsetY 单元格（“Fill Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60077
localization_priority: Normal
ms.assetid: ef200f41-7b69-1291-f9df-a7035239a033
description: 确定形状的阴影与该形状垂直偏移的距离（按页面单位）。
ms.openlocfilehash: 4ae4347ba9009e88bbd181d4dd6e242e1fad53be
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32349138"
---
# <a name="shapeshdwoffsety-cell-fill-format-section"></a><span data-ttu-id="58dab-103">ShapeShdwOffsetY 单元格（“Fill Format”内容）</span><span class="sxs-lookup"><span data-stu-id="58dab-103">ShapeShdwOffsetY Cell (Fill Format Section)</span></span>

<span data-ttu-id="58dab-104">确定形状的阴影与该形状垂直偏移的距离（按页面单位）。</span><span class="sxs-lookup"><span data-stu-id="58dab-104">Determines the distance in page units that a shape's shadow is offset vertically from the shape.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="58dab-105">注解</span><span class="sxs-lookup"><span data-stu-id="58dab-105">Remarks</span></span>

<span data-ttu-id="58dab-106">此值对应于 **“阴影”** 对话框（在 **“开始”** 选项卡上的 **“形状”** 组中，单击 **“阴影”**，然后单击 **“阴影选项”**）中的 **“Y 轴偏移”** 设置中的值。</span><span class="sxs-lookup"><span data-stu-id="58dab-106">This value corresponds to the value in the **Y Offset** setting in the **Shadow** dialog box (on the **Home** tab, in the **Shape** group, click **Shadow**, and then click **Shadow Options**).</span></span>
  
<span data-ttu-id="58dab-107">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ShapeShdwOffsetY 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="58dab-107">To get a reference to the ShapeShdwOffsetY cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="58dab-108">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="58dab-108">Cell name:</span></span>  <br/> | <span data-ttu-id="58dab-109">ShapeShdwOffsetY</span><span class="sxs-lookup"><span data-stu-id="58dab-109">ShapeShdwOffsetY</span></span>  <br/> |
   
<span data-ttu-id="58dab-110">若要从某个程序按索引获取对 ShapeShdwOffsetY 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="58dab-110">To get a reference to the ShapeShdwOffsetY cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="58dab-111">内容索引：</span><span class="sxs-lookup"><span data-stu-id="58dab-111">Section index:</span></span>  <br/> |<span data-ttu-id="58dab-112">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="58dab-112">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="58dab-113">行索引：</span><span class="sxs-lookup"><span data-stu-id="58dab-113">Row index:</span></span>  <br/> |<span data-ttu-id="58dab-114">**visRowFill**</span><span class="sxs-lookup"><span data-stu-id="58dab-114">**visRowFill**</span></span> <br/> |
| <span data-ttu-id="58dab-115">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="58dab-115">Cell index:</span></span>  <br/> |<span data-ttu-id="58dab-116">**visFillShdwOffsetY**</span><span class="sxs-lookup"><span data-stu-id="58dab-116">**visFillShdwOffsetY**</span></span> <br/> |
   

