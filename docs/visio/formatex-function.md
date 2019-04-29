---
title: FORMATEX 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251590
localization_priority: Normal
ms.assetid: d375c971-fee2-baa3-dc4f-a26018e70e8a
description: 以字符串的形式返回在 srcUnit 中计算的表达式的结果, 该字符串根据 dstUnit 中表示的格式设置格式。
ms.openlocfilehash: e341cbcb16cc273f0413f98c195f77ad08946ab1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430964"
---
# <a name="formatex-function"></a><span data-ttu-id="e7c96-103">FORMATEX 函数</span><span class="sxs-lookup"><span data-stu-id="e7c96-103">FORMATEX Function</span></span>

<span data-ttu-id="e7c96-104">以字符串的形式返回在 srcUnit 中计算的表达式的结果, 该字符串根据 dstUnit 中表示的格式设置格式。</span><span class="sxs-lookup"><span data-stu-id="e7c96-104">Returns the result of expression evaluated in srcUnit as a string formatted according to format expressed in dstUnit.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="e7c96-105">语法</span><span class="sxs-lookup"><span data-stu-id="e7c96-105">Syntax</span></span>

<span data-ttu-id="e7c96-106">FORMATEX (\* **表达式** *、"* \* *format* \* *"、[* \* *srcUnit* *]、[* \* *dstUnit* \* *]、[* \* *langID* \* \*] [, \* \* *calID* \* \*])</span><span class="sxs-lookup"><span data-stu-id="e7c96-106">FORMATEX(\*\* *expression* \*\*," \*\* *format* \*\* ",[ \*\* *srcUnit* \*\* ],[ \*\* *dstUnit* \*\* ],[ \*\* *langID* \*\* ][, \*\* *calID* \*\* ])</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="e7c96-107">参数</span><span class="sxs-lookup"><span data-stu-id="e7c96-107">Parameters</span></span>

|<span data-ttu-id="e7c96-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="e7c96-108">**Name**</span></span>|<span data-ttu-id="e7c96-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="e7c96-109">**Required/Optional**</span></span>|<span data-ttu-id="e7c96-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e7c96-110">**Data Type**</span></span>|<span data-ttu-id="e7c96-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="e7c96-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="e7c96-112">_expression_</span><span class="sxs-lookup"><span data-stu-id="e7c96-112">_expression_</span></span> <br/> |<span data-ttu-id="e7c96-113">必需</span><span class="sxs-lookup"><span data-stu-id="e7c96-113">Required</span></span>  <br/> |<span data-ttu-id="e7c96-114">**String**</span><span class="sxs-lookup"><span data-stu-id="e7c96-114">**String**</span></span> <br/> |<span data-ttu-id="e7c96-115">常量、运算符、函数和对 ShapeSheet 单元格的引用的组合，其结果为一个值。</span><span class="sxs-lookup"><span data-stu-id="e7c96-115">A combination of constants, operators, functions, and references to ShapeSheet cells that results in a value.</span></span>  <br/> |
| <span data-ttu-id="e7c96-116">_format_</span><span class="sxs-lookup"><span data-stu-id="e7c96-116">_format_</span></span> <br/> |<span data-ttu-id="e7c96-117">必需</span><span class="sxs-lookup"><span data-stu-id="e7c96-117">Required</span></span>  <br/> |<span data-ttu-id="e7c96-118">**String**</span><span class="sxs-lookup"><span data-stu-id="e7c96-118">**String**</span></span> <br/> |<span data-ttu-id="e7c96-119">用于设置字符串格式的格式图片。</span><span class="sxs-lookup"><span data-stu-id="e7c96-119">The format picture used to format the string.</span></span> <span data-ttu-id="e7c96-120">有关设置图片格式的详细信息, 请参阅[关于格式图片](about-format-pictures.md)。</span><span class="sxs-lookup"><span data-stu-id="e7c96-120">For more information about format pictures, see [About Format Pictures](about-format-pictures.md).</span></span>  <br/> |
| <span data-ttu-id="e7c96-121">_srcUnit_</span><span class="sxs-lookup"><span data-stu-id="e7c96-121">_srcUnit_</span></span> <br/> |<span data-ttu-id="e7c96-122">可选</span><span class="sxs-lookup"><span data-stu-id="e7c96-122">Optional</span></span>  <br/> |<span data-ttu-id="e7c96-123">**字符串**</span><span class="sxs-lookup"><span data-stu-id="e7c96-123">**String**</span></span> <br/> | <span data-ttu-id="e7c96-124">用来计算 expression 的单位（in、cm 等）。</span><span class="sxs-lookup"><span data-stu-id="e7c96-124">Units used to evaluate expression (in, cm, and so forth).</span></span>  <br/> |
| <span data-ttu-id="e7c96-125">_dstUnit_</span><span class="sxs-lookup"><span data-stu-id="e7c96-125">_dstUnit_</span></span> <br/> |<span data-ttu-id="e7c96-126">可选</span><span class="sxs-lookup"><span data-stu-id="e7c96-126">Optional</span></span>  <br/> |<span data-ttu-id="e7c96-127">**字符串**</span><span class="sxs-lookup"><span data-stu-id="e7c96-127">**String**</span></span> <br/> |<span data-ttu-id="e7c96-128">用于 expression 结果的单位（in、cm 等）。</span><span class="sxs-lookup"><span data-stu-id="e7c96-128">Units to use for the result of expression (in, cm, and so forth).</span></span>  <br/> |
| <span data-ttu-id="e7c96-129">_langID_</span><span class="sxs-lookup"><span data-stu-id="e7c96-129">_langID_</span></span> <br/> |<span data-ttu-id="e7c96-130">可选</span><span class="sxs-lookup"><span data-stu-id="e7c96-130">Optional</span></span>  <br/> |<span data-ttu-id="e7c96-131">**Number**</span><span class="sxs-lookup"><span data-stu-id="e7c96-131">**Number**</span></span> <br/> |<span data-ttu-id="e7c96-132">设置 Microsoft Office System 日期/时间图片的格式时所使用的语言。</span><span class="sxs-lookup"><span data-stu-id="e7c96-132">The language used when formatting Microsoft Office System date/time pictures.</span></span>  <br/> |
| <span data-ttu-id="e7c96-133">_calID_</span><span class="sxs-lookup"><span data-stu-id="e7c96-133">_calID_</span></span> <br/> |<span data-ttu-id="e7c96-134">可选</span><span class="sxs-lookup"><span data-stu-id="e7c96-134">Optional</span></span>  <br/> |<span data-ttu-id="e7c96-135">**Number**</span><span class="sxs-lookup"><span data-stu-id="e7c96-135">**Number**</span></span> <br/> |<span data-ttu-id="e7c96-136">设置 Microsoft Office System 日期/时间图片的格式时所使用的日历。</span><span class="sxs-lookup"><span data-stu-id="e7c96-136">The calendar used when formatting Microsoft Office System date/time pictures.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="e7c96-137">返回值</span><span class="sxs-lookup"><span data-stu-id="e7c96-137">Return value</span></span>

