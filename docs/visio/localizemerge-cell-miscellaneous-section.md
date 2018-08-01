---
title: LocalizeMerge 单元格（“Miscellaneous”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033773
localization_priority: Normal
ms.assetid: 734d4415-05dd-4c4d-763e-e035fa56dcec
description: 确定在文档间复制时是否本地化形状。
ms.openlocfilehash: 47593802e412c1871685f7218dd2a810bc2bc469
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780599"
---
# <a name="localizemerge-cell-miscellaneous-section"></a><span data-ttu-id="687dd-103">LocalizeMerge 单元格（“Miscellaneous”部分）</span><span class="sxs-lookup"><span data-stu-id="687dd-103">LocalizeMerge Cell (Miscellaneous Section)</span></span>

<span data-ttu-id="687dd-104">确定在文档间复制时是否本地化形状。</span><span class="sxs-lookup"><span data-stu-id="687dd-104">Determines whether shapes are localized when copied between documents.</span></span>
  
|<span data-ttu-id="687dd-105">**值**</span><span class="sxs-lookup"><span data-stu-id="687dd-105">**Value**</span></span>|<span data-ttu-id="687dd-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="687dd-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="687dd-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="687dd-107">TRUE</span></span>  <br/> | <span data-ttu-id="687dd-108">使用目标文档的语言本地化形状。</span><span class="sxs-lookup"><span data-stu-id="687dd-108">Localize a shape in the language of the destination document.</span></span>  <br/> |
| <span data-ttu-id="687dd-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="687dd-109">FALSE</span></span>  <br/> | <span data-ttu-id="687dd-110">不本地化形状基于目标文档 （默认值） 的语言。</span><span class="sxs-lookup"><span data-stu-id="687dd-110">Do not localize a shape based on the language of the destination document (the default).</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="687dd-111">说明</span><span class="sxs-lookup"><span data-stu-id="687dd-111">Remarks</span></span>

<span data-ttu-id="687dd-112">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 LocalizeMerge 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="687dd-112">To get a reference to the LocalizeMerge cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="687dd-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="687dd-113">Cell name:</span></span>  <br/> | <span data-ttu-id="687dd-114">LocalizeMerge</span><span class="sxs-lookup"><span data-stu-id="687dd-114">LocalizeMerge</span></span>  <br/> |
   
<span data-ttu-id="687dd-115">要从某个程序按索引获取对 LocalizeMerge 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="687dd-115">To get a reference to the LocalizeMerge cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="687dd-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="687dd-116">Section index:</span></span>  <br/> |<span data-ttu-id="687dd-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="687dd-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="687dd-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="687dd-118">Row index:</span></span>  <br/> |<span data-ttu-id="687dd-119">**visRowMisc**</span><span class="sxs-lookup"><span data-stu-id="687dd-119">**visRowMisc**</span></span> <br/> |
| <span data-ttu-id="687dd-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="687dd-120">Cell index:</span></span>  <br/> |<span data-ttu-id="687dd-121">**visObjLocalizeMerge**</span><span class="sxs-lookup"><span data-stu-id="687dd-121">**visObjLocalizeMerge**</span></span> <br/> |
   

