---
title: 'ClippingPath Cell (Foreign Image Info Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 0ec70417-5b23-45af-95a0-1b26f6791699
description: 包含对图像所绑定路径的几何图形的引用。
ms.openlocfilehash: cfbbb3ca7294f751f088df7c3284bf6461270af7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425510"
---
# <a name="clippingpath-cell-foreign-image-info-section"></a><span data-ttu-id="79f06-103">ClippingPath Cell (Foreign Image Info Section) </span><span class="sxs-lookup"><span data-stu-id="79f06-103">ClippingPath Cell (Foreign Image Info Section)</span></span>

<span data-ttu-id="79f06-104">包含对图像所绑定路径的几何图形的引用。</span><span class="sxs-lookup"><span data-stu-id="79f06-104">Contains a reference to the geometry of the path that an image is bounded by.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="79f06-105">备注</span><span class="sxs-lookup"><span data-stu-id="79f06-105">Remarks</span></span>

<span data-ttu-id="79f06-106">如果 **ClippingPath** 单元格指向有效的路径，则剪裁图像，以便图像在路径内呈现。</span><span class="sxs-lookup"><span data-stu-id="79f06-106">If the **ClippingPath** cell points to a valid path, the image is clipped so that the image is rendered inside of the path.</span></span> <span data-ttu-id="79f06-107">如果 **ClippingPath** 单元格为空或包含无效条目，则图像将采用矩形剪辑呈现，使用比例和偏移值。</span><span class="sxs-lookup"><span data-stu-id="79f06-107">If the **ClippingPath** cell is empty or contains an invalid entry, then the image will be rendered with a rectangular clip, using the scale and offset values.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="79f06-108">只有图像 [ShapeSheet 中的"Geometry"](geometry-section.md) 内容定义的路径是 **ClippingPath** 单元格的有效条目。</span><span class="sxs-lookup"><span data-stu-id="79f06-108">Only paths defined by a [Geometry](geometry-section.md) section in the image's ShapeSheet are valid entries for the **ClippingPath** cell.</span></span> <span data-ttu-id="79f06-109">跨工作表引用不能用于定义图像剪辑路径。</span><span class="sxs-lookup"><span data-stu-id="79f06-109">Cross-sheet references cannot be used to define an image clipping path.</span></span> 
  
<span data-ttu-id="79f06-110">若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 CellsU 属性从某个程序按名称获取对 **ClippingPath** 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="79f06-110">To get a reference to the **ClippingPath** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="79f06-111">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="79f06-111">Cell name:</span></span>  <br/> | <span data-ttu-id="79f06-112">ClippingPath</span><span class="sxs-lookup"><span data-stu-id="79f06-112">ClippingPath</span></span>  <br/> |
   
<span data-ttu-id="79f06-113">若要从程序按索引获取对 **ClippingPath** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="79f06-113">To get a reference to the **ClippingPath** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="79f06-114">内容索引：</span><span class="sxs-lookup"><span data-stu-id="79f06-114">Section index:</span></span>  <br/> |<span data-ttu-id="79f06-115">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="79f06-115">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="79f06-116">行索引：</span><span class="sxs-lookup"><span data-stu-id="79f06-116">Row index:</span></span>  <br/> |<span data-ttu-id="79f06-117">**visRowForeign**</span><span class="sxs-lookup"><span data-stu-id="79f06-117">**visRowForeign**</span></span> <br/> |
| <span data-ttu-id="79f06-118">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="79f06-118">Cell index:</span></span>  <br/> |<span data-ttu-id="79f06-119">**visFrgnImgClippingPath**</span><span class="sxs-lookup"><span data-stu-id="79f06-119">**visFrgnImgClippingPath**</span></span> <br/> |
   
## <a name="example"></a><span data-ttu-id="79f06-120">示例</span><span class="sxs-lookup"><span data-stu-id="79f06-120">Example</span></span>

<span data-ttu-id="79f06-121">可以通过执行以下操作将图像边界形状更改为椭圆：</span><span class="sxs-lookup"><span data-stu-id="79f06-121">You can change the bounding shape of an image to an oval by doing the following:</span></span>
  
- <span data-ttu-id="79f06-122">将图片插入到绘图画布上。</span><span class="sxs-lookup"><span data-stu-id="79f06-122">Insert the picture onto the drawing canvas.</span></span>
    
- <span data-ttu-id="79f06-123">右键单击图片，然后选择"显示 **ShapeSheet"。**</span><span class="sxs-lookup"><span data-stu-id="79f06-123">Right-click the picture and then select **Show ShapeSheet**.</span></span>
    
- <span data-ttu-id="79f06-124">右键单击 ShapeSheet 中的任何位置，然后选择"**插入内容"。**</span><span class="sxs-lookup"><span data-stu-id="79f06-124">Right-click anywhere in the ShapeSheet and select **Insert Section**.</span></span>
    
- <span data-ttu-id="79f06-125">在"**插入内容"** 对话框中，选择 **"几何图形**"，然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="79f06-125">In the **Insert Section** dialog box, select **Geometry** and then click **OK**.</span></span>
    
- <span data-ttu-id="79f06-126">在"新建几何图形" ("Geometry2") 删除除一行外的所有行。</span><span class="sxs-lookup"><span data-stu-id="79f06-126">In the new Geometry section (e.g. "Geometry2"), delete all but one row.</span></span>
    
- <span data-ttu-id="79f06-127">右键单击其余行，然后单击"**更改行类型"。**</span><span class="sxs-lookup"><span data-stu-id="79f06-127">Right-click the remaining row and then click **Change Row Type**.</span></span>
    
- <span data-ttu-id="79f06-128">在"**更改行类型**"对话框中，选择 **"Ellipse"，** 然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="79f06-128">In the **Change Row Type** dialog box, select **Ellipse** and then click **OK**.</span></span>
    
- <span data-ttu-id="79f06-129">在 **"Foreign Image"** 内容中，将 **ClippingPath** 单元格的公式设置为  `="Geometry2.Path"` ，然后接受该公式。</span><span class="sxs-lookup"><span data-stu-id="79f06-129">In the **Foreign Image** section, set the formula for the **ClippingPath** cell to  `="Geometry2.Path"` and then accept the formula.</span></span> 
    

