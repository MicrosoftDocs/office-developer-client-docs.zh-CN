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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25396622"
---
# <a name="description-cell-hyperlinks-section"></a><span data-ttu-id="ea59c-103">Description 单元格（“Hyperlinks”部分）</span><span class="sxs-lookup"><span data-stu-id="ea59c-103">Description Cell (Hyperlinks Section)</span></span>

<span data-ttu-id="ea59c-104">代表超链接的说明性文本字符串。</span><span class="sxs-lookup"><span data-stu-id="ea59c-104">Represents a descriptive text string for a hyperlink.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="ea59c-105">注解</span><span class="sxs-lookup"><span data-stu-id="ea59c-105">Remarks</span></span>

<span data-ttu-id="ea59c-106">此单元格用于存储有关超链接; 注释例如，"我们定价网站链接。"</span><span class="sxs-lookup"><span data-stu-id="ea59c-106">Use this cell to store comments about the hyperlink; for example, "Link to our pricing website."</span></span>
  
<span data-ttu-id="ea59c-107">您还可以在 **“超链接”** 对话框（在 **“插入”** 选项卡上单击 **“超链接”**）中设置此单元格的值。</span><span class="sxs-lookup"><span data-stu-id="ea59c-107">You can also set the value of this cell in the **Hyperlinks** dialog box (click **Hyperlink** on the **Insert** tab).</span></span> 
  
<span data-ttu-id="ea59c-108">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Description 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="ea59c-108">To get a reference to the Description cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="ea59c-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="ea59c-109">Cell name:</span></span>  <br/> | <span data-ttu-id="ea59c-110">超链接。</span><span class="sxs-lookup"><span data-stu-id="ea59c-110">Hyperlink.</span></span>  <span data-ttu-id="ea59c-111">*名称*。说明其中超链接。</span><span class="sxs-lookup"><span data-stu-id="ea59c-111">*Name*  .Description where Hyperlink.</span></span>  <span data-ttu-id="ea59c-112">*Name*是超链接行的名称</span><span class="sxs-lookup"><span data-stu-id="ea59c-112">*Name*  is the name of the hyperlink row</span></span>  <br/> |
   
<span data-ttu-id="ea59c-113">要从某个程序按索引获取对 Description 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="ea59c-113">To get a reference to the Description cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="ea59c-114">内容索引：</span><span class="sxs-lookup"><span data-stu-id="ea59c-114">Section index:</span></span>  <br/> |<span data-ttu-id="ea59c-115">**visSectionHyperlink**</span><span class="sxs-lookup"><span data-stu-id="ea59c-115">**visSectionHyperlink**</span></span> <br/> |
| <span data-ttu-id="ea59c-116">行索引：</span><span class="sxs-lookup"><span data-stu-id="ea59c-116">Row index:</span></span>  <br/> |<span data-ttu-id="ea59c-117">**visRow1stHyperlink** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="ea59c-117">**visRow1stHyperlink** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="ea59c-118">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="ea59c-118">Cell index:</span></span>  <br/> |<span data-ttu-id="ea59c-119">**visHLinkDescription**</span><span class="sxs-lookup"><span data-stu-id="ea59c-119">**visHLinkDescription**</span></span> <br/> |
   

