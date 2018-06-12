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
ms.openlocfilehash: 567a90b3162c109582c3149c156a994392980577
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780105"
---
# <a name="description-cell-hyperlinks-section"></a><span data-ttu-id="1c678-103">Description 单元格（“Hyperlinks”内容）</span><span class="sxs-lookup"><span data-stu-id="1c678-103">Description Cell (Hyperlinks Section)</span></span>

<span data-ttu-id="1c678-104">代表超链接的说明性文本字符串。</span><span class="sxs-lookup"><span data-stu-id="1c678-104">Represents a descriptive text string for a hyperlink.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="1c678-105">注解</span><span class="sxs-lookup"><span data-stu-id="1c678-105">Remarks</span></span>

<span data-ttu-id="1c678-106">使用此单元格可以存储有关超链接的注释；例如，“链接到我们的价格网站”。</span><span class="sxs-lookup"><span data-stu-id="1c678-106">Use this cell to store comments about the hyperlink; for example, "Link to our pricing Web site."</span></span>
  
<span data-ttu-id="1c678-107">此外可以设置此单元格的值，在**超链接**对话框 （单击**插入**选项卡上的**超链接**）。</span><span class="sxs-lookup"><span data-stu-id="1c678-107">You can also set the value of this cell in the **Hyperlinks** dialog box (click **Hyperlink** on the **Insert** tab).</span></span> 
  
<span data-ttu-id="1c678-108">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 Description 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="1c678-108">To get a reference to the Description cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="1c678-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="1c678-109">Cell name:</span></span>  <br/> | <span data-ttu-id="1c678-110">超链接。</span><span class="sxs-lookup"><span data-stu-id="1c678-110">Hyperlink.</span></span>  <span data-ttu-id="1c678-111">*名称*。说明其中超链接。</span><span class="sxs-lookup"><span data-stu-id="1c678-111">*Name*  .Description where Hyperlink.</span></span>  <span data-ttu-id="1c678-112">*Name*是超链接行的名称</span><span class="sxs-lookup"><span data-stu-id="1c678-112">*Name*  is the name of the hyperlink row</span></span>  <br/> |
   
<span data-ttu-id="1c678-113">若要从某个程序按索引获取对 Description 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="1c678-113">To get a reference to the Description cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="1c678-114">内容索引：</span><span class="sxs-lookup"><span data-stu-id="1c678-114">Section index:</span></span>  <br/> |<span data-ttu-id="1c678-115">**visSectionHyperlink**</span><span class="sxs-lookup"><span data-stu-id="1c678-115">**visSectionHyperlink**</span></span> <br/> |
| <span data-ttu-id="1c678-116">行索引：</span><span class="sxs-lookup"><span data-stu-id="1c678-116">Row index:</span></span>  <br/> |<span data-ttu-id="1c678-117">**visRow1stHyperlink** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="1c678-117">**visRow1stHyperlink** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="1c678-118">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="1c678-118">Cell index:</span></span>  <br/> |<span data-ttu-id="1c678-119">**visHLinkDescription**</span><span class="sxs-lookup"><span data-stu-id="1c678-119">**visHLinkDescription**</span></span> <br/> |
   

