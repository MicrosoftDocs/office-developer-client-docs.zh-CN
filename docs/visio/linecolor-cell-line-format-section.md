---
title: LineColor 单元格（“Line Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm535
localization_priority: Normal
ms.assetid: d857b48b-9a3d-a1e1-5ad2-6816a492c8ab
description: 确定形状的线条颜色。
ms.openlocfilehash: 6086a45108b88475e250c4d833ab4b740f33b8e7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780574"
---
# <a name="linecolor-cell-line-format-section"></a><span data-ttu-id="8a211-103">LineColor 单元格（“Line Format”内容）</span><span class="sxs-lookup"><span data-stu-id="8a211-103">LineColor Cell (Line Format Section)</span></span>

<span data-ttu-id="8a211-104">确定形状的线条颜色。</span><span class="sxs-lookup"><span data-stu-id="8a211-104">Determines the line color of the shape.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="8a211-105">注解</span><span class="sxs-lookup"><span data-stu-id="8a211-105">Remarks</span></span>

<span data-ttu-id="8a211-106">要设置的线条颜色，请输入介于 0 到 23 数字，这是集合中的线条颜色的索引。</span><span class="sxs-lookup"><span data-stu-id="8a211-106">To set the line color, enter a number from 0 to 23, which is an index into a collection of line colors.</span></span> <span data-ttu-id="8a211-107">在**线条**对话框中，可以查看线条颜色集合 （在**主页**选项卡，**形状**组中，单击**线条**，指向**权重**，，然后单击**多行**）。</span><span class="sxs-lookup"><span data-stu-id="8a211-107">You can view the line color collection in the **Line** dialog box (on the **Home** tab, in the **Shape** group, click **Line**, point to **Weight**, and then click **More Lines**).</span></span> <span data-ttu-id="8a211-108">您还可以在**线条**对话框来设置线条颜色的值。</span><span class="sxs-lookup"><span data-stu-id="8a211-108">You can also set the value of LineColor in the **Line** dialog box.</span></span> 
  
<span data-ttu-id="8a211-109">若要输入自定义颜色，使用 RGB 或 HSL 函数。</span><span class="sxs-lookup"><span data-stu-id="8a211-109">To enter a custom color, use the RGB or HSL function.</span></span> <span data-ttu-id="8a211-110">自定义颜色的值为 RGB 颜色，并且 RGB （ *r、 g、 b*），而不是一个号码，将显示在 ShapeSheet 窗口中。</span><span class="sxs-lookup"><span data-stu-id="8a211-110">The value of a custom color is its RGB color, and RGB( *r, g, b*), rather than a number, will be shown in the ShapeSheet window.</span></span> <span data-ttu-id="8a211-111">当使用中的数字运算，自定义颜色具有值将大于或等于，共 24 部分。</span><span class="sxs-lookup"><span data-stu-id="8a211-111">When used in numeric operations, custom colors have values of 24 and above.</span></span> 
  
<span data-ttu-id="8a211-112">您可以在 LineColorTrans 单元格中设置线条颜色的透明度。</span><span class="sxs-lookup"><span data-stu-id="8a211-112">You can set the transparency of the line color in the LineColorTrans cell.</span></span>
  
<span data-ttu-id="8a211-113">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 LineColor 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="8a211-113">To get a reference to the LineColor cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="8a211-114">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="8a211-114">Cell name:</span></span>  <br/> |<span data-ttu-id="8a211-115">LineColor</span><span class="sxs-lookup"><span data-stu-id="8a211-115">LineColor</span></span>  <br/> |
   
<span data-ttu-id="8a211-116">若要从某个程序按索引获取对 LineColor 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="8a211-116">To get a reference to the LineColor cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="8a211-117">内容索引：</span><span class="sxs-lookup"><span data-stu-id="8a211-117">Section index:</span></span>  <br/> |<span data-ttu-id="8a211-118">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="8a211-118">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="8a211-119">行索引：</span><span class="sxs-lookup"><span data-stu-id="8a211-119">Row index:</span></span>  <br/> |<span data-ttu-id="8a211-120">**visRowLine**</span><span class="sxs-lookup"><span data-stu-id="8a211-120">**visRowLine**</span></span> <br/> |
|<span data-ttu-id="8a211-121">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="8a211-121">Cell index:</span></span>  <br/> |<span data-ttu-id="8a211-122">**visLineColor**</span><span class="sxs-lookup"><span data-stu-id="8a211-122">**visLineColor**</span></span> <br/> |
   