<span data-ttu-id="e7c96-138">String</span><span class="sxs-lookup"><span data-stu-id="e7c96-138">String</span></span>
  
## <a name="remarks"></a><span data-ttu-id="e7c96-139">说明</span><span class="sxs-lookup"><span data-stu-id="e7c96-139">Remarks</span></span>

<span data-ttu-id="e7c96-140">表达式的类型和格式图片中指定的类型将控制返回的字符串的行为。</span><span class="sxs-lookup"><span data-stu-id="e7c96-140">The type of the expression and the type specified in the format picture govern the behavior of the returned string.</span></span> <span data-ttu-id="e7c96-141">format 必须适合该表达式的类型。</span><span class="sxs-lookup"><span data-stu-id="e7c96-141">The format must be appropriate for the type of expression.</span></span>
  
<span data-ttu-id="e7c96-142">srcUnit 参数用于为非类型化的表达式的结果（如 3 + 4）提供单位。</span><span class="sxs-lookup"><span data-stu-id="e7c96-142">The srcUnit argument is used to scale untyped expression results, such as 3 + 4.</span></span> <span data-ttu-id="e7c96-143">如果 expression 的结果具有显式类型，如 3 ft + 8 ft，则将忽略 srcUnit。</span><span class="sxs-lookup"><span data-stu-id="e7c96-143">If the result of expression has an explicit type, such as 3 ft + 8 ft, then srcUnit is ignored.</span></span>
  
<span data-ttu-id="e7c96-144">dstUnit 参数用于指定带格式的结果所使用的单位。</span><span class="sxs-lookup"><span data-stu-id="e7c96-144">The dstUnit argument is used to specify the units used for the formatted result.</span></span> <span data-ttu-id="e7c96-145">如果未指定 dstUnit，则将使用表达式结果的单位。</span><span class="sxs-lookup"><span data-stu-id="e7c96-145">If dstUnit is not specified, the units for the result of the expression are used.</span></span>
  
<span data-ttu-id="e7c96-146">在以下情况下将返回错误：expression 的结果和 format 中预期的类型不同；format 中出现语法错误；无法识别作为 srcUnit 或 dstUnit 传递的单位。</span><span class="sxs-lookup"><span data-stu-id="e7c96-146">Returns an error if the result of expression and the type expected in format are of a different kind, if there are syntax errors in format, or if it does not recognize the units passed as srcUnit or dstUnit.</span></span>
  
## <a name="example"></a><span data-ttu-id="e7c96-147">示例</span><span class="sxs-lookup"><span data-stu-id="e7c96-147">Example</span></span>

<span data-ttu-id="e7c96-148">FORMATEX(5.5, "0.00 u", "cm", "ft")</span><span class="sxs-lookup"><span data-stu-id="e7c96-148">FORMATEX(5.5, "0.00 u", "cm", "ft")</span></span> 
  
<span data-ttu-id="e7c96-149">返回 0.18 英尺。</span><span class="sxs-lookup"><span data-stu-id="e7c96-149">Returns 0.18 feet.</span></span> 
  

