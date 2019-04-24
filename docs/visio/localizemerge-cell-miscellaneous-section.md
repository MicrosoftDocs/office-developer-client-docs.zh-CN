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
ms.openlocfilehash: ddd6041ec6531652deb38a0c16be2c741bac91a6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32344572"
---
# <a name="localizemerge-cell-miscellaneous-section"></a><span data-ttu-id="88e3f-103">LocalizeMerge 单元格（“Miscellaneous”内容）</span><span class="sxs-lookup"><span data-stu-id="88e3f-103">LocalizeMerge Cell (Miscellaneous Section)</span></span>

<span data-ttu-id="88e3f-104">确定在文档间复制时是否本地化形状。</span><span class="sxs-lookup"><span data-stu-id="88e3f-104">Determines whether shapes are localized when copied between documents.</span></span>
  
|<span data-ttu-id="88e3f-105">**Value**</span><span class="sxs-lookup"><span data-stu-id="88e3f-105">**Value**</span></span>|<span data-ttu-id="88e3f-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="88e3f-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="88e3f-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="88e3f-107">TRUE</span></span>  <br/> | <span data-ttu-id="88e3f-108">使用目标文档的语言本地化形状。</span><span class="sxs-lookup"><span data-stu-id="88e3f-108">Localize a shape in the language of the destination document.</span></span>  <br/> |
| <span data-ttu-id="88e3f-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="88e3f-109">FALSE</span></span>  <br/> | <span data-ttu-id="88e3f-110">不根据目标文档的语言本地化形状 (默认值)。</span><span class="sxs-lookup"><span data-stu-id="88e3f-110">Do not localize a shape based on the language of the destination document (the default).</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="88e3f-111">注解</span><span class="sxs-lookup"><span data-stu-id="88e3f-111">Remarks</span></span>

<span data-ttu-id="88e3f-112">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 LocalizeMerge 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="88e3f-112">To get a reference to the LocalizeMerge cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="88e3f-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="88e3f-113">Cell name:</span></span>  <br/> | <span data-ttu-id="88e3f-114">LocalizeMerge</span><span class="sxs-lookup"><span data-stu-id="88e3f-114">LocalizeMerge</span></span>  <br/> |
   
<span data-ttu-id="88e3f-115">要从某个程序按索引获取对 LocalizeMerge 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="88e3f-115">To get a reference to the LocalizeMerge cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="88e3f-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="88e3f-116">Section index:</span></span>  <br/> |<span data-ttu-id="88e3f-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="88e3f-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="88e3f-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="88e3f-118">Row index:</span></span>  <br/> |<span data-ttu-id="88e3f-119">**visRowMisc**</span><span class="sxs-lookup"><span data-stu-id="88e3f-119">**visRowMisc**</span></span> <br/> |
| <span data-ttu-id="88e3f-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="88e3f-120">Cell index:</span></span>  <br/> |<span data-ttu-id="88e3f-121">**visObjLocalizeMerge**</span><span class="sxs-lookup"><span data-stu-id="88e3f-121">**visObjLocalizeMerge**</span></span> <br/> |
   

