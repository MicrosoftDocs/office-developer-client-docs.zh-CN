---
title: DefaultTabstop 单元格（“Text Block Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm220
localization_priority: Normal
ms.assetid: 3b3e458a-206c-8699-8bf7-da80f4350706
description: 确定默认制表位在文本块中的间隔。
ms.openlocfilehash: 1ae923f6373b9cee76238b1fb27ec5eb3acb43ce
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407828"
---
# <a name="defaulttabstop-cell-text-block-format-section"></a><span data-ttu-id="26968-103">DefaultTabstop 单元格（“Text Block Format”内容）</span><span class="sxs-lookup"><span data-stu-id="26968-103">DefaultTabstop Cell (Text Block Format Section)</span></span>

<span data-ttu-id="26968-104">确定默认制表位在文本块中的间隔。</span><span class="sxs-lookup"><span data-stu-id="26968-104">Determines the interval of the default tab stops in a text block.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="26968-105">备注</span><span class="sxs-lookup"><span data-stu-id="26968-105">Remarks</span></span>

<span data-ttu-id="26968-106">对于以英制单位创建的文档，默认值是 0.5 英寸；对于以公制单位创建的文档，默认值是 1.5 厘米。</span><span class="sxs-lookup"><span data-stu-id="26968-106">The default value is 0.5 inches for documents created in imperial units and 1.5 centimeters for documents created in metric units.</span></span>
  
<span data-ttu-id="26968-107">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 DefaultTabstop 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="26968-107">To get a reference to the DefaultTabstop cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="26968-108">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="26968-108">Cell name:</span></span>  <br/> |<span data-ttu-id="26968-109">DefaultTabstop</span><span class="sxs-lookup"><span data-stu-id="26968-109">DefaultTabstop</span></span>  <br/> |
   
<span data-ttu-id="26968-110">若要从某个程序按索引获取对 DefaultTabstop 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="26968-110">To get a reference to the DefaultTabstop cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="26968-111">内容索引：</span><span class="sxs-lookup"><span data-stu-id="26968-111">Section index:</span></span>  <br/> |<span data-ttu-id="26968-112">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="26968-112">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="26968-113">行索引：</span><span class="sxs-lookup"><span data-stu-id="26968-113">Row index:</span></span>  <br/> |<span data-ttu-id="26968-114">**visRowText**</span><span class="sxs-lookup"><span data-stu-id="26968-114">**visRowText**</span></span> <br/> |
|<span data-ttu-id="26968-115">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="26968-115">Cell index:</span></span>  <br/> |<span data-ttu-id="26968-116">**visTxtBlkDefaultTabStop**</span><span class="sxs-lookup"><span data-stu-id="26968-116">**visTxtBlkDefaultTabStop**</span></span> <br/> |
   

