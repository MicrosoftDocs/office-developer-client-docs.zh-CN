---
title: ShdwOffsetX 单元格（“Page Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251373
localization_priority: Normal
ms.assetid: 92ec9b11-f53f-a1c9-832a-6cac08aa5379
description: 确定形状的投影与该形状水平偏移的距离（按页面单位）。
ms.openlocfilehash: 9aec108146e329d7a8161acc4ca7cdcb19424eff
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781325"
---
# <a name="shdwoffsetx-cell-page-properties-section"></a><span data-ttu-id="5c5b6-103">ShdwOffsetX 单元格（“Page Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="5c5b6-103">ShdwOffsetX Cell (Page Properties Section)</span></span>

<span data-ttu-id="5c5b6-104">确定形状的投影与该形状水平偏移的距离（按页面单位）。</span><span class="sxs-lookup"><span data-stu-id="5c5b6-104">Determines the distance in page units that a shape's drop shadow is offset horizontally from the shape.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="5c5b6-105">注解</span><span class="sxs-lookup"><span data-stu-id="5c5b6-105">Remarks</span></span>

<span data-ttu-id="5c5b6-106">在**页面设置**对话框设置此值 （**设计**选项卡中，单击**页面设置**箭头）。</span><span class="sxs-lookup"><span data-stu-id="5c5b6-106">This value is set in the **Page Setup** dialog box (on the **Design** tab, click the **Page Setup** arrow).</span></span> <span data-ttu-id="5c5b6-107">此值是比例的绘图无关。</span><span class="sxs-lookup"><span data-stu-id="5c5b6-107">This value is independent of the scale of the drawing.</span></span> <span data-ttu-id="5c5b6-108">缩放绘图时，如果阴影偏移量保持不变。</span><span class="sxs-lookup"><span data-stu-id="5c5b6-108">If the drawing is scaled, the shadow offset remains the same.</span></span> 
  
<span data-ttu-id="5c5b6-109">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 ShdwOffsetX 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="5c5b6-109">To get a reference to the ShdwOffsetX cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="5c5b6-110">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="5c5b6-110">Cell name:</span></span>  <br/> | <span data-ttu-id="5c5b6-111">ShdwOffsetX</span><span class="sxs-lookup"><span data-stu-id="5c5b6-111">ShdwOffsetX</span></span>  <br/> |
   
<span data-ttu-id="5c5b6-112">若要从某个程序按索引获取对 ShdwOffsetX 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="5c5b6-112">To get a reference to the ShdwOffsetX cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="5c5b6-113">内容索引：</span><span class="sxs-lookup"><span data-stu-id="5c5b6-113">Section index:</span></span>  <br/> |<span data-ttu-id="5c5b6-114">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="5c5b6-114">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="5c5b6-115">行索引：</span><span class="sxs-lookup"><span data-stu-id="5c5b6-115">Row index:</span></span>  <br/> |<span data-ttu-id="5c5b6-116">**visRowPage**</span><span class="sxs-lookup"><span data-stu-id="5c5b6-116">**visRowPage**</span></span> <br/> |
| <span data-ttu-id="5c5b6-117">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="5c5b6-117">Cell index:</span></span>  <br/> |<span data-ttu-id="5c5b6-118">**visPageShdwOffsetX**</span><span class="sxs-lookup"><span data-stu-id="5c5b6-118">**visPageShdwOffsetX**</span></span> <br/> |
   

