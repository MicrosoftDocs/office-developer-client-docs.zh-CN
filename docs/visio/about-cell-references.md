---
title: 关于单元格引用
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
f1_keywords:
- Vis_DSS.chm82251827
localization_priority: Normal
ms.assetid: e6a9aceb-90d7-fb53-eaf4-416a1ae2a98b
description: 您可以使用 ShapeSheet 单元格引用在公式间创建相互依赖关系。单元格引用使您能根据某一单元格的值计算另一单元格的值。例如，形状的 Width 单元格可能包含通过引用它的 Height 单元格的值来计算该形状的宽度的公式，这样，当用户纵向调整形状的大小时，它的宽度会保持与高度的比例。
ms.openlocfilehash: 54c7fd69e2ddaa9350996e2d8c921958a04e34ab
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779610"
---
# <a name="about-cell-references"></a><span data-ttu-id="744e5-105">关于单元格引用</span><span class="sxs-lookup"><span data-stu-id="744e5-105">About Cell References</span></span>

<span data-ttu-id="744e5-p102">您可以使用 ShapeSheet 单元格引用在公式间创建相互依赖关系。单元格引用使您能根据某一单元格的值计算另一单元格的值。例如，形状的 Width 单元格可能包含通过引用它的 Height 单元格的值来计算该形状的宽度的公式，这样，当用户纵向调整形状的大小时，它的宽度会保持与高度的比例。</span><span class="sxs-lookup"><span data-stu-id="744e5-p102">You can create interdependencies among formulas by means of ShapeSheet cell references. Cell references give you the power to calculate a value for one cell based on another cell's value. For example, a shape's Width cell might contain a formula that calculates the shape's width by referring to the value of its Height cell, so that when a user resizes the shape vertically, its width stays in proportion.</span></span>
  
<span data-ttu-id="744e5-109">在单元格的公式中，可以引用同一形状的单元格或者其他对象（例如文档或页面）的单元格，这样，Microsoft Visio 将根据其他单元格的值为某个单元格计算值。</span><span class="sxs-lookup"><span data-stu-id="744e5-109">In a cell's formula, you can refer to a cell of the same shape or another object, such as a document or page, so that Microsoft Visio calculates a value for one cell based on another cell's value.</span></span>
  
## <a name="what-cell-references-can-include"></a><span data-ttu-id="744e5-110">可包括的单元格引用</span><span class="sxs-lookup"><span data-stu-id="744e5-110">What cell references can include</span></span>

<span data-ttu-id="744e5-111">单元格引用可以包含形状标识符 (Id) 或名称。</span><span class="sxs-lookup"><span data-stu-id="744e5-111">Cell references can include shape identifiers (IDs) or names.</span></span> <span data-ttu-id="744e5-112">是否形状已命名，始终可以引用由其 ID，页上的任何形状。</span><span class="sxs-lookup"><span data-stu-id="744e5-112">You can always refer to any shape on the page by its ID, whether the shape is named or not.</span></span> <span data-ttu-id="744e5-113">如果形状不起作用尚未命名，它的默认名称为工作表。</span><span class="sxs-lookup"><span data-stu-id="744e5-113">If a shape hasn't been named, its default name is Sheet.</span></span> <span data-ttu-id="744e5-114">*i* ，其中*i*是形状 id。</span><span class="sxs-lookup"><span data-stu-id="744e5-114">*i*  , where  *i*  is the shape ID.</span></span> <span data-ttu-id="744e5-115">当形状创建并且不会更改除非将形状移动到另一个页面或文档分配的 ID。</span><span class="sxs-lookup"><span data-stu-id="744e5-115">The ID is assigned when the shape is created and does not change unless you move the shape to another page or document.</span></span> <span data-ttu-id="744e5-116">如果页上的多个形状具有相同的名称，则必须包括分配的 id。</span><span class="sxs-lookup"><span data-stu-id="744e5-116">If more than one shape on a page has the same name, you must include the assigned ID.</span></span> 
  
## <a name="cell-reference-syntax-and-examples"></a><span data-ttu-id="744e5-117">单元格引用语法和示例</span><span class="sxs-lookup"><span data-stu-id="744e5-117">Cell reference syntax and examples</span></span>

<span data-ttu-id="744e5-p104">您使用的语法以及是否能按名称引用形状都取决于两个对象之间的关系。以下通用规则适用：</span><span class="sxs-lookup"><span data-stu-id="744e5-p104">The syntax you use and whether you can refer to a shape by name depend on the relationship between the two objects. These general rules apply:</span></span>
  
