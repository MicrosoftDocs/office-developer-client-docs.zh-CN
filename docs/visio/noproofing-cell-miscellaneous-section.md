---
title: 'NoProofing Cell (Miscellaneous Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 668f993c-b4d1-4762-9801-c578b17fdafd
description: 确定是否自动更正拼写以及是否显示选定形状的拼写错误。 接受一个布尔值。
ms.openlocfilehash: 8d7eebcc349c54db3cd48d6c5fa3c8fa6f4f760e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431251"
---
# <a name="noproofing-cell-miscellaneous-section"></a><span data-ttu-id="c929f-104">NoProofing Cell (Miscellaneous Section) </span><span class="sxs-lookup"><span data-stu-id="c929f-104">NoProofing Cell (Miscellaneous Section)</span></span>

<span data-ttu-id="c929f-105">确定是否自动更正拼写以及是否显示选定形状的拼写错误。</span><span class="sxs-lookup"><span data-stu-id="c929f-105">Determines whether spelling is automatically corrected and whether spelling errors are displayed for the selected shape.</span></span> <span data-ttu-id="c929f-106">接受 **一个布尔** 值。</span><span class="sxs-lookup"><span data-stu-id="c929f-106">Takes a **Boolean** value.</span></span> 
  
|<span data-ttu-id="c929f-107">**值**</span><span class="sxs-lookup"><span data-stu-id="c929f-107">**Value**</span></span>|<span data-ttu-id="c929f-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="c929f-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c929f-109">TRUE</span><span class="sxs-lookup"><span data-stu-id="c929f-109">TRUE</span></span>  <br/> |<span data-ttu-id="c929f-110">不会自动更正拼写，并且不会为选定的形状显示拼写错误。</span><span class="sxs-lookup"><span data-stu-id="c929f-110">Spelling is not automatically corrected and spelling errors are not displayed for the selected shape.</span></span>  <br/> |
|<span data-ttu-id="c929f-111">FALSE</span><span class="sxs-lookup"><span data-stu-id="c929f-111">FALSE</span></span>  <br/> |<span data-ttu-id="c929f-112">自动更正拼写，并显示选定形状的拼写错误。</span><span class="sxs-lookup"><span data-stu-id="c929f-112">Spelling is automatically corrected and spelling errors are displayed for the selected shape.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c929f-113">备注</span><span class="sxs-lookup"><span data-stu-id="c929f-113">Remarks</span></span>

<span data-ttu-id="c929f-114">若要从另一个公式或程序按名称获取对 NoProofing 单元格的引用，请使用 **CellsU** 属性：</span><span class="sxs-lookup"><span data-stu-id="c929f-114">To get a reference to the NoProofing cell by name from another formula or from a program, by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c929f-115">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="c929f-115">Cell name:</span></span>  <br/> |<span data-ttu-id="c929f-116">NoProofing</span><span class="sxs-lookup"><span data-stu-id="c929f-116">NoProofing</span></span>  <br/> |
   
<span data-ttu-id="c929f-117">若要从程序按索引获取对 NoProofing 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="c929f-117">To get a reference to the NoProofing cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c929f-118">内容索引：</span><span class="sxs-lookup"><span data-stu-id="c929f-118">Section index:</span></span>  <br/> |<span data-ttu-id="c929f-119">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="c929f-119">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="c929f-120">行索引：</span><span class="sxs-lookup"><span data-stu-id="c929f-120">Row index:</span></span>  <br/> |<span data-ttu-id="c929f-121">**visRowMisc**</span><span class="sxs-lookup"><span data-stu-id="c929f-121">**visRowMisc**</span></span> <br/> |
|<span data-ttu-id="c929f-122">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="c929f-122">Cell index:</span></span>  <br/> |<span data-ttu-id="c929f-123">**visObjNoProofing**</span><span class="sxs-lookup"><span data-stu-id="c929f-123">**visObjNoProofing**</span></span> <br/> |
   

