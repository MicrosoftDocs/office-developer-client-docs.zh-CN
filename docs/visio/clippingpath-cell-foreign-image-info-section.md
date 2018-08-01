---
title: ClippingPath 单元格（“Foreign Image Info”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 0ec70417-5b23-45af-95a0-1b26f6791699
description: 包含引用的绑定图像的路径。
ms.openlocfilehash: 9f1c159e303c1d7bc3467c36756a422a3f325c7b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779877"
---
# <a name="clippingpath-cell-foreign-image-info-section"></a><span data-ttu-id="465a6-103">ClippingPath 单元格（“Foreign Image Info”部分）</span><span class="sxs-lookup"><span data-stu-id="465a6-103">ClippingPath Cell (Foreign Image Info Section)</span></span>

<span data-ttu-id="465a6-104">包含引用的绑定图像的路径。</span><span class="sxs-lookup"><span data-stu-id="465a6-104">Contains a reference to the geometry of the path that an image is bounded by.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="465a6-105">说明</span><span class="sxs-lookup"><span data-stu-id="465a6-105">Remarks</span></span>

<span data-ttu-id="465a6-106">如果**ClippingPath**单元格指向的有效路径，则剪裁图像，以便在路径呈现图像。</span><span class="sxs-lookup"><span data-stu-id="465a6-106">If the **ClippingPath** cell points to a valid path, the image is clipped so that the image is rendered inside of the path.</span></span> <span data-ttu-id="465a6-107">如果**ClippingPath**单元格为空或包含无效输入，然后将矩形剪辑，使用范围和偏移值呈现图像。</span><span class="sxs-lookup"><span data-stu-id="465a6-107">If the **ClippingPath** cell is empty or contains an invalid entry, then the image will be rendered with a rectangular clip, using the scale and offset values.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="465a6-108">仅由[geometry](geometry-section.md)内容的图像的 ShapeSheet 中定义的路径是**ClippingPath**单元格的有效条目。</span><span class="sxs-lookup"><span data-stu-id="465a6-108">Only paths defined by a [Geometry](geometry-section.md) section in the image's ShapeSheet are valid entries for the **ClippingPath** cell.</span></span> <span data-ttu-id="465a6-109">跨工作表引用不能用于定义图像剪辑路径。</span><span class="sxs-lookup"><span data-stu-id="465a6-109">Cross-sheet references cannot be used to define an image clipping path.</span></span> 
  
<span data-ttu-id="465a6-110">要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**ClippingPath**单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="465a6-110">To get a reference to the **ClippingPath** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="465a6-111">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="465a6-111">Cell name:</span></span>  <br/> | <span data-ttu-id="465a6-112">ClippingPath</span><span class="sxs-lookup"><span data-stu-id="465a6-112">ClippingPath</span></span>  <br/> |
   
<span data-ttu-id="465a6-113">若要从某个程序按索引获取对**ClippingPath**单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="465a6-113">To get a reference to the **ClippingPath** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="465a6-114">内容索引：</span><span class="sxs-lookup"><span data-stu-id="465a6-114">Section index:</span></span>  <br/> |<span data-ttu-id="465a6-115">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="465a6-115">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="465a6-116">行索引：</span><span class="sxs-lookup"><span data-stu-id="465a6-116">Row index:</span></span>  <br/> |<span data-ttu-id="465a6-117">**visRowForeign**</span><span class="sxs-lookup"><span data-stu-id="465a6-117">**visRowForeign**</span></span> <br/> |
| <span data-ttu-id="465a6-118">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="465a6-118">Cell index:</span></span>  <br/> |<span data-ttu-id="465a6-119">**visFrgnImgClippingPath**</span><span class="sxs-lookup"><span data-stu-id="465a6-119">**visFrgnImgClippingPath**</span></span> <br/> |
   
## <a name="example"></a><span data-ttu-id="465a6-120">示例</span><span class="sxs-lookup"><span data-stu-id="465a6-120">Example</span></span>

<span data-ttu-id="465a6-121">可以通过执行以下操作来更改为一个椭圆图像的边框形状的：</span><span class="sxs-lookup"><span data-stu-id="465a6-121">You can change the bounding shape of an image to an oval by doing the following:</span></span>
  
- <span data-ttu-id="465a6-122">插入到绘图画布上的图片。</span><span class="sxs-lookup"><span data-stu-id="465a6-122">Insert the picture onto the drawing canvas.</span></span>
    
- <span data-ttu-id="465a6-123">右键单击该图片，然后选择**显示 ShapeSheet**。</span><span class="sxs-lookup"><span data-stu-id="465a6-123">Right-click the picture and then select **Show ShapeSheet**.</span></span>
    
- <span data-ttu-id="465a6-124">ShapeSheet 中的任意位置单击右键，然后选择**插入节**。</span><span class="sxs-lookup"><span data-stu-id="465a6-124">Right-click anywhere in the ShapeSheet and select **Insert Section**.</span></span>
    
- <span data-ttu-id="465a6-125">**插入节**对话框中，选择**geometry** ，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="465a6-125">In the **Insert Section** dialog box, select **Geometry** and then click **OK**.</span></span>
    
- <span data-ttu-id="465a6-126">在新的 geometry 内容 (例如"Geometry2") 中，删除所有但一个行。</span><span class="sxs-lookup"><span data-stu-id="465a6-126">In the new Geometry section (e.g. "Geometry2"), delete all but one row.</span></span>
    
- <span data-ttu-id="465a6-127">右键单击的剩余行，然后单击**更改行类型**。</span><span class="sxs-lookup"><span data-stu-id="465a6-127">Right-click the remaining row and then click **Change Row Type**.</span></span>
    
- <span data-ttu-id="465a6-128">**更改行类型**对话框中，选择**椭圆**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="465a6-128">In the **Change Row Type** dialog box, select **Ellipse** and then click **OK**.</span></span>
    
- <span data-ttu-id="465a6-129">在**Foreign Image**部分中，将设置为**ClippingPath**单元格的公式`="Geometry2.Path"`，然后接受公式。</span><span class="sxs-lookup"><span data-stu-id="465a6-129">In the **Foreign Image** section, set the formula for the **ClippingPath** cell to  `="Geometry2.Path"` and then accept the formula.</span></span> 
    

