---
title: ShapeShdwOffsetX 单元格（“Fill Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60076
localization_priority: Normal
ms.assetid: a426f471-d35f-ef87-4c59-2c007ec2653f
description: 确定形状的阴影与该形状水平偏移的距离（按页面单位）。
ms.openlocfilehash: 12512ce9edf49f91c786c3cd50baa8d07498a3de
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781298"
---
# <a name="shapeshdwoffsetx-cell-fill-format-section"></a><span data-ttu-id="087cb-103">ShapeShdwOffsetX 单元格（“Fill Format”内容）</span><span class="sxs-lookup"><span data-stu-id="087cb-103">ShapeShdwOffsetX Cell (Fill Format Section)</span></span>

<span data-ttu-id="087cb-104">确定形状的阴影与该形状水平偏移的距离（按页面单位）。</span><span class="sxs-lookup"><span data-stu-id="087cb-104">Determines the distance in page units that a shape's shadow is offset horizontally from the shape.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="087cb-105">注解</span><span class="sxs-lookup"><span data-stu-id="087cb-105">Remarks</span></span>

<span data-ttu-id="087cb-106">此值对应于**阴影**对话框中的**X 偏移**设置中的值 （在**主页**选项卡，**形状**组中，单击**阴影**，然后单击**阴影选项**）。</span><span class="sxs-lookup"><span data-stu-id="087cb-106">This value corresponds to the value in the **X Offset** setting in the **Shadow** dialog box (on the **Home** tab, in the **Shape** group, click **Shadow**, and then click **Shadow Options**).</span></span>
  
<span data-ttu-id="087cb-107">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 ShapeShdwOffsetX 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="087cb-107">To get a reference to the ShapeShdwOffsetX cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="087cb-108">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="087cb-108">Cell name:</span></span>  <br/> | <span data-ttu-id="087cb-109">ShapeShdwOffsetX</span><span class="sxs-lookup"><span data-stu-id="087cb-109">ShapeShdwOffsetX</span></span>  <br/> |
   
<span data-ttu-id="087cb-110">若要从某个程序按索引获取对 ShapeShdwOffsetX 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="087cb-110">To get a reference to the ShapeShdwOffsetX cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="087cb-111">内容索引：</span><span class="sxs-lookup"><span data-stu-id="087cb-111">Section index:</span></span>  <br/> |<span data-ttu-id="087cb-112">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="087cb-112">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="087cb-113">行索引：</span><span class="sxs-lookup"><span data-stu-id="087cb-113">Row index:</span></span>  <br/> |<span data-ttu-id="087cb-114">**visRowFill**</span><span class="sxs-lookup"><span data-stu-id="087cb-114">**visRowFill**</span></span> <br/> |
| <span data-ttu-id="087cb-115">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="087cb-115">Cell index:</span></span>  <br/> |<span data-ttu-id="087cb-116">**visFillShdwOffsetX**</span><span class="sxs-lookup"><span data-stu-id="087cb-116">**visFillShdwOffsetX**</span></span> <br/> |
   