- <span data-ttu-id="744e5-p105">如果您编辑一个形状的公式，而某个形状是它的对等形状，则可以按名称引用这个对等形状。如果该对等形状是一个组合，则可以按名称引用该组合，但不能引用它的成员。您也不能按名称引用一个形状的父形状或父形状的对等形状。</span><span class="sxs-lookup"><span data-stu-id="744e5-p105">If a shape is a peer of the shape whose formula you are editing, you can refer to the peer shape by name. If the peer shape is a group, you can refer by name to the group, but not its members. Neither can you refer by name to a shape's parent or its parent's peers.</span></span>
    
- <span data-ttu-id="744e5-123">您可以用语法 Sheet.ID 来引用页面上的任何形状，不论该形状是在组合中或者是一个形状的父形状。</span><span class="sxs-lookup"><span data-stu-id="744e5-123">You can use Sheet.ID syntax to refer to any shape on the page, whether the shape is in a group or is a parent of a shape.</span></span>
    
- <span data-ttu-id="744e5-p106">含有非标准字符的名称必须用单引号引起来。非标准名称中的单引号字符前面必须有一个单引号。</span><span class="sxs-lookup"><span data-stu-id="744e5-p106">Names that contain nonstandard characters must be enclosed in single quotation marks. Single quotation mark characters in a nonstandard name must be prefixed by a single quotation mark.</span></span>
    
|<span data-ttu-id="744e5-126">**引用的单元格**</span><span class="sxs-lookup"><span data-stu-id="744e5-126">**To reference a cell of**</span></span>|<span data-ttu-id="744e5-127">**使用以下语法**</span><span class="sxs-lookup"><span data-stu-id="744e5-127">**Use this syntax**</span></span>|<span data-ttu-id="744e5-128">**示例**</span><span class="sxs-lookup"><span data-stu-id="744e5-128">**Example**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="744e5-129">
                
                
                同一形状
</span><span class="sxs-lookup"><span data-stu-id="744e5-129">The same shape</span></span>  <br/> | <span data-ttu-id="744e5-130">CellName</span><span class="sxs-lookup"><span data-stu-id="744e5-130">CellName</span></span>  <br/> | <span data-ttu-id="744e5-131">宽度</span><span class="sxs-lookup"><span data-stu-id="744e5-131">Width</span></span>  <br/> |
| <span data-ttu-id="744e5-132">
                
                
                形状、组合或参考线
</span><span class="sxs-lookup"><span data-stu-id="744e5-132">A shape, group, or guide</span></span>  <br/> | <span data-ttu-id="744e5-133">Shapename ！CellName</span><span class="sxs-lookup"><span data-stu-id="744e5-133">Shapename!CellName</span></span>  <br/> | <span data-ttu-id="744e5-134">
                
                
                Star!Angle
</span><span class="sxs-lookup"><span data-stu-id="744e5-134">Star!Angle</span></span>  <br/> |
| <span data-ttu-id="744e5-135">
                
                
                形状、组合或参考线，其中有多个同级的形状同名
</span><span class="sxs-lookup"><span data-stu-id="744e5-135">A shape, group, or guide in which more than one shape at the same level has the same name</span></span>  <br/> | <span data-ttu-id="744e5-136">Shapename.ID ！CellName</span><span class="sxs-lookup"><span data-stu-id="744e5-136">Shapename.ID!CellName</span></span>  <br/> | <span data-ttu-id="744e5-137">Executive.2 ！高度</span><span class="sxs-lookup"><span data-stu-id="744e5-137">Executive.2!Height</span></span>  <br/> |
| <span data-ttu-id="744e5-138">
                
                
                带有已建立索引的行的命名列
</span><span class="sxs-lookup"><span data-stu-id="744e5-138">A named column with indexed rows</span></span>  <br/> | <span data-ttu-id="744e5-139">Section.Column[index]</span><span class="sxs-lookup"><span data-stu-id="744e5-139">Section.Column[index]</span></span>  <br/> | <span data-ttu-id="744e5-140">Char.Font[3]</span><span class="sxs-lookup"><span data-stu-id="744e5-140">Char.Font[3]</span></span>  <br/> |
| <span data-ttu-id="744e5-141">
                
                
                带有已建立索引的行的未命名列
</span><span class="sxs-lookup"><span data-stu-id="744e5-141">An unnamed column with indexed rows</span></span>  <br/> | <span data-ttu-id="744e5-142">Section.ColumnIndex</span><span class="sxs-lookup"><span data-stu-id="744e5-142">Section.ColumnIndex</span></span>  <br/> | <span data-ttu-id="744e5-143">Scratch.A5</span><span class="sxs-lookup"><span data-stu-id="744e5-143">Scratch.A5</span></span>  <br/> |
| <span data-ttu-id="744e5-144">
                
                
                任何形状、页面、主控形状或样式
