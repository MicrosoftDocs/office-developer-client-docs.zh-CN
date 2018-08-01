---
title: Connection Points 行（“Connection Points”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm3005
localization_priority: Normal
ms.assetid: eaac62a5-f516-9b81-587a-8e0e02de59ee
description: 包含 x 和 y-坐标、 水平和垂直方向和指向形状上一次连接的类型。 从形状的原点的测量连接点的坐标。 形状包含每个连接点的一个 Connection Points 行。
ms.openlocfilehash: f1b8daf7f9845b85e76020c7f89c8c42b4500823
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779962"
---
# <a name="connection-points-row-connection-points-section"></a><span data-ttu-id="cff90-105">Connection Points 行（“Connection Points”部分）</span><span class="sxs-lookup"><span data-stu-id="cff90-105">Connection Points Row (Connection Points Section)</span></span>

<span data-ttu-id="cff90-106">包含*x*和*y* -坐标、 水平和垂直方向和指向形状上一次连接的类型。</span><span class="sxs-lookup"><span data-stu-id="cff90-106">Contains the  *x*  - and  *y*  -coordinates, horizontal and vertical direction, and type for a single connection point on a shape.</span></span> <span data-ttu-id="cff90-107">从形状的原点的测量连接点的坐标。</span><span class="sxs-lookup"><span data-stu-id="cff90-107">Coordinates of connection points are measured from the origin of the shape.</span></span> <span data-ttu-id="cff90-108">形状包含每个连接点的一个 Connection Points 行。</span><span class="sxs-lookup"><span data-stu-id="cff90-108">A shape contains one Connection Points row for each connection point.</span></span> 
  
<span data-ttu-id="cff90-109">如果命名 Connection Points 行，这些名称显示为连接。</span><span class="sxs-lookup"><span data-stu-id="cff90-109">If Connection Points rows are named, those names appear as Connections.</span></span> <span data-ttu-id="cff90-110">在 ShapeSheet 窗口中的*名称*。</span><span class="sxs-lookup"><span data-stu-id="cff90-110">*name*  in the ShapeSheet window.</span></span> <span data-ttu-id="cff90-111">Connection Points 行包含以下单元格。</span><span class="sxs-lookup"><span data-stu-id="cff90-111">Connection Points rows contain the following cells.</span></span> <span data-ttu-id="cff90-112">有关详细信息，请参阅特定单元格主题。</span><span class="sxs-lookup"><span data-stu-id="cff90-112">For more details, see the specific cell topics.</span></span> 
  
