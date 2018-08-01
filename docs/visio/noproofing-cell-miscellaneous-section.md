---
title: NoProofing 单元格（“Miscellaneous”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 668f993c-b4d1-4762-9801-c578b17fdafd
description: 确定是否会自动更正拼写检查和拼写错误是否显示所选形状。 采用一个布尔值。
ms.openlocfilehash: 6c27e6740b547af83058519de8edd38fc3522b32
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/21/2018
ms.locfileid: "19780793"
---
# <a name="noproofing-cell-miscellaneous-section"></a><span data-ttu-id="c0414-104">NoProofing 单元格（“Miscellaneous”部分）</span><span class="sxs-lookup"><span data-stu-id="c0414-104">NoProofing Cell (Miscellaneous Section)</span></span>

<span data-ttu-id="c0414-105">确定是否会自动更正拼写检查和拼写错误是否显示所选形状。</span><span class="sxs-lookup"><span data-stu-id="c0414-105">Determines whether spelling is automatically corrected and whether spelling errors are displayed for the selected shape.</span></span> <span data-ttu-id="c0414-106">采用一个**布尔**值。</span><span class="sxs-lookup"><span data-stu-id="c0414-106">Takes a **Boolean** value.</span></span> 
  
|<span data-ttu-id="c0414-107">**值**</span><span class="sxs-lookup"><span data-stu-id="c0414-107">**Value**</span></span>|<span data-ttu-id="c0414-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="c0414-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c0414-109">TRUE</span><span class="sxs-lookup"><span data-stu-id="c0414-109">TRUE</span></span>  <br/> |<span data-ttu-id="c0414-110">不自动更正拼写检查和拼写错误不显示所选形状。</span><span class="sxs-lookup"><span data-stu-id="c0414-110">Spelling is not automatically corrected and spelling errors are not displayed for the selected shape.</span></span>  <br/> |
|<span data-ttu-id="c0414-111">FALSE</span><span class="sxs-lookup"><span data-stu-id="c0414-111">FALSE</span></span>  <br/> |<span data-ttu-id="c0414-112">自动更正拼写检查和拼写错误显示为所选形状。</span><span class="sxs-lookup"><span data-stu-id="c0414-112">Spelling is automatically corrected and spelling errors are displayed for the selected shape.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c0414-113">说明</span><span class="sxs-lookup"><span data-stu-id="c0414-113">Remarks</span></span>

<span data-ttu-id="c0414-114">若要获取 NoProofing 单元格的引用名称从另一个公式或从某个程序中，使用**CellsU**属性，使用：</span><span class="sxs-lookup"><span data-stu-id="c0414-114">To get a reference to the NoProofing cell by name from another formula or from a program, by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c0414-115">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="c0414-115">Cell name:</span></span>  <br/> |<span data-ttu-id="c0414-116">NoProofing</span><span class="sxs-lookup"><span data-stu-id="c0414-116">NoProofing</span></span>  <br/> |
   
<span data-ttu-id="c0414-117">若要从某个程序按索引获取对 NoProofing 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="c0414-117">To get a reference to the NoProofing cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c0414-118">内容索引：</span><span class="sxs-lookup"><span data-stu-id="c0414-118">Section index:</span></span>  <br/> |<span data-ttu-id="c0414-119">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="c0414-119">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="c0414-120">行索引：</span><span class="sxs-lookup"><span data-stu-id="c0414-120">Row index:</span></span>  <br/> |<span data-ttu-id="c0414-121">**visRowMisc**</span><span class="sxs-lookup"><span data-stu-id="c0414-121">**visRowMisc**</span></span> <br/> |
|<span data-ttu-id="c0414-122">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="c0414-122">Cell index:</span></span>  <br/> |<span data-ttu-id="c0414-123">**visObjNoProofing**</span><span class="sxs-lookup"><span data-stu-id="c0414-123">**visObjNoProofing**</span></span> <br/> |
   

