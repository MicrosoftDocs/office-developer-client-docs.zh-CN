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
ms.openlocfilehash: 301f566151362727daf8236f8ca88fca8758054e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779598"
---
# <a name="about-error-values"></a><span data-ttu-id="6df4e-103">关于错误值</span><span class="sxs-lookup"><span data-stu-id="6df4e-103">About Error Values</span></span>

<span data-ttu-id="6df4e-104">错误值显示在含有该单元格的错误公式的单元格中。</span><span class="sxs-lookup"><span data-stu-id="6df4e-104">Error values are displayed in cells that have incorrect formulas for that cell.</span></span>
  
<span data-ttu-id="6df4e-p101">如果一个公式引用了含有错误值的单元格，该公式也会显示一个错误值。您可以使用 ISERR、ISERRNA、ISERROR 或 ISERRVALUE 函数来查看错误值。</span><span class="sxs-lookup"><span data-stu-id="6df4e-p101">If a formula references a cell that contains an error value, that formula also displays an error value. You can use the function ISERR, ISERRNA, ISERROR, or ISERRVALUE to look for error values.</span></span>
  
<span data-ttu-id="6df4e-107">**错误值**</span><span class="sxs-lookup"><span data-stu-id="6df4e-107">**Error values**</span></span>

||||
|:-----|:-----|:-----|
|<span data-ttu-id="6df4e-108">**如果单元格显示**</span><span class="sxs-lookup"><span data-stu-id="6df4e-108">**If the cell displays**</span></span> <br/> |<span data-ttu-id="6df4e-109">**则公式包含**</span><span class="sxs-lookup"><span data-stu-id="6df4e-109">**The formula includes**</span></span> <br/> |<span data-ttu-id="6df4e-110">**示例**</span><span class="sxs-lookup"><span data-stu-id="6df4e-110">**Example**</span></span> <br/> |
| <span data-ttu-id="6df4e-111">#DIV/0!</span><span class="sxs-lookup"><span data-stu-id="6df4e-111">#DIV/0!</span></span>  <br/> |<span data-ttu-id="6df4e-112">
                被零除
</span><span class="sxs-lookup"><span data-stu-id="6df4e-112">Division by 0</span></span>  <br/> |<span data-ttu-id="6df4e-113">10/0</span><span class="sxs-lookup"><span data-stu-id="6df4e-113">10/0</span></span>  <br/> |
| <span data-ttu-id="6df4e-114">#VALUE!</span><span class="sxs-lookup"><span data-stu-id="6df4e-114">#VALUE!</span></span>  <br/> | <span data-ttu-id="6df4e-115">
                
                
                错误的参数或操作数类型
</span><span class="sxs-lookup"><span data-stu-id="6df4e-115">An argument or operand of the wrong type</span></span>  <br/> | <span data-ttu-id="6df4e-116">
                
                
                5 + "House"
</span><span class="sxs-lookup"><span data-stu-id="6df4e-116">5 + "House"</span></span>  <br/> |
| <span data-ttu-id="6df4e-117">#REF!</span><span class="sxs-lookup"><span data-stu-id="6df4e-117">#REF!</span></span>  <br/> | <span data-ttu-id="6df4e-118">
                
                
                指向不存在的单元格的引用
</span><span class="sxs-lookup"><span data-stu-id="6df4e-118">A reference to a cell that does not exist</span></span>  <br/> | <span data-ttu-id="6df4e-119">
                
                
                一个单元格引用另一个已不存在的单元格
</span><span class="sxs-lookup"><span data-stu-id="6df4e-119">A cell that refers to another cell that no longer exists</span></span>  <br/> |
| <span data-ttu-id="6df4e-120">#NUM!</span><span class="sxs-lookup"><span data-stu-id="6df4e-120">#NUM!</span></span>  <br/> | <span data-ttu-id="6df4e-121">
                
                
                无效的数字
</span><span class="sxs-lookup"><span data-stu-id="6df4e-121">An invalid number</span></span>  <br/> | <span data-ttu-id="6df4e-122">
                
                
                负数求平方根
</span><span class="sxs-lookup"><span data-stu-id="6df4e-122">Square root of a negative number</span></span>  <br/> |
| <span data-ttu-id="6df4e-123">#N/A!</span><span class="sxs-lookup"><span data-stu-id="6df4e-123">#N/A!</span></span>  <br/> | <span data-ttu-id="6df4e-124">不是一个可用的值</span><span class="sxs-lookup"><span data-stu-id="6df4e-124">Not an available value</span></span>  <br/> | <span data-ttu-id="6df4e-125">
                
                
                NA( ) 函数
</span><span class="sxs-lookup"><span data-stu-id="6df4e-125">NA( ) function</span></span>  <br/> |
| <span data-ttu-id="6df4e-126">#DIM ！</span><span class="sxs-lookup"><span data-stu-id="6df4e-126">#DIM!</span></span>  <br/> | <span data-ttu-id="6df4e-127">超过尺寸范围的尺寸值 (有效的幂是整数-128 \<= n \<= 127)</span><span class="sxs-lookup"><span data-stu-id="6df4e-127">A dimensional value that exceeds the dimension range (valid powers are integers -128 \<= n \<= 127)</span></span>  <br/> <span data-ttu-id="6df4e-128">对一个尺寸值的不当操作
</span><span class="sxs-lookup"><span data-stu-id="6df4e-128">A dimensional value used with an inappropriate operation</span></span>  <br/> |<span data-ttu-id="6df4e-129">1in ^100 \* 1in ^100 (结果是 1in ^200，超出了尺寸范围)</span><span class="sxs-lookup"><span data-stu-id="6df4e-129">1in^100 \* 1in^100 (the result is 1in^200, which is beyond the dimension range)</span></span>  <br/> <span data-ttu-id="6df4e-130">5.2cm^1.5（不是整数次幂）
</span><span class="sxs-lookup"><span data-stu-id="6df4e-130">5.2cm^1.5 (not an integer power)</span></span>  <br/> |
   