|<span data-ttu-id="cff90-113">**Cell**</span><span class="sxs-lookup"><span data-stu-id="cff90-113">**Cell**</span></span>|<span data-ttu-id="cff90-114">**说明**</span><span class="sxs-lookup"><span data-stu-id="cff90-114">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="cff90-115">X</span><span class="sxs-lookup"><span data-stu-id="cff90-115">X</span></span>](x-cell-connection-points-section.md) <br/> |<span data-ttu-id="cff90-116">*X* -在本地坐标系中的连接点的坐标。</span><span class="sxs-lookup"><span data-stu-id="cff90-116">The  *x*  -coordinate for a connection point in local coordinates.</span></span>  <br/> |
|[<span data-ttu-id="cff90-117">Y</span><span class="sxs-lookup"><span data-stu-id="cff90-117">Y</span></span>](y-cell-connection-points-section.md) <br/> |<span data-ttu-id="cff90-118">*Y* -在本地坐标系中的连接点的坐标。</span><span class="sxs-lookup"><span data-stu-id="cff90-118">The  *y*  -coordinate for a connection point in local coordinates.</span></span>  <br/> |
|[<span data-ttu-id="cff90-119">DirX/A</span><span class="sxs-lookup"><span data-stu-id="cff90-119">DirX/A</span></span>](dirxa-cell-connection-points-section.md) <br/> |<span data-ttu-id="cff90-120">*X* -组件所需的对齐向量的匹配连接点。</span><span class="sxs-lookup"><span data-stu-id="cff90-120">The  *x*  -component for the required alignment vector of a matching connection point.</span></span> <span data-ttu-id="cff90-121">此外可用于确定动态连接线的附加的线路的方向。</span><span class="sxs-lookup"><span data-stu-id="cff90-121">It is also used to orient the attached leg of a dynamic connector.</span></span> <span data-ttu-id="cff90-122">此单元格采用浮点数据点值。</span><span class="sxs-lookup"><span data-stu-id="cff90-122">This cell takes a floating point value.</span></span>  <br/> |
|[<span data-ttu-id="cff90-123">DirY/B</span><span class="sxs-lookup"><span data-stu-id="cff90-123">DirY/B</span></span>](diryb-cell-connection-points-section.md) <br/> |<span data-ttu-id="cff90-124">*Y* -组件所需的对齐向量的匹配连接点。</span><span class="sxs-lookup"><span data-stu-id="cff90-124">The  *y*  -component for the required alignment vector of a matching connection point.</span></span> <span data-ttu-id="cff90-125">此外可用于确定动态连接线的附加的线路的方向。</span><span class="sxs-lookup"><span data-stu-id="cff90-125">It is also used to orient the attached leg of a dynamic connector.</span></span> <span data-ttu-id="cff90-126">此单元格采用浮点数据点值。</span><span class="sxs-lookup"><span data-stu-id="cff90-126">This cell takes a floating point value.</span></span>  <br/> |
|[<span data-ttu-id="cff90-127">Type/C</span><span class="sxs-lookup"><span data-stu-id="cff90-127">Type/C</span></span>](typec-cell-connection-points-section.md) <br/> |<span data-ttu-id="cff90-128">连接点类型（0 = 向内；1 = 向外；2 = 向内 + 向外）。</span><span class="sxs-lookup"><span data-stu-id="cff90-128">The connection point type (0 = inward; 1 = outward; 2 = inward + outward).</span></span>  <br/> |
|[<span data-ttu-id="cff90-129">D</span><span class="sxs-lookup"><span data-stu-id="cff90-129">D</span></span>](d-cell-connection-points-section.md) <br/> |<span data-ttu-id="cff90-p106">可用于输入或测试公式的草稿单元格。若要访问此单元格，可右击某一行，然后单击快捷菜单上的 **“更改行类型”**。</span><span class="sxs-lookup"><span data-stu-id="cff90-p106">A scratch cell that you can use for entering or testing formulas. To access this cell, right-click a row, and then click **Change Row Type** on the shortcut menu.  </span></span><br/> |
   
## <a name="remarks"></a><span data-ttu-id="cff90-132">说明</span><span class="sxs-lookup"><span data-stu-id="cff90-132">Remarks</span></span>

<span data-ttu-id="cff90-133">在连接的单元格。</span><span class="sxs-lookup"><span data-stu-id="cff90-133">Cells in the Connections.</span></span> <span data-ttu-id="cff90-134">*名称*行之所以标为 DirX/A、 DirY/B 和 Type/C 因为这些行可能是扩展或非扩展行。</span><span class="sxs-lookup"><span data-stu-id="cff90-134">*name*  row are labeled DirX/A, DirY/B, and Type/C because these rows can be extended or non-extended rows.</span></span> 
  
<span data-ttu-id="cff90-p108">大多数连接点（通过用户界面创建的所有连接点）都是非扩展的，具有 DirX、DirY 和 Type 单元格。它们的行类型为 **visTagCnnctPt** 或 **visTagCnnctNamed**。</span><span class="sxs-lookup"><span data-stu-id="cff90-p108">Most connection points (all connection points created through the user interface) are non-extended and have DirX, DirY, and Type cells. Their row type is **visTagCnnctPt** or **visTagCnnctNamed.**</span></span>
  
<span data-ttu-id="cff90-p109">在非扩展行中，DirX 和 DirY 单元格共同定义了一个方向向量，该向量会影响到使用连接点进行连接时所涉及到的形状的转动。如果两个单元格皆为零，则该点为无方向。连接点的类型包括：</span><span class="sxs-lookup"><span data-stu-id="cff90-p109">In non-extended rows the DirX and DirY cells together define a direction vector that influences the rotation of shapes involved in connections using the connection point. If both are zero the point is directionless. Connection points are of the following types:</span></span>
  
- <span data-ttu-id="cff90-p110">向内 (0)，表示形状粘附于它们。这是默认值。</span><span class="sxs-lookup"><span data-stu-id="cff90-p110">Inward (0), which means that shapes glue to them. This is the default.</span></span>
    
