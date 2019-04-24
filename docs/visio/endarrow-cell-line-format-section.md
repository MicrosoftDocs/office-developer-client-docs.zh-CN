---
title: EndArrow 单元格（“Line Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm320
localization_priority: Normal
ms.assetid: 2f9c11ba-a316-bc34-60d4-0a41b2af486f
description: 指出线条末端是箭头还是其他线端格式。
ms.openlocfilehash: 54ef11125a8774914a60897850fb75cd4ab949a5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328901"
---
# <a name="endarrow-cell-line-format-section"></a><span data-ttu-id="8e438-103">EndArrow 单元格（“Line Format”内容）</span><span class="sxs-lookup"><span data-stu-id="8e438-103">EndArrow Cell (Line Format Section)</span></span>

<span data-ttu-id="8e438-104">指出线条末端是箭头还是其他线端格式。</span><span class="sxs-lookup"><span data-stu-id="8e438-104">Indicates whether a line has an arrowhead or other line end format at its last vertex.</span></span>
  
|<span data-ttu-id="8e438-105">**Value**</span><span class="sxs-lookup"><span data-stu-id="8e438-105">**Value**</span></span>|<span data-ttu-id="8e438-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="8e438-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8e438-107">0</span><span class="sxs-lookup"><span data-stu-id="8e438-107">0</span></span>  <br/> |<span data-ttu-id="8e438-108">无箭头。</span><span class="sxs-lookup"><span data-stu-id="8e438-108">No arrowhead.</span></span>  <br/> |
|<span data-ttu-id="8e438-109">1 - 45</span><span class="sxs-lookup"><span data-stu-id="8e438-109">1 - 45</span></span>  <br/> |<span data-ttu-id="8e438-110">各种类型的箭头样式，与 **“线条”** 对话框中的索引项相对应。</span><span class="sxs-lookup"><span data-stu-id="8e438-110">Assorted arrowhead styles that correspond to indexed entries in the **Line** dialog box.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8e438-111">注解</span><span class="sxs-lookup"><span data-stu-id="8e438-111">Remarks</span></span>

<span data-ttu-id="8e438-112">您还可以在 **“线条”** 对话框中设置此值（在 **“开始”** 选项卡上的 **“形状”** 组中，单击 **“线条”**，指向 **“箭头”**，然后单击 **“其他箭头”**）。</span><span class="sxs-lookup"><span data-stu-id="8e438-112">You can also set this value in the **Line** dialog box (on the **Home** tab, in the **Shape** group, click **Line**, point to **Arrows**, and then click **More Arrows**).</span></span> <span data-ttu-id="8e438-113">箭头的大小在 EndArrowSize 单元格中设置。</span><span class="sxs-lookup"><span data-stu-id="8e438-113">The size of the arrowhead is set in the EndArrowSize cell.</span></span>
  
<span data-ttu-id="8e438-114">您可以使用 USE 函数在此单元格中指定自定义线端。</span><span class="sxs-lookup"><span data-stu-id="8e438-114">You can specify a custom line end using the USE function in this cell.</span></span> 
  
<span data-ttu-id="8e438-115">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 EndArrow 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="8e438-115">To get a reference to the EndArrow cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="8e438-116">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="8e438-116">Cell name:</span></span>  <br/> |<span data-ttu-id="8e438-117">EndArrow</span><span class="sxs-lookup"><span data-stu-id="8e438-117">EndArrow</span></span>  <br/> |
   
<span data-ttu-id="8e438-118">若要从某个程序按索引获取对 EndArrow 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="8e438-118">To get a reference to the EndArrow cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="8e438-119">内容索引：</span><span class="sxs-lookup"><span data-stu-id="8e438-119">Section index:</span></span>  <br/> |<span data-ttu-id="8e438-120">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="8e438-120">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="8e438-121">行索引：</span><span class="sxs-lookup"><span data-stu-id="8e438-121">Row index:</span></span>  <br/> |<span data-ttu-id="8e438-122">**visRowLine**</span><span class="sxs-lookup"><span data-stu-id="8e438-122">**visRowLine**</span></span> <br/> |
|<span data-ttu-id="8e438-123">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="8e438-123">Cell index:</span></span>  <br/> |<span data-ttu-id="8e438-124">**visLineEndArrow**</span><span class="sxs-lookup"><span data-stu-id="8e438-124">**visLineEndArrow**</span></span> <br/> |
   

