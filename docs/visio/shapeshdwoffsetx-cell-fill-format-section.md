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
ms.openlocfilehash: 5c3f994f0ceba84c86585a76c7a67667a0c20a53
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426483"
---
# <a name="shapeshdwoffsetx-cell-fill-format-section"></a><span data-ttu-id="03ecd-103">ShapeShdwOffsetX 单元格（“Fill Format”内容）</span><span class="sxs-lookup"><span data-stu-id="03ecd-103">ShapeShdwOffsetX Cell (Fill Format Section)</span></span>

<span data-ttu-id="03ecd-104">确定形状的阴影与该形状水平偏移的距离（按页面单位）。</span><span class="sxs-lookup"><span data-stu-id="03ecd-104">Determines the distance in page units that a shape's shadow is offset horizontally from the shape.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="03ecd-105">说明</span><span class="sxs-lookup"><span data-stu-id="03ecd-105">Remarks</span></span>

<span data-ttu-id="03ecd-106">此值对应于 **“阴影”** 对话框（在 **“开始”** 选项卡上的 **“形状”** 组中，单击 **“阴影”**，然后单击 **“阴影选项”**）中的 **“X 轴偏移”** 设置中的值。</span><span class="sxs-lookup"><span data-stu-id="03ecd-106">This value corresponds to the value in the **X Offset** setting in the **Shadow** dialog box (on the **Home** tab, in the **Shape** group, click **Shadow**, and then click **Shadow Options**).</span></span>
  
<span data-ttu-id="03ecd-107">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ShapeShdwOffsetX 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="03ecd-107">To get a reference to the ShapeShdwOffsetX cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="03ecd-108">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="03ecd-108">Cell name:</span></span>  <br/> | <span data-ttu-id="03ecd-109">ShapeShdwOffsetX</span><span class="sxs-lookup"><span data-stu-id="03ecd-109">ShapeShdwOffsetX</span></span>  <br/> |
   
<span data-ttu-id="03ecd-110">若要从某个程序按索引获取对 ShapeShdwOffsetX 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="03ecd-110">To get a reference to the ShapeShdwOffsetX cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="03ecd-111">内容索引：</span><span class="sxs-lookup"><span data-stu-id="03ecd-111">Section index:</span></span>  <br/> |<span data-ttu-id="03ecd-112">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="03ecd-112">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="03ecd-113">行索引：</span><span class="sxs-lookup"><span data-stu-id="03ecd-113">Row index:</span></span>  <br/> |<span data-ttu-id="03ecd-114">**visRowFill**</span><span class="sxs-lookup"><span data-stu-id="03ecd-114">**visRowFill**</span></span> <br/> |
| <span data-ttu-id="03ecd-115">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="03ecd-115">Cell index:</span></span>  <br/> |<span data-ttu-id="03ecd-116">**visFillShdwOffsetX**</span><span class="sxs-lookup"><span data-stu-id="03ecd-116">**visFillShdwOffsetX**</span></span> <br/> |
   

