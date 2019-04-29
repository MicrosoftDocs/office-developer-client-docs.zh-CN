---
title: Default 单元格（“Hyperlinks”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251545
localization_priority: Normal
ms.assetid: 0edea0ea-58dd-15da-6d4f-185d40133452
description: 确定形状或页的默认超链接。将此单元格的值设置为 TRUE 可以将一个超链接设置为默认超链接。
ms.openlocfilehash: 9991bd0e241c5dfd4fda65aeff8b6cc203ad3458
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434352"
---
# <a name="default-cell-hyperlinks-section"></a><span data-ttu-id="83498-104">Default 单元格（“Hyperlinks”内容）</span><span class="sxs-lookup"><span data-stu-id="83498-104">Default Cell (Hyperlinks Section)</span></span>

<span data-ttu-id="83498-p102">确定形状或页的默认超链接。将此单元格的值设置为 TRUE 可以将一个超链接设置为默认超链接。</span><span class="sxs-lookup"><span data-stu-id="83498-p102">Determines the default hyperlink for a shape or page. Set the value of this cell to TRUE to set a hyperlink as the default.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="83498-107">说明</span><span class="sxs-lookup"><span data-stu-id="83498-107">Remarks</span></span>

<span data-ttu-id="83498-p103">您还可以使用以下方法设置默认超链接：选择一个形状，在 **“插入”** 选项卡上单击 **“超链接”**，选择一个超链接，然后单击 **“默认值”**。默认的超链接以粗体文本显示。</span><span class="sxs-lookup"><span data-stu-id="83498-p103">You can also set the default hyperlink by selecting a shape, clicking **Hyperlink** on the **Insert** tab, selecting a hyperlink, and then clicking **Default**. The default hyperlink appears in bold text.</span></span>
  
<span data-ttu-id="83498-110">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Default 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="83498-110">To get a reference to the Default cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="83498-111">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="83498-111">Cell name:</span></span>  <br/> |<span data-ttu-id="83498-112">超链接。</span><span class="sxs-lookup"><span data-stu-id="83498-112">Hyperlink.</span></span> <span data-ttu-id="83498-113">*名称*。超链接的默认位置。</span><span class="sxs-lookup"><span data-stu-id="83498-113">*Name*  .Default           where Hyperlink.</span></span> <span data-ttu-id="83498-114">*名称*是行名称</span><span class="sxs-lookup"><span data-stu-id="83498-114">*Name*  is the row name</span></span>  <br/> |
   
<span data-ttu-id="83498-115">若要从某个程序按索引获取对 Default 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="83498-115">To get a reference to the Default cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="83498-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="83498-116">Section index:</span></span>  <br/> |<span data-ttu-id="83498-117">**visSectionHyperlink**</span><span class="sxs-lookup"><span data-stu-id="83498-117">**visSectionHyperlink**</span></span> <br/> |
|<span data-ttu-id="83498-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="83498-118">Row index:</span></span>  <br/> |<span data-ttu-id="83498-119">**visRow1stHyperlink** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="83498-119">**visRow1stHyperlink** +  *i*           where  *i*  = 0, 1, 2...</span></span>  <br/> |
|<span data-ttu-id="83498-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="83498-120">Cell index:</span></span>  <br/> |<span data-ttu-id="83498-121">**visHLinkDefault**</span><span class="sxs-lookup"><span data-stu-id="83498-121">**visHLinkDefault**</span></span> <br/> |
   