- <span data-ttu-id="cff90-142">向外 (1)，表示这些连接点将粘附于向内连接点。</span><span class="sxs-lookup"><span data-stu-id="cff90-142">Outward (1), which means these connection points will glue to inward connection points.</span></span>
    
- <span data-ttu-id="cff90-143">向内和向外 (2)，在此情况下，方向为向内方向，但是若用作向外连接则方向相反。</span><span class="sxs-lookup"><span data-stu-id="cff90-143">Both inward and outward (2), in which case the direction is the inward direction, which is reversed if used as an outward connection.</span></span>
    
<span data-ttu-id="cff90-p111">扩展行有 A、B、C 和 D 单元格，其行为类似“向内”类型的无方向的非扩展行。通常不使用扩展行，但在将数据与 A、B、C 和 D 单元格中的连接点相关联时可能要使用它们。它们的行类型为 **visTagCnnctPtABCD** 或 **visTagCnnctNamedABCD**。如果 D 单元格中存在公式，便可识别这是扩展行。</span><span class="sxs-lookup"><span data-stu-id="cff90-p111">Extended rows have A, B, C, and D cells and behave like directionless non-extended rows of type Inward. Extended rows are not commonly used, but you might use them to associate data with a connection point in the A, B, C, and D cells. Their row type is **visTagCnnctPtABCD** or **visTagCnnctNamedABCD**. Extended rows can be identified by the presence of a formula in the D cell.</span></span> 
  
 <span data-ttu-id="cff90-148">您可以添加任意多个连接。</span><span class="sxs-lookup"><span data-stu-id="cff90-148">You can add as many Connections.</span></span>  <span data-ttu-id="cff90-149">*名称*行根据需要为这些行中，指定有意义的名称，并设置单元格的值。</span><span class="sxs-lookup"><span data-stu-id="cff90-149">*name*  rows as you need, assign meaningful names to the rows, and set cell values.</span></span> <span data-ttu-id="cff90-150">若要添加到现有的 Connection points 连接点，右击某一行，然后单击快捷菜单上的**插入行**。</span><span class="sxs-lookup"><span data-stu-id="cff90-150">To add a connection point to an existing Connection Points section, right-click a row and click **Insert Row** on the shortcut menu.</span></span> 
  
<span data-ttu-id="cff90-151">您可以引用 Connection Points 行单元格，这些行名称在 ShapeSheet 窗口中显示为红色文本。</span><span class="sxs-lookup"><span data-stu-id="cff90-151">You can reference Connection Points row cells by their row name, which appears in a ShapeSheet window in red text.</span></span> <span data-ttu-id="cff90-152">若要更改行名称，单击它，，然后键入名称，例如*自定义*，例如，若要创建的行名称 Connections.Custom。</span><span class="sxs-lookup"><span data-stu-id="cff90-152">To change the row name, click it, and then type a name such as  *Custom*  , for example, to create the row name Connections.Custom.</span></span> <span data-ttu-id="cff90-153">然后，可以引用 X 单元格使用 Connections.Custom.X，例如或 Connections.X1，如果您想要使用的行号。</span><span class="sxs-lookup"><span data-stu-id="cff90-153">You can then reference the X cell using Connections.Custom.X, for example, or Connections.X1 if you want to use the row number.</span></span> 
  
<span data-ttu-id="cff90-154">您输入的行名称在该内容中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="cff90-154">The row name you enter must be unique within the section.</span></span> <span data-ttu-id="cff90-155">在连接点部分中创建一个行的名称时，Microsoft Office Visio 使用默认名称，Connections.Row_ *n*姓名部分中的所有行。</span><span class="sxs-lookup"><span data-stu-id="cff90-155">When you create a name for one row in the Connection Points section, Microsoft Office Visio names all the rows in the section with the default name, Connections.Row_ *n*  .</span></span> 
  
<span data-ttu-id="cff90-p115">命名的 Connection Points 行与 Visio 5.0 之前的版本不兼容。用早期格式保存带有命名的 Connection Points 行的 Visio 绘图文件时，对命名的 Connection Points 行的引用会转换为索引引用，且行名称会丢失。</span><span class="sxs-lookup"><span data-stu-id="cff90-p115">Named Connection Points rows are not compatible with versions of Visio earlier than 5.0. When saving a Visio drawing file with named Connection Points rows to an earlier format, references to named Connection Points rows are converted to indexed references, and the row names are lost.</span></span>
  

