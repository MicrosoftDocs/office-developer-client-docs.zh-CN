---
title: 关于错误值
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
f1_keywords:
- Vis_DSS.chm82251832
localization_priority: Normal
ms.assetid: 56430658-a798-c004-b4ba-363443f43ded
description: 错误值显示在含有该单元格的错误公式的单元格中。
ms.openlocfilehash: 5219becdd1af888e424a2fe33faa7df5a06f61fb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423865"
---
# <a name="about-error-values"></a><span data-ttu-id="c7482-103">关于错误值</span><span class="sxs-lookup"><span data-stu-id="c7482-103">About Error Values</span></span>

<span data-ttu-id="c7482-104">错误值显示在含有该单元格的错误公式的单元格中。</span><span class="sxs-lookup"><span data-stu-id="c7482-104">Error values are displayed in cells that have incorrect formulas for that cell.</span></span>
  
<span data-ttu-id="c7482-p101">如果一个公式引用了含有错误值的单元格，该公式也会显示一个错误值。您可以使用 ISERR、ISERRNA、ISERROR 或 ISERRVALUE 函数来查看错误值。</span><span class="sxs-lookup"><span data-stu-id="c7482-p101">If a formula references a cell that contains an error value, that formula also displays an error value. You can use the function ISERR, ISERRNA, ISERROR, or ISERRVALUE to look for error values.</span></span>
  
<span data-ttu-id="c7482-107">**错误值**</span><span class="sxs-lookup"><span data-stu-id="c7482-107">**Error values**</span></span>

||||
|:-----|:-----|:-----|
|<span data-ttu-id="c7482-108">**如果单元格显示**</span><span class="sxs-lookup"><span data-stu-id="c7482-108">**If the cell displays**</span></span> <br/> |<span data-ttu-id="c7482-109">**则公式包含**</span><span class="sxs-lookup"><span data-stu-id="c7482-109">**The formula includes**</span></span> <br/> |<span data-ttu-id="c7482-110">**示例**</span><span class="sxs-lookup"><span data-stu-id="c7482-110">**Example**</span></span> <br/> |
| <span data-ttu-id="c7482-111">#DIV/0!</span><span class="sxs-lookup"><span data-stu-id="c7482-111">#DIV/0!</span></span>  <br/> |<span data-ttu-id="c7482-112">被零除</span><span class="sxs-lookup"><span data-stu-id="c7482-112">Division by 0</span></span>  <br/> |<span data-ttu-id="c7482-113">10/0</span><span class="sxs-lookup"><span data-stu-id="c7482-113">10/0</span></span>  <br/> |
| <span data-ttu-id="c7482-114">#VALUE!</span><span class="sxs-lookup"><span data-stu-id="c7482-114">#VALUE!</span></span>  <br/> | <span data-ttu-id="c7482-115">错误的参数或操作数类型</span><span class="sxs-lookup"><span data-stu-id="c7482-115">An argument or operand of the wrong type</span></span>  <br/> | <span data-ttu-id="c7482-116">5 + "House"</span><span class="sxs-lookup"><span data-stu-id="c7482-116">5 + "House"</span></span>  <br/> |
| <span data-ttu-id="c7482-117">#REF!</span><span class="sxs-lookup"><span data-stu-id="c7482-117">#REF!</span></span>  <br/> | <span data-ttu-id="c7482-118">指向不存在的单元格的引用</span><span class="sxs-lookup"><span data-stu-id="c7482-118">A reference to a cell that does not exist</span></span>  <br/> | <span data-ttu-id="c7482-119">一个单元格引用另一个已不存在的单元格</span><span class="sxs-lookup"><span data-stu-id="c7482-119">A cell that refers to another cell that no longer exists</span></span>  <br/> |
| <span data-ttu-id="c7482-120">#NUM!</span><span class="sxs-lookup"><span data-stu-id="c7482-120">#NUM!</span></span>  <br/> | <span data-ttu-id="c7482-121">无效的数字</span><span class="sxs-lookup"><span data-stu-id="c7482-121">An invalid number</span></span>  <br/> | <span data-ttu-id="c7482-122">负数求平方根</span><span class="sxs-lookup"><span data-stu-id="c7482-122">Square root of a negative number</span></span>  <br/> |
| <span data-ttu-id="c7482-123">#N/A！</span><span class="sxs-lookup"><span data-stu-id="c7482-123">#N/A!</span></span>  <br/> | <span data-ttu-id="c7482-124">不可用值</span><span class="sxs-lookup"><span data-stu-id="c7482-124">Not an available value</span></span>  <br/> | <span data-ttu-id="c7482-125">NA( ) 函数</span><span class="sxs-lookup"><span data-stu-id="c7482-125">NA( ) function</span></span>  <br/> |
| <span data-ttu-id="c7482-126">#DIM！</span><span class="sxs-lookup"><span data-stu-id="c7482-126">#DIM!</span></span>  <br/> | <span data-ttu-id="c7482-127">超过维度范围的维度值 (有效值为整数 -128 \< = n \< = 127) </span><span class="sxs-lookup"><span data-stu-id="c7482-127">A dimensional value that exceeds the dimension range (valid powers are integers -128 \<= n \<= 127)</span></span>  <br/> <span data-ttu-id="c7482-128">对一个尺寸值的不当操作</span><span class="sxs-lookup"><span data-stu-id="c7482-128">A dimensional value used with an inappropriate operation</span></span>  <br/> |<span data-ttu-id="c7482-129">1in^100 \* 1in^100 (结果为 1in^200，超出维度范围) </span><span class="sxs-lookup"><span data-stu-id="c7482-129">1in^100 \* 1in^100 (the result is 1in^200, which is beyond the dimension range)</span></span>  <br/> <span data-ttu-id="c7482-130">5.2cm^1.5（不是整数次幂）</span><span class="sxs-lookup"><span data-stu-id="c7482-130">5.2cm^1.5 (not an integer power)</span></span>  <br/> |
   

