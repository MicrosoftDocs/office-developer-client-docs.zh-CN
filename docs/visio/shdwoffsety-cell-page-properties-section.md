---
title: ShdwOffsetY 单元格（“Page Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm930
localization_priority: Normal
ms.assetid: f3f53a7d-7450-b2b0-b508-6044a87450d9
description: 确定形状的投影与该形状垂直偏移的距离（按页面单位）。
ms.openlocfilehash: 0228fef00230dd1517d20067fda855225cef5533
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781342"
---
# <a name="shdwoffsety-cell-page-properties-section"></a><span data-ttu-id="ec779-103">ShdwOffsetY 单元格（“Page Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="ec779-103">ShdwOffsetY Cell (Page Properties Section)</span></span>

<span data-ttu-id="ec779-104">确定形状的投影与该形状垂直偏移的距离（按页面单位）。</span><span class="sxs-lookup"><span data-stu-id="ec779-104">Determines the distance in page units that a shape's drop shadow is offset vertically from the shape.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="ec779-105">注解</span><span class="sxs-lookup"><span data-stu-id="ec779-105">Remarks</span></span>

<span data-ttu-id="ec779-106">在**页面设置**对话框设置此值 （**设计**选项卡中，单击**页面设置**箭头）。</span><span class="sxs-lookup"><span data-stu-id="ec779-106">This value is set in the **Page Setup** dialog box (on the **Design** tab, click the **Page Setup** arrow).</span></span> <span data-ttu-id="ec779-107">此值是比例的绘图无关。</span><span class="sxs-lookup"><span data-stu-id="ec779-107">This value is independent of the scale of the drawing.</span></span> <span data-ttu-id="ec779-108">缩放绘图时，如果阴影偏移量保持不变。</span><span class="sxs-lookup"><span data-stu-id="ec779-108">If the drawing is scaled, the shadow offset remains the same.</span></span> 
  
<span data-ttu-id="ec779-109">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 ShdwOffsetY 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="ec779-109">To get a reference to the ShdwOffsetY cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="ec779-110">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="ec779-110">Cell name:</span></span>  <br/> | <span data-ttu-id="ec779-111">ShdwOffsetY</span><span class="sxs-lookup"><span data-stu-id="ec779-111">ShdwOffsetY</span></span>  <br/> |
   
<span data-ttu-id="ec779-112">若要从某个程序按索引获取对 ShdwOffsetY 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="ec779-112">To get a reference to the ShdwOffsetY cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="ec779-113">内容索引：</span><span class="sxs-lookup"><span data-stu-id="ec779-113">Section index:</span></span>  <br/> |<span data-ttu-id="ec779-114">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="ec779-114">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="ec779-115">行索引：</span><span class="sxs-lookup"><span data-stu-id="ec779-115">Row index:</span></span>  <br/> |<span data-ttu-id="ec779-116">**visRowPage**</span><span class="sxs-lookup"><span data-stu-id="ec779-116">**visRowPage**</span></span> <br/> |
| <span data-ttu-id="ec779-117">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="ec779-117">Cell index:</span></span>  <br/> |<span data-ttu-id="ec779-118">**visPageShdwOffsetY**</span><span class="sxs-lookup"><span data-stu-id="ec779-118">**visPageShdwOffsetY**</span></span> <br/> |
   

