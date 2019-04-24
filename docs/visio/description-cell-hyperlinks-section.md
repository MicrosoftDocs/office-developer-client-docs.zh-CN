---
title: Description 单元格（“Hyperlinks”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm230
localization_priority: Normal
ms.assetid: 2f571c65-6b7a-5a3a-c075-3c52d3ab989b
description: 代表超链接的说明性文本字符串。
ms.openlocfilehash: b58e6dc3ec2fc3b64db00e0f19e0718fe897aaa3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360240"
---
# <a name="description-cell-hyperlinks-section"></a><span data-ttu-id="f983d-103">Description 单元格（“Hyperlinks”内容）</span><span class="sxs-lookup"><span data-stu-id="f983d-103">Description Cell (Hyperlinks Section)</span></span>

<span data-ttu-id="f983d-104">代表超链接的说明性文本字符串。</span><span class="sxs-lookup"><span data-stu-id="f983d-104">Represents a descriptive text string for a hyperlink.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="f983d-105">注解</span><span class="sxs-lookup"><span data-stu-id="f983d-105">Remarks</span></span>

<span data-ttu-id="f983d-106">使用此单元格存储有关超链接的注释;例如, "链接到我们的定价网站"。</span><span class="sxs-lookup"><span data-stu-id="f983d-106">Use this cell to store comments about the hyperlink; for example, "Link to our pricing website."</span></span>
  
<span data-ttu-id="f983d-107">您还可以在 **“超链接”** 对话框（在 **“插入”** 选项卡上单击 **“超链接”**）中设置此单元格的值。</span><span class="sxs-lookup"><span data-stu-id="f983d-107">You can also set the value of this cell in the **Hyperlinks** dialog box (click **Hyperlink** on the **Insert** tab).</span></span> 
  
<span data-ttu-id="f983d-108">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Description 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="f983d-108">To get a reference to the Description cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="f983d-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="f983d-109">Cell name:</span></span>  <br/> | <span data-ttu-id="f983d-110">超链接。</span><span class="sxs-lookup"><span data-stu-id="f983d-110">Hyperlink.</span></span>  <span data-ttu-id="f983d-111">*名称*。超链接的说明。</span><span class="sxs-lookup"><span data-stu-id="f983d-111">*Name*  .Description where Hyperlink.</span></span>  <span data-ttu-id="f983d-112">*name*是超链接行的名称</span><span class="sxs-lookup"><span data-stu-id="f983d-112">*Name*  is the name of the hyperlink row</span></span>  <br/> |
   
<span data-ttu-id="f983d-113">要从某个程序按索引获取对 Description 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="f983d-113">To get a reference to the Description cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="f983d-114">内容索引：</span><span class="sxs-lookup"><span data-stu-id="f983d-114">Section index:</span></span>  <br/> |<span data-ttu-id="f983d-115">**visSectionHyperlink**</span><span class="sxs-lookup"><span data-stu-id="f983d-115">**visSectionHyperlink**</span></span> <br/> |
| <span data-ttu-id="f983d-116">行索引：</span><span class="sxs-lookup"><span data-stu-id="f983d-116">Row index:</span></span>  <br/> |<span data-ttu-id="f983d-117">**visRow1stHyperlink** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="f983d-117">**visRow1stHyperlink** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="f983d-118">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="f983d-118">Cell index:</span></span>  <br/> |<span data-ttu-id="f983d-119">**visHLinkDescription**</span><span class="sxs-lookup"><span data-stu-id="f983d-119">**visHLinkDescription**</span></span> <br/> |
   

