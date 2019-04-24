---
title: ClippingPath 单元格 ("外部图像信息" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 0ec70417-5b23-45af-95a0-1b26f6791699
description: 包含对图像所绑定的路径的几何图形的引用。
ms.openlocfilehash: cfbbb3ca7294f751f088df7c3284bf6461270af7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341858"
---
# <a name="clippingpath-cell-foreign-image-info-section"></a><span data-ttu-id="e39ed-103">ClippingPath 单元格 ("外部图像信息" 部分)</span><span class="sxs-lookup"><span data-stu-id="e39ed-103">ClippingPath Cell (Foreign Image Info Section)</span></span>

<span data-ttu-id="e39ed-104">包含对图像所绑定的路径的几何图形的引用。</span><span class="sxs-lookup"><span data-stu-id="e39ed-104">Contains a reference to the geometry of the path that an image is bounded by.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="e39ed-105">注解</span><span class="sxs-lookup"><span data-stu-id="e39ed-105">Remarks</span></span>

<span data-ttu-id="e39ed-106">如果**ClippingPath**单元格指向有效的路径, 则会对图像进行剪切, 以便在路径中呈现图像。</span><span class="sxs-lookup"><span data-stu-id="e39ed-106">If the **ClippingPath** cell points to a valid path, the image is clipped so that the image is rendered inside of the path.</span></span> <span data-ttu-id="e39ed-107">如果**ClippingPath**单元格为空或包含无效的条目, 则将使用 "缩放" 和 "偏移" 值来呈现图像和矩形剪辑。</span><span class="sxs-lookup"><span data-stu-id="e39ed-107">If the **ClippingPath** cell is empty or contains an invalid entry, then the image will be rendered with a rectangular clip, using the scale and offset values.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="e39ed-108">仅由图像 ShapeSheet 中的 " [Geometry](geometry-section.md) " 内容定义的路径是**ClippingPath**单元格的有效输入项。</span><span class="sxs-lookup"><span data-stu-id="e39ed-108">Only paths defined by a [Geometry](geometry-section.md) section in the image's ShapeSheet are valid entries for the **ClippingPath** cell.</span></span> <span data-ttu-id="e39ed-109">跨工作表引用不能用于定义图像剪切路径。</span><span class="sxs-lookup"><span data-stu-id="e39ed-109">Cross-sheet references cannot be used to define an image clipping path.</span></span> 
  
<span data-ttu-id="e39ed-110">若要从另一个公式按名称获取对**ClippingPath**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用:</span><span class="sxs-lookup"><span data-stu-id="e39ed-110">To get a reference to the **ClippingPath** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="e39ed-111">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="e39ed-111">Cell name:</span></span>  <br/> | <span data-ttu-id="e39ed-112">ClippingPath</span><span class="sxs-lookup"><span data-stu-id="e39ed-112">ClippingPath</span></span>  <br/> |
   
<span data-ttu-id="e39ed-113">若要从某个程序按索引获取对**ClippingPath**单元格的引用, 请使用带下列参数的**CellsSRC**属性:</span><span class="sxs-lookup"><span data-stu-id="e39ed-113">To get a reference to the **ClippingPath** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="e39ed-114">内容索引：</span><span class="sxs-lookup"><span data-stu-id="e39ed-114">Section index:</span></span>  <br/> |<span data-ttu-id="e39ed-115">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="e39ed-115">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="e39ed-116">行索引：</span><span class="sxs-lookup"><span data-stu-id="e39ed-116">Row index:</span></span>  <br/> |<span data-ttu-id="e39ed-117">**visRowForeign**</span><span class="sxs-lookup"><span data-stu-id="e39ed-117">**visRowForeign**</span></span> <br/> |
| <span data-ttu-id="e39ed-118">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="e39ed-118">Cell index:</span></span>  <br/> |<span data-ttu-id="e39ed-119">**visFrgnImgClippingPath**</span><span class="sxs-lookup"><span data-stu-id="e39ed-119">**visFrgnImgClippingPath**</span></span> <br/> |
   
## <a name="example"></a><span data-ttu-id="e39ed-120">示例</span><span class="sxs-lookup"><span data-stu-id="e39ed-120">Example</span></span>

<span data-ttu-id="e39ed-121">您可以通过执行以下操作, 将图像的边框形状更改为椭圆:</span><span class="sxs-lookup"><span data-stu-id="e39ed-121">You can change the bounding shape of an image to an oval by doing the following:</span></span>
  
- <span data-ttu-id="e39ed-122">将图片插入绘图画布上。</span><span class="sxs-lookup"><span data-stu-id="e39ed-122">Insert the picture onto the drawing canvas.</span></span>
    
- <span data-ttu-id="e39ed-123">右键单击图片, 然后选择 "**显示 ShapeSheet**"。</span><span class="sxs-lookup"><span data-stu-id="e39ed-123">Right-click the picture and then select **Show ShapeSheet**.</span></span>
    
- <span data-ttu-id="e39ed-124">右键单击 ShapeSheet 中的任意位置, 然后选择 "**插入节**"。</span><span class="sxs-lookup"><span data-stu-id="e39ed-124">Right-click anywhere in the ShapeSheet and select **Insert Section**.</span></span>
    
- <span data-ttu-id="e39ed-125">在 "**插入内容**" 对话框中, 选择 "**几何图形**", 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="e39ed-125">In the **Insert Section** dialog box, select **Geometry** and then click **OK**.</span></span>
    
- <span data-ttu-id="e39ed-126">在 "新建几何图形" 部分 (例如 "Geometry2") 中, 删除除一行之外的所有行。</span><span class="sxs-lookup"><span data-stu-id="e39ed-126">In the new Geometry section (e.g. "Geometry2"), delete all but one row.</span></span>
    
- <span data-ttu-id="e39ed-127">右键单击其余的行, 然后单击 "**更改行类型**"。</span><span class="sxs-lookup"><span data-stu-id="e39ed-127">Right-click the remaining row and then click **Change Row Type**.</span></span>
    
- <span data-ttu-id="e39ed-128">在 "**更改行类型**" 对话框中, 选择 "**椭圆形**", 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="e39ed-128">In the **Change Row Type** dialog box, select **Ellipse** and then click **OK**.</span></span>
    
- <span data-ttu-id="e39ed-129">在 "**外部图像**" 部分, 将 " **ClippingPath** " 单元格的`="Geometry2.Path"`公式设置为, 然后接受该公式。</span><span class="sxs-lookup"><span data-stu-id="e39ed-129">In the **Foreign Image** section, set the formula for the **ClippingPath** cell to  `="Geometry2.Path"` and then accept the formula.</span></span> 
    

