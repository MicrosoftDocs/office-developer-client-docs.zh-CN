---
title: ReflectionSize 单元格（“Additional Effect Properties”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 7dfeb78e-a0fa-4492-b35f-70b1e2975d38
description: 确定相对于形状，从 0.0 100.0%的百分比反射的大小。 值为 0 %reflectionsize 单元格中的形状没有反射;值为 100%显示形状的完整镜像。
ms.openlocfilehash: b525a5f7379b2702dd7152d4eccf6dab1879a6cb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781034"
---
# <a name="reflectionsize-cell-additional-effect-properties-section"></a><span data-ttu-id="4d571-104">ReflectionSize 单元格（“Additional Effect Properties”部分）</span><span class="sxs-lookup"><span data-stu-id="4d571-104">ReflectionSize Cell (Additional Effect Properties Section)</span></span>

<span data-ttu-id="4d571-105">确定相对于形状，从 0.0 100.0%的百分比反射的大小。</span><span class="sxs-lookup"><span data-stu-id="4d571-105">Determines the size of the reflection relative to the shape, as a percentage from 0.0 to 100.0%.</span></span> <span data-ttu-id="4d571-106">值为 0 %reflectionsize**** 单元格中的形状没有反射;值为 100%显示形状的完整镜像。</span><span class="sxs-lookup"><span data-stu-id="4d571-106">A shape with a value of 0% in the **ReflectionSize** cell does not have a reflection; a value of 100% displays a complete mirror image of the shape.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="4d571-107">说明</span><span class="sxs-lookup"><span data-stu-id="4d571-107">Remarks</span></span>

<span data-ttu-id="4d571-108">要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**ReflectionSize**单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="4d571-108">To get a reference to the **ReflectionSize** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="4d571-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="4d571-109">Cell name:</span></span>  <br/> | <span data-ttu-id="4d571-110">ReflectionSize</span><span class="sxs-lookup"><span data-stu-id="4d571-110">ReflectionSize</span></span>  <br/> |
   
<span data-ttu-id="4d571-111">若要从某个程序按索引获取对**ReflectionSize**单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="4d571-111">To get a reference to the **ReflectionSize** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="4d571-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="4d571-112">Section index:</span></span>  <br/> |<span data-ttu-id="4d571-113">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="4d571-113">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="4d571-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="4d571-114">Row index:</span></span>  <br/> |<span data-ttu-id="4d571-115">**visRowOtherEffectProperties**</span><span class="sxs-lookup"><span data-stu-id="4d571-115">**visRowOtherEffectProperties**</span></span> <br/> |
| <span data-ttu-id="4d571-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="4d571-116">Cell index:</span></span>  <br/> |<span data-ttu-id="4d571-117">**visReflectionSize**</span><span class="sxs-lookup"><span data-stu-id="4d571-117">**visReflectionSize**</span></span> <br/> |
   

