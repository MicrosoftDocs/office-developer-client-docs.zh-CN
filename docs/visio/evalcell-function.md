---
title: EVALCELL 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4aa3a1c9-dec9-5eb0-5743-0534c0b3bb5f
description: 获取一个对包含自定义函数以及一个或多个作为参数传递给自定义函数的名称值对的单元格的引用 (可选)。 返回给定了指定参数和值的自定义函数的计算结果。
ms.openlocfilehash: 4ad6645862d620a36b90e4f46d09588d7e83fcc1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329069"
---
# <a name="evalcell-function"></a><span data-ttu-id="5f169-104">EVALCELL 函数</span><span class="sxs-lookup"><span data-stu-id="5f169-104">EVALCELL Function</span></span>

<span data-ttu-id="5f169-105">获取一个对包含自定义函数以及一个或多个作为参数传递给自定义函数的名称值对的单元格的引用 (可选)。</span><span class="sxs-lookup"><span data-stu-id="5f169-105">Takes a reference to a cell that contains a custom function as well as one or more name-value pairs to pass to the custom function as arguments (optional).</span></span> <span data-ttu-id="5f169-106">返回给定了指定参数和值的自定义函数的计算结果。</span><span class="sxs-lookup"><span data-stu-id="5f169-106">Returns the calculated result of the custom function given the specified arguments and values.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="5f169-107">语法</span><span class="sxs-lookup"><span data-stu-id="5f169-107">Syntax</span></span>

<span data-ttu-id="5f169-108">EVALCELL (\* \* *cellRef* \* *, [* \* *arg1Name, arg1* \* *], [* \* *arg2Name, arg2* \* \*],...)</span><span class="sxs-lookup"><span data-stu-id="5f169-108">EVALCELL(\*\* *cellRef* \*\*,[ \*\* *arg1Name,arg1* \*\* ],[ \*\* *arg2Name,arg2* \*\* ],…)</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="5f169-109">参数</span><span class="sxs-lookup"><span data-stu-id="5f169-109">Parameters</span></span>

|<span data-ttu-id="5f169-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="5f169-110">**Name**</span></span>|<span data-ttu-id="5f169-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="5f169-111">**Required/Optional**</span></span>|<span data-ttu-id="5f169-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="5f169-112">**Data Type**</span></span>|<span data-ttu-id="5f169-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="5f169-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="5f169-114">_cellRef_</span><span class="sxs-lookup"><span data-stu-id="5f169-114">_cellRef_</span></span> <br/> |<span data-ttu-id="5f169-115">必需</span><span class="sxs-lookup"><span data-stu-id="5f169-115">Required</span></span>  <br/> |<span data-ttu-id="5f169-116">**String**</span><span class="sxs-lookup"><span data-stu-id="5f169-116">**String**</span></span> <br/> |<span data-ttu-id="5f169-117">对包含自定义函数的单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="5f169-117">A reference to the cell that contains the custom function.</span></span> <span data-ttu-id="5f169-118">允许工作表交叉引用。</span><span class="sxs-lookup"><span data-stu-id="5f169-118">Cross-sheet references are allowed.</span></span>  <br/> |
| <span data-ttu-id="5f169-119">_arg1Name_</span><span class="sxs-lookup"><span data-stu-id="5f169-119">_arg1Name_</span></span> <br/> |<span data-ttu-id="5f169-120">可选</span><span class="sxs-lookup"><span data-stu-id="5f169-120">Optional</span></span>  <br/> |<span data-ttu-id="5f169-121">**字符串**</span><span class="sxs-lookup"><span data-stu-id="5f169-121">**String**</span></span> <br/> |<span data-ttu-id="5f169-122">要传递给自定义函数的第一个参数的名称。</span><span class="sxs-lookup"><span data-stu-id="5f169-122">The name of the first argument to be passed to the custom function.</span></span> <span data-ttu-id="5f169-123">可以包含空格。</span><span class="sxs-lookup"><span data-stu-id="5f169-123">Spaces are allowed.</span></span>  <br/> |
| <span data-ttu-id="5f169-124">_arg1_</span><span class="sxs-lookup"><span data-stu-id="5f169-124">_arg1_</span></span> <br/> |<span data-ttu-id="5f169-125">可选</span><span class="sxs-lookup"><span data-stu-id="5f169-125">Optional</span></span>  <br/> |<span data-ttu-id="5f169-126">**相同**</span><span class="sxs-lookup"><span data-stu-id="5f169-126">**Varies**</span></span> <br/> |<span data-ttu-id="5f169-127">_arg1_参数的值。</span><span class="sxs-lookup"><span data-stu-id="5f169-127">Value of the  _arg1_ parameter.</span></span>  <br/> |
| <span data-ttu-id="5f169-128">_arg2Name_</span><span class="sxs-lookup"><span data-stu-id="5f169-128">_arg2Name_</span></span> <br/> |<span data-ttu-id="5f169-129">可选</span><span class="sxs-lookup"><span data-stu-id="5f169-129">Optional</span></span>  <br/> |<span data-ttu-id="5f169-130">**字符串**</span><span class="sxs-lookup"><span data-stu-id="5f169-130">**String**</span></span> <br/> |<span data-ttu-id="5f169-131">要传递给自定义函数的第二个参数的名称。</span><span class="sxs-lookup"><span data-stu-id="5f169-131">The name of the second argument to be passed to the custom function.</span></span> <span data-ttu-id="5f169-132">可以包含空格。</span><span class="sxs-lookup"><span data-stu-id="5f169-132">Spaces are allowed.</span></span>  <br/> |
| <span data-ttu-id="5f169-133">_arg2_</span><span class="sxs-lookup"><span data-stu-id="5f169-133">_arg2_</span></span> <br/> |<span data-ttu-id="5f169-134">可选</span><span class="sxs-lookup"><span data-stu-id="5f169-134">Optional</span></span>  <br/> |<span data-ttu-id="5f169-135">**相同**</span><span class="sxs-lookup"><span data-stu-id="5f169-135">**Varies**</span></span> <br/> |<span data-ttu-id="5f169-136">_arg2_参数的值。</span><span class="sxs-lookup"><span data-stu-id="5f169-136">Value of the  _arg2_ parameter.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="5f169-137">返回值</span><span class="sxs-lookup"><span data-stu-id="5f169-137">Return value</span></span>

