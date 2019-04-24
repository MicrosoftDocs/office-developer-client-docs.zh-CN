---
title: FORMAT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251424
localization_priority: Normal
ms.assetid: 52f5ef4d-07c6-ab36-bf74-b30b50eea221
description: 以字符串形式返回 expression 的结果，该字符串的格式根据 formatpicture 设置。
ms.openlocfilehash: 5eb2195c2bc52e9cc8e7aa8bc4068826a5cd14c5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339891"
---
# <a name="format-function"></a><span data-ttu-id="a575f-103">FORMAT 函数</span><span class="sxs-lookup"><span data-stu-id="a575f-103">FORMAT Function</span></span>

<span data-ttu-id="a575f-104">以字符串的形式返回_表达式_的结果, 该字符串根据_formatpicture_设置格式。</span><span class="sxs-lookup"><span data-stu-id="a575f-104">Returns the result of  _expression_ as a string formatted according to  _formatpicture_.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="a575f-105">语法</span><span class="sxs-lookup"><span data-stu-id="a575f-105">Syntax</span></span>

<span data-ttu-id="a575f-106">FORMAT (\* **表达式** *, "* \* *formatpicture* \* \*")</span><span class="sxs-lookup"><span data-stu-id="a575f-106">FORMAT(\*\* *expression* \*\*," \*\* *formatpicture* \*\* ")</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="a575f-107">参数</span><span class="sxs-lookup"><span data-stu-id="a575f-107">Parameters</span></span>

|<span data-ttu-id="a575f-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="a575f-108">**Name**</span></span>|<span data-ttu-id="a575f-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="a575f-109">**Required/Optional**</span></span>|<span data-ttu-id="a575f-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a575f-110">**Data Type**</span></span>|<span data-ttu-id="a575f-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="a575f-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="a575f-112">_expression_</span><span class="sxs-lookup"><span data-stu-id="a575f-112">_expression_</span></span> <br/> |<span data-ttu-id="a575f-113">必需</span><span class="sxs-lookup"><span data-stu-id="a575f-113">Required</span></span>  <br/> |<span data-ttu-id="a575f-114">**String**</span><span class="sxs-lookup"><span data-stu-id="a575f-114">**String**</span></span> <br/> |<span data-ttu-id="a575f-115">常量、运算符、函数和对 ShapeSheet 单元格的引用的组合，其结果为一个值。</span><span class="sxs-lookup"><span data-stu-id="a575f-115">A combination of constants, operators, functions, and references to ShapeSheet cells that results in a value.</span></span>  <br/> |
| <span data-ttu-id="a575f-116">_formatpicture_</span><span class="sxs-lookup"><span data-stu-id="a575f-116">_formatpicture_</span></span> <br/> |<span data-ttu-id="a575f-117">必需</span><span class="sxs-lookup"><span data-stu-id="a575f-117">Required</span></span>  <br/> |<span data-ttu-id="a575f-118">**String**</span><span class="sxs-lookup"><span data-stu-id="a575f-118">**String**</span></span> <br/> |<span data-ttu-id="a575f-119">用于设置字符串格式的格式图片。</span><span class="sxs-lookup"><span data-stu-id="a575f-119">The format picture used to fomat the string.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="a575f-120">返回值</span><span class="sxs-lookup"><span data-stu-id="a575f-120">Return value</span></span>

<span data-ttu-id="a575f-121">字符串</span><span class="sxs-lookup"><span data-stu-id="a575f-121">String</span></span>
  
## <a name="remarks"></a><span data-ttu-id="a575f-122">注解</span><span class="sxs-lookup"><span data-stu-id="a575f-122">Remarks</span></span>

<span data-ttu-id="a575f-123">表达式的类型和格式图片中指定的类型将控制返回的字符串的行为。</span><span class="sxs-lookup"><span data-stu-id="a575f-123">The type of the expression and the type specified in the format picture govern the behavior of the returned string.</span></span> <span data-ttu-id="a575f-124">_formatpicture_必须适合于表达式的类型。</span><span class="sxs-lookup"><span data-stu-id="a575f-124">The  _formatpicture_ must be appropriate for the type of expression.</span></span> <span data-ttu-id="a575f-125">有关指定格式图片的详细信息，请参阅[关于格式图片](about-format-pictures.md)。</span><span class="sxs-lookup"><span data-stu-id="a575f-125">For more information about specifying format pictures, see [About format pictures](about-format-pictures.md).</span></span>
  
<span data-ttu-id="a575f-126">如果_表达式_和_formatpicture_中预期的类型的结果是不同的, 或者_formatpicture_中有语法错误, 则返回错误。</span><span class="sxs-lookup"><span data-stu-id="a575f-126">Returns an error if the result of  _expression_ and the type expected in  _formatpicture_ are of a different kind or if there are syntax errors in  _formatpicture_.</span></span>
  
## <a name="example-1"></a><span data-ttu-id="a575f-127">示例 1</span><span class="sxs-lookup"><span data-stu-id="a575f-127">Example 1</span></span>

<span data-ttu-id="a575f-128">FORMAT(1cm/4, "0.000 u")</span><span class="sxs-lookup"><span data-stu-id="a575f-128">FORMAT(1cm/4, "0.000 u")</span></span>
  
<span data-ttu-id="a575f-129">返回“0.250 cm”。</span><span class="sxs-lookup"><span data-stu-id="a575f-129">Returns "0.250 cm."</span></span>
  
## <a name="example-2"></a><span data-ttu-id="a575f-130">示例 2</span><span class="sxs-lookup"><span data-stu-id="a575f-130">Example 2</span></span>

<span data-ttu-id="a575f-131">FORMAT(1cm/4, "0.00 U")</span><span class="sxs-lookup"><span data-stu-id="a575f-131">FORMAT(1cm/4, "0.00 U")</span></span>
  
<span data-ttu-id="a575f-132">返回“0.25 CM”。</span><span class="sxs-lookup"><span data-stu-id="a575f-132">Returns "0.25 CM."</span></span>
  
## <a name="example-3"></a><span data-ttu-id="a575f-133">示例 3</span><span class="sxs-lookup"><span data-stu-id="a575f-133">Example 3</span></span>

<span data-ttu-id="a575f-134">FORMAT(1cm/4, "0.0 u")</span><span class="sxs-lookup"><span data-stu-id="a575f-134">FORMAT(1cm/4, "0.0 u")</span></span>
  
<span data-ttu-id="a575f-135">返回“0.3 cm”。</span><span class="sxs-lookup"><span data-stu-id="a575f-135">Returns "0.3 cm."</span></span>
  

