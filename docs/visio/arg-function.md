---
title: ARG 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 781369e1-fade-ec10-7c51-0f921b5c3b76
description: 指定调用单元格可以传递到自定义函数的参数，以及当调用单元格未传递该参数的值时自定义函数返回的默认值。返回调用单元格指定的值以及匹配的 argName 参数。
ms.openlocfilehash: f85c3dc4a49878b034674330f272a63e79c17d49
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422724"
---
# <a name="arg-function"></a><span data-ttu-id="d4cb6-104">ARG 函数</span><span class="sxs-lookup"><span data-stu-id="d4cb6-104">ARG Function</span></span>

<span data-ttu-id="d4cb6-p102">指定调用单元格可以传递到自定义函数的参数，以及当调用单元格未传递该参数的值时自定义函数返回的默认值。返回调用单元格指定的值以及匹配的 argName 参数。</span><span class="sxs-lookup"><span data-stu-id="d4cb6-p102">Specifies an argument that the calling cell can pass to a custom function, as well as the default value returned by the custom function if the calling cell does not pass in a value for the argument. Returns the value specified by the calling cell and the matching argName parameter.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="d4cb6-107">语法</span><span class="sxs-lookup"><span data-stu-id="d4cb6-107">Syntax</span></span>

<span data-ttu-id="d4cb6-108">ARG (\* \* *argName* \* *, [* \* *defaultValue* \* \*])</span><span class="sxs-lookup"><span data-stu-id="d4cb6-108">ARG(\*\* *argName* \*\*,[ \*\* *defaultValue* \*\* ])</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="d4cb6-109">参数</span><span class="sxs-lookup"><span data-stu-id="d4cb6-109">Parameters</span></span>

|<span data-ttu-id="d4cb6-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="d4cb6-110">**Name**</span></span>|<span data-ttu-id="d4cb6-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="d4cb6-111">**Required/Optional**</span></span>|<span data-ttu-id="d4cb6-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="d4cb6-112">**Data Type**</span></span>|<span data-ttu-id="d4cb6-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="d4cb6-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="d4cb6-114">_argName_</span><span class="sxs-lookup"><span data-stu-id="d4cb6-114">_argName_</span></span> <br/> |<span data-ttu-id="d4cb6-115">必需</span><span class="sxs-lookup"><span data-stu-id="d4cb6-115">Required</span></span>  <br/> |<span data-ttu-id="d4cb6-116">**String**</span><span class="sxs-lookup"><span data-stu-id="d4cb6-116">**String**</span></span> <br/> |<span data-ttu-id="d4cb6-117">调用单元格可以传递给该函数的参数的名称。</span><span class="sxs-lookup"><span data-stu-id="d4cb6-117">The name of an argument that the calling cell can pass into the function.</span></span>  <br/> |
| <span data-ttu-id="d4cb6-118">_默认值_</span><span class="sxs-lookup"><span data-stu-id="d4cb6-118">_default Value_</span></span> <br/> |<span data-ttu-id="d4cb6-119">可选</span><span class="sxs-lookup"><span data-stu-id="d4cb6-119">Optional</span></span>  <br/> |<span data-ttu-id="d4cb6-120">**数值**</span><span class="sxs-lookup"><span data-stu-id="d4cb6-120">**Numeric**</span></span> <br/> |<span data-ttu-id="d4cb6-121">如果调用单元格未传入_argName_参数的值, 则由 ARG 返回的值。</span><span class="sxs-lookup"><span data-stu-id="d4cb6-121">The value returned by ARG if the calling cell did not pass in a value for the  _argName_ parameter.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d4cb6-122">说明</span><span class="sxs-lookup"><span data-stu-id="d4cb6-122">Remarks</span></span>

<span data-ttu-id="d4cb6-p103">作为形状开发人员，您可以通过将某个表达式放置在一个单元格中并从一个或多个其他单元格调用该表达式来创建自定义函数。该表达式可以包括文字字符串、ShapeSheet 函数和单元格引用。该表达式也可以包括由调用单元格传递的特定参数。</span><span class="sxs-lookup"><span data-stu-id="d4cb6-p103">As a shape developer, you can create custom functions by placing an expression in one cell and calling that expression from one or more other cells. The expression can include literal strings, ShapeSheet functions, and cell references. The expression can also include specific arguments that are passed in by the calling cell.</span></span> 
  
<span data-ttu-id="d4cb6-126">调用单元格指定包含自定义函数以及它希望传递给该函数的任何参数的单元格。</span><span class="sxs-lookup"><span data-stu-id="d4cb6-126">The calling cell specifies the cell that contains the custom function as well as any arguments that it wants to pass to the function.</span></span> <span data-ttu-id="d4cb6-127">将会对表达式单元格进行计算，并将计算结果返回到调用单元格。</span><span class="sxs-lookup"><span data-stu-id="d4cb6-127">The expression cell is evaluated and the result returned to the calling cell.</span></span>
  
## <a name="example"></a><span data-ttu-id="d4cb6-128">示例</span><span class="sxs-lookup"><span data-stu-id="d4cb6-128">Example</span></span>

<span data-ttu-id="d4cb6-129">以下示例显示了如何将 ARG 函数与 EVALCELL 函数一起使用，以查找一组三个值的中间值。</span><span class="sxs-lookup"><span data-stu-id="d4cb6-129">The following example shows how to use the ARG function in conjunction with the EVALCELL function to find the middle value from a set of three values.</span></span> 
  
<span data-ttu-id="d4cb6-130">在表达式单元格中，放置定义自定义函数的以下代码：</span><span class="sxs-lookup"><span data-stu-id="d4cb6-130">In the expression cell, place the following code that defines the custom function:</span></span> 
  
```vb
User.MiddleValue = IF(ARG("A")>ARG("B"),IF(ARG("B")>ARG("C"),ARG("B"),IF(ARG("A")>ARG("C"),ARG("C"),ARG("A"))),IF(ARG("A")>ARG("C"),ARG("A"),IF(ARG("B")>ARG("C"),ARG("C"),ARG("B"))))
```

<span data-ttu-id="d4cb6-131">在调用单元格中，放置调用自定义函数的以下代码：</span><span class="sxs-lookup"><span data-stu-id="d4cb6-131">In the calling cells, place the following code that calls the custom function:</span></span>
  
```vb
User.Middle1 = EVALCELL(User.MiddleValue,"A",3,"B",9,"C",5) 
User.Middle2 = EVALCELL(User.MiddleValue,"A",12,"B",0,"C",21) 

```