<span data-ttu-id="5f169-138">帐号</span><span class="sxs-lookup"><span data-stu-id="5f169-138">Number</span></span>
  
## <a name="remarks"></a><span data-ttu-id="5f169-139">注解</span><span class="sxs-lookup"><span data-stu-id="5f169-139">Remarks</span></span>

<span data-ttu-id="5f169-140">调用单元格不必指定自定义函数使用的每一个参数。</span><span class="sxs-lookup"><span data-stu-id="5f169-140">The calling cell does not have to specify every argument used by the custom function.</span></span> 
  
## <a name="example"></a><span data-ttu-id="5f169-141">示例</span><span class="sxs-lookup"><span data-stu-id="5f169-141">Example</span></span>

<span data-ttu-id="5f169-142">以下示例显示了如何将 EVALCELL 函数与 ARG 函数一起使用，以查找一组三个值的中间值。</span><span class="sxs-lookup"><span data-stu-id="5f169-142">The following example shows how to use the EVALCELL function in conjunction with the ARG function to find the middle value from a set of three values.</span></span> 
  
<span data-ttu-id="5f169-143">在表达式单元格中，放置定义自定义函数的以下代码：</span><span class="sxs-lookup"><span data-stu-id="5f169-143">In the expression cell, place the following code that defines the custom function:</span></span> 
  
```vb
User.MiddleValue = IF(ARG("A")>ARG("B"),IF(ARG("B")>ARG("C"),ARG("B"),IF(ARG("A")>ARG("C"),ARG("C"),ARG("A"))),IF(ARG("A")>ARG("C"),ARG("A"),IF(ARG("B")>ARG("C"),ARG("C"),ARG("B"))))
```

<span data-ttu-id="5f169-144">在调用单元格中，放置调用自定义函数的以下代码：</span><span class="sxs-lookup"><span data-stu-id="5f169-144">In the calling cells, place the following code that calls the custom function:</span></span>
  
```vb
User.Middle1 = EVALCELL(User.MiddleValue,"A",3,"B",9,"C",5) 
User.Middle2 = EVALCELL(User.MiddleValue,"A",12,"B",0,"C",21) 

```


