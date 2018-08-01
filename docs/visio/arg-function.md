---
title: ARG 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 781369e1-fade-ec10-7c51-0f921b5c3b76
description: 指定调用单元格可以传递到自定义函数的参数，以及当调用单元格未传递该参数的值时自定义函数返回的默认值。返回调用单元格指定的值以及匹配的 argName 参数。
ms.openlocfilehash: 3d0e126e0fa075ff2a07773197c1973e6b0249d3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779674"
---
# <a name="arg-function"></a><span data-ttu-id="03296-104">ARG 函数</span><span class="sxs-lookup"><span data-stu-id="03296-104">ARG Function</span></span>

<span data-ttu-id="03296-p102">指定调用单元格可以传递到自定义函数的参数，以及当调用单元格未传递该参数的值时自定义函数返回的默认值。返回调用单元格指定的值以及匹配的 argName 参数。</span><span class="sxs-lookup"><span data-stu-id="03296-p102">Specifies an argument that the calling cell can pass to a custom function, as well as the default value returned by the custom function if the calling cell does not pass in a value for the argument. Returns the value specified by the calling cell and the matching argName parameter.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="03296-107">语法</span><span class="sxs-lookup"><span data-stu-id="03296-107">Syntax</span></span>

<span data-ttu-id="03296-108">ARG (* * *argName* * *，[* * *defaultValue* * *])</span><span class="sxs-lookup"><span data-stu-id="03296-108">ARG(** *argName* **,[ ** *defaultValue* ** ])</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="03296-109">参数</span><span class="sxs-lookup"><span data-stu-id="03296-109">Parameters</span></span>

|<span data-ttu-id="03296-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="03296-110">**Name**</span></span>|<span data-ttu-id="03296-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="03296-111">**Required/Optional**</span></span>|<span data-ttu-id="03296-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="03296-112">**Data Type**</span></span>|<span data-ttu-id="03296-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="03296-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="03296-114">_argName_</span><span class="sxs-lookup"><span data-stu-id="03296-114">_argName_</span></span> <br/> |<span data-ttu-id="03296-115">必需</span><span class="sxs-lookup"><span data-stu-id="03296-115">Required</span></span>  <br/> |<span data-ttu-id="03296-116">**字符串**</span><span class="sxs-lookup"><span data-stu-id="03296-116">**String**</span></span> <br/> |<span data-ttu-id="03296-117">调用单元格可以传递给该函数的参数的名称。</span><span class="sxs-lookup"><span data-stu-id="03296-117">The name of an argument that the calling cell can pass into the function.</span></span>  <br/> |
| <span data-ttu-id="03296-118">_默认值_</span><span class="sxs-lookup"><span data-stu-id="03296-118">_default Value_</span></span> <br/> |<span data-ttu-id="03296-119">可选</span><span class="sxs-lookup"><span data-stu-id="03296-119">Optional</span></span>  <br/> |<span data-ttu-id="03296-120">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="03296-120">**Numeric**</span></span> <br/> |<span data-ttu-id="03296-121">如果调用单元格没有传递_argName_参数的值由 ARG 返回的值。</span><span class="sxs-lookup"><span data-stu-id="03296-121">The value returned by ARG if the calling cell did not pass in a value for the  _argName_ parameter.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="03296-122">注解</span><span class="sxs-lookup"><span data-stu-id="03296-122">Remarks</span></span>

<span data-ttu-id="03296-p103">作为形状开发人员，您可以通过将某个表达式放置在一个单元格中并从一个或多个其他单元格调用该表达式来创建自定义函数。该表达式可以包括文字字符串、ShapeSheet 函数和单元格引用。该表达式也可以包括由调用单元格传递的特定参数。</span><span class="sxs-lookup"><span data-stu-id="03296-p103">As a shape developer, you can create custom functions by placing an expression in one cell and calling that expression from one or more other cells. The expression can include literal strings, ShapeSheet functions, and cell references. The expression can also include specific arguments that are passed in by the calling cell.</span></span> 
  
<span data-ttu-id="03296-126">调用单元格指定的单元格包含自定义的函数，以及任何要传递给函数的参数。</span><span class="sxs-lookup"><span data-stu-id="03296-126">The calling cell specifies the cell that contains the custom function as well as any arguments that it wants to pass to the function.</span></span> <span data-ttu-id="03296-127">计算表达式单元格并返回到调用单元格的结果。</span><span class="sxs-lookup"><span data-stu-id="03296-127">The expression cell is evaluated and the result returned to the calling cell.</span></span>
  
## <a name="example"></a><span data-ttu-id="03296-128">示例</span><span class="sxs-lookup"><span data-stu-id="03296-128">Example</span></span>

<span data-ttu-id="03296-129">以下示例显示了如何将 ARG 函数与 EVALCELL 函数一起使用，以查找一组三个值的中间值。</span><span class="sxs-lookup"><span data-stu-id="03296-129">The following example shows how to use the ARG function in conjunction with the EVALCELL function to find the middle value from a set of three values.</span></span> 
  
<span data-ttu-id="03296-130">在表达式单元格中，放置定义自定义函数的以下代码：</span><span class="sxs-lookup"><span data-stu-id="03296-130">In the expression cell, place the following code that defines the custom function:</span></span> 
  
```vb
User.MiddleValue = IF(ARG("A")>ARG("B"),IF(ARG("B")>ARG("C"),ARG("B"),IF(ARG("A")>ARG("C"),ARG("C"),ARG("A"))),IF(ARG("A")>ARG("C"),ARG("A"),IF(ARG("B")>ARG("C"),ARG("C"),ARG("B"))))
```

<span data-ttu-id="03296-131">在调用单元格中，放置调用自定义函数的以下代码：</span><span class="sxs-lookup"><span data-stu-id="03296-131">In the calling cells, place the following code that calls the custom function:</span></span>
  
```vb
User.Middle1 = EVALCELL(User.MiddleValue,"A",3,"B",9,"C",5) 
User.Middle2 = EVALCELL(User.MiddleValue,"A",12,"B",0,"C",21) 

```


