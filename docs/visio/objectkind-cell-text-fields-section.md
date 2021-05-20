---
title: ObjectKind 单元格（“Text Fields”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60058
localization_priority: Normal
ms.assetid: cc4c373c-f073-e3c9-3aaa-a4abf050cd20
description: 指示文本域的类型。
ms.openlocfilehash: c2f891620f704a3c48861124b886e49d356960ba
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438510"
---
# <a name="objectkind-cell-text-fields-section"></a><span data-ttu-id="b31de-103">ObjectKind 单元格（“Text Fields”内容）</span><span class="sxs-lookup"><span data-stu-id="b31de-103">ObjectKind Cell (Text Fields Section)</span></span>

<span data-ttu-id="b31de-104">指示文本域的类型。</span><span class="sxs-lookup"><span data-stu-id="b31de-104">Indicates the type of text field.</span></span>
  
|<span data-ttu-id="b31de-105">**值**</span><span class="sxs-lookup"><span data-stu-id="b31de-105">**Value**</span></span>|<span data-ttu-id="b31de-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="b31de-106">**Description**</span></span>|<span data-ttu-id="b31de-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="b31de-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="b31de-108">0</span><span class="sxs-lookup"><span data-stu-id="b31de-108">0</span></span>  <br/> | <span data-ttu-id="b31de-109">标准</span><span class="sxs-lookup"><span data-stu-id="b31de-109">Standard</span></span>  <br/> |<span data-ttu-id="b31de-110">**visTFOKStandard**</span><span class="sxs-lookup"><span data-stu-id="b31de-110">**visTFOKStandard**</span></span> <br/> |
| <span data-ttu-id="b31de-111">1</span><span class="sxs-lookup"><span data-stu-id="b31de-111">1</span></span>  <br/> |<span data-ttu-id="b31de-112">纵横混排</span><span class="sxs-lookup"><span data-stu-id="b31de-112">Horizontal in vertical</span></span>  <br/> |<span data-ttu-id="b31de-113">**visTFOKHorizontaInVertical**</span><span class="sxs-lookup"><span data-stu-id="b31de-113">**visTFOKHorizontaInVertical**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b31de-114">备注</span><span class="sxs-lookup"><span data-stu-id="b31de-114">Remarks</span></span>

<span data-ttu-id="b31de-115">文本域可以是以下类型之一：</span><span class="sxs-lookup"><span data-stu-id="b31de-115">Text fields can be one of the following types:</span></span>
  
- <span data-ttu-id="b31de-116">标准，指示按照域类别插入该域。</span><span class="sxs-lookup"><span data-stu-id="b31de-116">Standard, indicating that the field was inserted by field category.</span></span>
    
- <span data-ttu-id="b31de-117">纵横混排，指示该域中的文本采用纵横混排的方式。</span><span class="sxs-lookup"><span data-stu-id="b31de-117">Horizontal in vertical, indicating that the field is horizontal text set within vertical text.</span></span>
    
<span data-ttu-id="b31de-118">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 ObjectKind 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="b31de-118">To get a reference to the ObjectKind cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="b31de-119">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="b31de-119">Cell name:</span></span>  <br/> | <span data-ttu-id="b31de-120">Fields.ObjectKind[  *i*  ] 其中  *i*  = <1> 2， 3...</span><span class="sxs-lookup"><span data-stu-id="b31de-120">Fields.ObjectKind[  *i*  ]            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="b31de-121">要从某个程序按索引获取对 ObjectKind 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="b31de-121">To get a reference to the ObjectKind cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="b31de-122">内容索引：</span><span class="sxs-lookup"><span data-stu-id="b31de-122">Section index:</span></span>  <br/> |<span data-ttu-id="b31de-123">**visSectionTextField**</span><span class="sxs-lookup"><span data-stu-id="b31de-123">**visSectionTextField**</span></span> <br/> |
| <span data-ttu-id="b31de-124">行索引：</span><span class="sxs-lookup"><span data-stu-id="b31de-124">Row index:</span></span>  <br/> |<span data-ttu-id="b31de-125">**visRowField**  +  *i* 其中 *i* = 0、1、2...</span><span class="sxs-lookup"><span data-stu-id="b31de-125">**visRowField** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="b31de-126">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="b31de-126">Cell index:</span></span>  <br/> |<span data-ttu-id="b31de-127">**visFieldObjectKind**</span><span class="sxs-lookup"><span data-stu-id="b31de-127">**visFieldObjectKind**</span></span> <br/> |
   

