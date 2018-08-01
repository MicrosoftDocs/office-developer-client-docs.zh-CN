---
title: 之间 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 9dcb32c6-ed9b-4a09-9e6a-48cc50063a6f
description: 指定要测试的范围。
ms.openlocfilehash: 0ef3384d6a29826968220f8d6cfc0d2f85e1131c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773449"
---
# <a name="between-access-custom-web-app"></a><span data-ttu-id="2f830-103">之间 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="2f830-103">BETWEEN (Access custom web app)</span></span>

<span data-ttu-id="2f830-104">指定要测试的范围。</span><span class="sxs-lookup"><span data-stu-id="2f830-104">Specifies a range to test.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2f830-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="2f830-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="2f830-107">语法</span><span class="sxs-lookup"><span data-stu-id="2f830-107">Syntax</span></span>

 <span data-ttu-id="2f830-108">*test_expression* [NOT]**BETWEEN***begin_expression***AND***end_expression*</span><span class="sxs-lookup"><span data-stu-id="2f830-108">*test_expression*  [ NOT ] **BETWEEN** *begin_expression* **AND** *end_expression*</span></span> 
  
<span data-ttu-id="2f830-109">**Between**运算符包含下列参数。</span><span class="sxs-lookup"><span data-stu-id="2f830-109">The **Between** operator contains the following arguments.</span></span> 
  
|<span data-ttu-id="2f830-110">**参数**</span><span class="sxs-lookup"><span data-stu-id="2f830-110">**Argument**</span></span>|<span data-ttu-id="2f830-111">**必需**</span><span class="sxs-lookup"><span data-stu-id="2f830-111">**Required**</span></span>|<span data-ttu-id="2f830-112">**说明**</span><span class="sxs-lookup"><span data-stu-id="2f830-112">**Description**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="2f830-113">*test_expression*</span><span class="sxs-lookup"><span data-stu-id="2f830-113">*test_expression*</span></span>  <br/> |<span data-ttu-id="2f830-114">可访问</span><span class="sxs-lookup"><span data-stu-id="2f830-114">Yes</span></span>  <br/> |<span data-ttu-id="2f830-115">要测试定义*begin_expression*和*end_expression*的范围中的表达式。</span><span class="sxs-lookup"><span data-stu-id="2f830-115">The expression to test for in the range defined by  *begin_expression*  and  *end_expression*  .</span></span> <span data-ttu-id="2f830-116">必须为*begin_expression*和*end_expression*同一字段数据类型。</span><span class="sxs-lookup"><span data-stu-id="2f830-116">Must be the same data type as both  *begin_expression*  and  *end_expression*  .</span></span>  <br/> |
| <span data-ttu-id="2f830-117">*NOT*</span><span class="sxs-lookup"><span data-stu-id="2f830-117">*NOT*</span></span>  <br/> |<span data-ttu-id="2f830-118">否</span><span class="sxs-lookup"><span data-stu-id="2f830-118">No</span></span>  <br/> |<span data-ttu-id="2f830-119">指定否定谓词的结果。</span><span class="sxs-lookup"><span data-stu-id="2f830-119">Specifies that the result of the predicate be negated.</span></span>  <br/> |
| <span data-ttu-id="2f830-120">*begin_expression*</span><span class="sxs-lookup"><span data-stu-id="2f830-120">*begin_expression*</span></span>  <br/> |<span data-ttu-id="2f830-121">可访问</span><span class="sxs-lookup"><span data-stu-id="2f830-121">Yes</span></span>  <br/> |<span data-ttu-id="2f830-122">一个有效表达式。</span><span class="sxs-lookup"><span data-stu-id="2f830-122">A valid expression.</span></span> <span data-ttu-id="2f830-123">必须为*test_expression*和*end_expression*同一字段数据类型。</span><span class="sxs-lookup"><span data-stu-id="2f830-123">Must be the same data type as both  *test_expression*  and  *end_expression*  .</span></span>  <br/> |
| <span data-ttu-id="2f830-124">*end_expression*</span><span class="sxs-lookup"><span data-stu-id="2f830-124">*end_expression*</span></span>  <br/> |<span data-ttu-id="2f830-125">可访问</span><span class="sxs-lookup"><span data-stu-id="2f830-125">Yes</span></span>  <br/> |<span data-ttu-id="2f830-126">一个有效表达式。</span><span class="sxs-lookup"><span data-stu-id="2f830-126">A valid expression.</span></span> <span data-ttu-id="2f830-127">必须为*test_expression*和*begin_expression*同一字段数据类型。</span><span class="sxs-lookup"><span data-stu-id="2f830-127">Must be the same data type as both  *test_expression*  and  *begin_expression*  .</span></span>  <br/> |
| <span data-ttu-id="2f830-128">*AND*</span><span class="sxs-lookup"><span data-stu-id="2f830-128">*AND*</span></span>  <br/> |<span data-ttu-id="2f830-129">可访问</span><span class="sxs-lookup"><span data-stu-id="2f830-129">Yes</span></span>  <br/> |<span data-ttu-id="2f830-130">指示*test_expression*应由*begin_expression*和*end_expression*指示范围内。</span><span class="sxs-lookup"><span data-stu-id="2f830-130">Indicates  *test_expression*  should be within the range indicated by  *begin_expression*  and  *end_expression*  .</span></span>  <br/> |
   
## <a name="result-type"></a><span data-ttu-id="2f830-131">结果类型</span><span class="sxs-lookup"><span data-stu-id="2f830-131">Result Type</span></span>

 <span data-ttu-id="2f830-132">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="2f830-132">**Boolean**</span></span>
  
## <a name="remarks"></a><span data-ttu-id="2f830-133">说明</span><span class="sxs-lookup"><span data-stu-id="2f830-133">Remarks</span></span>

 <span data-ttu-id="2f830-134">**BETWEEN**返回**TRUE** ，如果*test_expression*值大于或等于*begin_expression*值且小于或等于*end_expression*的值。</span><span class="sxs-lookup"><span data-stu-id="2f830-134">**BETWEEN** returns **TRUE** if the value of  *test_expression*  is greater than or equal to the value of  *begin_expression*  and less than or equal to the value of  *end_expression*  .</span></span> 
  
 <span data-ttu-id="2f830-135">**之间不**返回**TRUE** ，如果*test_expression*的值小于 value *begin_expression*或大于*end_expression*的值。</span><span class="sxs-lookup"><span data-stu-id="2f830-135">**NOT BETWEEN** returns **TRUE** if the value of  *test_expression*  is less than the value of  *begin_expression*  or greater than the value of  *end_expression*  .</span></span> 
  
<span data-ttu-id="2f830-136">要指定排除范围，请使用大于比 (\>) 且小于运算符 (\<)。</span><span class="sxs-lookup"><span data-stu-id="2f830-136">To specify an exclusive range, use the greater than (\>) and less than operators (\<).</span></span>
  