</span><span class="sxs-lookup"><span data-stu-id="744e5-144">Any shape, page, master, or style</span></span>  <br/> | <span data-ttu-id="744e5-145">Sheet.ID ！CellName</span><span class="sxs-lookup"><span data-stu-id="744e5-145">Sheet.ID!CellName</span></span>  <br/> | <span data-ttu-id="744e5-146">Sheet.8 ！FillForegnd</span><span class="sxs-lookup"><span data-stu-id="744e5-146">Sheet.8!FillForegnd</span></span>  <br/> |
| <span data-ttu-id="744e5-147">
                
                
                主控形状
</span><span class="sxs-lookup"><span data-stu-id="744e5-147">A master</span></span>  <br/> | <span data-ttu-id="744e5-148">主控形状 [MasterName] ！SheetName ！CellReference</span><span class="sxs-lookup"><span data-stu-id="744e5-148">Masters[MasterName]!SheetName!CellReference</span></span>  <br/> | <span data-ttu-id="744e5-149">主控形状 [齿轮] ！轴 ！Geometry1.X1</span><span class="sxs-lookup"><span data-stu-id="744e5-149">Masters[Gear]!Shaft!Geometry1.X1</span></span>  <br/> |
| <span data-ttu-id="744e5-150">
                
                
                对象所在的页面或主控形状页面
</span><span class="sxs-lookup"><span data-stu-id="744e5-150">The page or master page on which the object is located</span></span>  <br/> | <span data-ttu-id="744e5-151">页面设置 ！CellReference</span><span class="sxs-lookup"><span data-stu-id="744e5-151">ThePage!CellReference</span></span>  <br/> | <span data-ttu-id="744e5-152">页面设置 ！User.Vanishing_Point</span><span class="sxs-lookup"><span data-stu-id="744e5-152">ThePage!User.Vanishing_Point</span></span>  <br/> |
| <span data-ttu-id="744e5-153">
                
                
                文档中的另一页面
</span><span class="sxs-lookup"><span data-stu-id="744e5-153">Another page in the document</span></span>  <br/> | <span data-ttu-id="744e5-154">页面 [PageName] ！SheetName ！CellReference</span><span class="sxs-lookup"><span data-stu-id="744e5-154">Pages[PageName]!SheetName!CellReference</span></span>  <br/> | <span data-ttu-id="744e5-155">页面 [3] ！Sheet.4 ！BeginX</span><span class="sxs-lookup"><span data-stu-id="744e5-155">Pages[Page-3]!Sheet.4!BeginX</span></span>  <br/> |
| <span data-ttu-id="744e5-156">
                
                
                样式
</span><span class="sxs-lookup"><span data-stu-id="744e5-156">A style</span></span>  <br/> | <span data-ttu-id="744e5-157">样式 ！SheetName ！CellReference</span><span class="sxs-lookup"><span data-stu-id="744e5-157">Styles!SheetName!CellReference</span></span>  <br/> | <span data-ttu-id="744e5-158">样式 ！管理器 ！LineColor</span><span class="sxs-lookup"><span data-stu-id="744e5-158">Styles!Manager!LineColor</span></span>  <br/> |
| <span data-ttu-id="744e5-159">
                
                
                文档
</span><span class="sxs-lookup"><span data-stu-id="744e5-159">The document</span></span>  <br/> | <span data-ttu-id="744e5-160">TheDoc ！CellReference</span><span class="sxs-lookup"><span data-stu-id="744e5-160">TheDoc!CellReference</span></span>  <br/> | <span data-ttu-id="744e5-161">TheDoc ！PreviewQuality</span><span class="sxs-lookup"><span data-stu-id="744e5-161">TheDoc!PreviewQuality</span></span>  <br/> |
| <span data-ttu-id="744e5-162">
                
                
                带有非标准名称的形状、页面、主控形状、文档或样式。
</span><span class="sxs-lookup"><span data-stu-id="744e5-162">A shape, page, master, document, or style with a nonstandard name.</span></span>  <br/> | <span data-ttu-id="744e5-163">Sheetname' ！CellName</span><span class="sxs-lookup"><span data-stu-id="744e5-163">'Sheetname'!CellName</span></span>  <br/> | <span data-ttu-id="744e5-164">1-D ' ！LineColor</span><span class="sxs-lookup"><span data-stu-id="744e5-164">'1-D'!LineColor</span></span>  <br/> |
   

