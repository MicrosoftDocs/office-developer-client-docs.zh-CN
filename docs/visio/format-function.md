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
description: 返回作为根据 formatpicture 设置格式的字符串表达式的结果。
ms.openlocfilehash: dcb898b3cb21d8cc5ebee7e56540d9e2eefcffdb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780313"
---
# <a name="format-function"></a><span data-ttu-id="17857-103">FORMAT 函数</span><span class="sxs-lookup"><span data-stu-id="17857-103">FORMAT Function</span></span>

<span data-ttu-id="17857-104">根据_formatpicture_设置格式以字符串形式返回_表达式_的结果。</span><span class="sxs-lookup"><span data-stu-id="17857-104">Returns the result of  _expression_ as a string formatted according to  _formatpicture_.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="17857-105">语法</span><span class="sxs-lookup"><span data-stu-id="17857-105">Syntax</span></span>

<span data-ttu-id="17857-106">格式 (* **表达式** *，"* * *formatpicture* * *")</span><span class="sxs-lookup"><span data-stu-id="17857-106">FORMAT(** *expression* **," ** *formatpicture* ** ")</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="17857-107">参数</span><span class="sxs-lookup"><span data-stu-id="17857-107">Parameters</span></span>

|<span data-ttu-id="17857-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="17857-108">**Name**</span></span>|<span data-ttu-id="17857-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="17857-109">**Required/Optional**</span></span>|<span data-ttu-id="17857-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="17857-110">**Data Type**</span></span>|<span data-ttu-id="17857-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="17857-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="17857-112">_expression_</span><span class="sxs-lookup"><span data-stu-id="17857-112">_expression_</span></span> <br/> |<span data-ttu-id="17857-113">必需</span><span class="sxs-lookup"><span data-stu-id="17857-113">Required</span></span>  <br/> |<span data-ttu-id="17857-114">**字符串**</span><span class="sxs-lookup"><span data-stu-id="17857-114">**String**</span></span> <br/> |<span data-ttu-id="17857-115">常量、运算符、函数和对 ShapeSheet 单元格的引用的组合，其结果为一个值。</span><span class="sxs-lookup"><span data-stu-id="17857-115">A combination of constants, operators, functions, and references to ShapeSheet cells that results in a value.</span></span>  <br/> |
| <span data-ttu-id="17857-116">_formatpicture_</span><span class="sxs-lookup"><span data-stu-id="17857-116">_formatpicture_</span></span> <br/> |<span data-ttu-id="17857-117">必需</span><span class="sxs-lookup"><span data-stu-id="17857-117">Required</span></span>  <br/> |<span data-ttu-id="17857-118">**字符串**</span><span class="sxs-lookup"><span data-stu-id="17857-118">**String**</span></span> <br/> |<span data-ttu-id="17857-119">用于设置字符串格式的格式图片。</span><span class="sxs-lookup"><span data-stu-id="17857-119">The format picture used to fomat the string.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="17857-120">返回值</span><span class="sxs-lookup"><span data-stu-id="17857-120">Return value</span></span>

<span data-ttu-id="17857-121">String</span><span class="sxs-lookup"><span data-stu-id="17857-121">String</span></span>
  
## <a name="remarks"></a><span data-ttu-id="17857-122">注解</span><span class="sxs-lookup"><span data-stu-id="17857-122">Remarks</span></span>

<span data-ttu-id="17857-123">表达式的类型和格式图片中指定的类型控制返回的字符串的行为。</span><span class="sxs-lookup"><span data-stu-id="17857-123">The type of the expression and the type specified in the format picture govern the behavior of the returned string.</span></span> <span data-ttu-id="17857-124">_Formatpicture_必须适用于表达式的类型。</span><span class="sxs-lookup"><span data-stu-id="17857-124">The  _formatpicture_ must be appropriate for the type of expression.</span></span> <span data-ttu-id="17857-125">有关指定图片格式的详细信息，请参阅[关于设置图片格式](about-format-pictures.md)。</span><span class="sxs-lookup"><span data-stu-id="17857-125">For more information about specifying format pictures, see [About format pictures](about-format-pictures.md).</span></span>
  
<span data-ttu-id="17857-126">如果_expression_的结果和_formatpicture_中的类型不同类型的或在_formatpicture_中有语法错误，则返回错误。</span><span class="sxs-lookup"><span data-stu-id="17857-126">Returns an error if the result of  _expression_ and the type expected in  _formatpicture_ are of a different kind or if there are syntax errors in  _formatpicture_.</span></span>
  
## <a name="example-1"></a><span data-ttu-id="17857-127">示例 1</span><span class="sxs-lookup"><span data-stu-id="17857-127">Example 1</span></span>

<span data-ttu-id="17857-128">FORMAT(1cm/4, "0.000 u")</span><span class="sxs-lookup"><span data-stu-id="17857-128">FORMAT(1cm/4, "0.000 u")</span></span>
  
<span data-ttu-id="17857-129">返回“0.250 cm”。</span><span class="sxs-lookup"><span data-stu-id="17857-129">Returns "0.250 cm."</span></span>
  
## <a name="example-2"></a><span data-ttu-id="17857-130">示例 2</span><span class="sxs-lookup"><span data-stu-id="17857-130">Example 2</span></span>

<span data-ttu-id="17857-131">FORMAT(1cm/4, "0.00 U")</span><span class="sxs-lookup"><span data-stu-id="17857-131">FORMAT(1cm/4, "0.00 U")</span></span>
  
<span data-ttu-id="17857-132">返回“0.25 CM”。</span><span class="sxs-lookup"><span data-stu-id="17857-132">Returns "0.25 CM."</span></span>
  
## <a name="example-3"></a><span data-ttu-id="17857-133">示例 3</span><span class="sxs-lookup"><span data-stu-id="17857-133">Example 3</span></span>

<span data-ttu-id="17857-134">FORMAT(1cm/4, "0.0 u")</span><span class="sxs-lookup"><span data-stu-id="17857-134">FORMAT(1cm/4, "0.0 u")</span></span>
  
<span data-ttu-id="17857-135">返回“0.3 cm”。</span><span class="sxs-lookup"><span data-stu-id="17857-135">Returns "0.3 cm."</span></span>
  

