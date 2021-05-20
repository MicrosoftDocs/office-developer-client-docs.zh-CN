---
title: 'Between (Access 自定义 Web 应用) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 9dcb32c6-ed9b-4a09-9e6a-48cc50063a6f
description: 指定要测试的范围。
ms.openlocfilehash: fd67d1163f6a39779e0202b5ca1ba998ba8650a7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429297"
---
# <a name="between-access-custom-web-app"></a><span data-ttu-id="6535d-103">Between (Access 自定义 Web 应用) </span><span class="sxs-lookup"><span data-stu-id="6535d-103">BETWEEN (Access custom web app)</span></span>

<span data-ttu-id="6535d-104">指定要测试的范围。</span><span class="sxs-lookup"><span data-stu-id="6535d-104">Specifies a range to test.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6535d-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="6535d-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="6535d-107">语法</span><span class="sxs-lookup"><span data-stu-id="6535d-107">Syntax</span></span>

 <span data-ttu-id="6535d-108">*test_expression* [ NOT ] **between begin_expression**  **AND end_expression** </span><span class="sxs-lookup"><span data-stu-id="6535d-108">*test_expression*  [ NOT ] **BETWEEN** *begin_expression* **AND** *end_expression*</span></span> 
  
<span data-ttu-id="6535d-109">Between 运算符包含下列参数。</span><span class="sxs-lookup"><span data-stu-id="6535d-109">The **Between** operator contains the following arguments.</span></span> 
  
|<span data-ttu-id="6535d-110">**参数**</span><span class="sxs-lookup"><span data-stu-id="6535d-110">**Argument**</span></span>|<span data-ttu-id="6535d-111">**必需**</span><span class="sxs-lookup"><span data-stu-id="6535d-111">**Required**</span></span>|<span data-ttu-id="6535d-112">**描述**</span><span class="sxs-lookup"><span data-stu-id="6535d-112">**Description**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="6535d-113">*test_expression*</span><span class="sxs-lookup"><span data-stu-id="6535d-113">*test_expression*</span></span>  <br/> |<span data-ttu-id="6535d-114">是</span><span class="sxs-lookup"><span data-stu-id="6535d-114">Yes</span></span>  <br/> |<span data-ttu-id="6535d-115">在由 begin_expression 和 end_expression 定义的范围内 *测试的表达式*。</span><span class="sxs-lookup"><span data-stu-id="6535d-115">The expression to test for in the range defined by  *begin_expression*  and  *end_expression*  .</span></span> <span data-ttu-id="6535d-116">必须与 数据类型 和  *begin_expression*  *end_expression*  相同。</span><span class="sxs-lookup"><span data-stu-id="6535d-116">Must be the same data type as both  *begin_expression*  and  *end_expression*  .</span></span>  <br/> |
| <span data-ttu-id="6535d-117">*NOT*</span><span class="sxs-lookup"><span data-stu-id="6535d-117">*NOT*</span></span>  <br/> |<span data-ttu-id="6535d-118">否</span><span class="sxs-lookup"><span data-stu-id="6535d-118">No</span></span>  <br/> |<span data-ttu-id="6535d-119">指定要否定谓词的结果。</span><span class="sxs-lookup"><span data-stu-id="6535d-119">Specifies that the result of the predicate be negated.</span></span>  <br/> |
| <span data-ttu-id="6535d-120">*begin_expression*</span><span class="sxs-lookup"><span data-stu-id="6535d-120">*begin_expression*</span></span>  <br/> |<span data-ttu-id="6535d-121">是</span><span class="sxs-lookup"><span data-stu-id="6535d-121">Yes</span></span>  <br/> |<span data-ttu-id="6535d-122">一个有效的表达式。</span><span class="sxs-lookup"><span data-stu-id="6535d-122">A valid expression.</span></span> <span data-ttu-id="6535d-123">必须与 数据类型 和  *test_expression end_expression*  *相同*  。</span><span class="sxs-lookup"><span data-stu-id="6535d-123">Must be the same data type as both  *test_expression*  and  *end_expression*  .</span></span>  <br/> |
| <span data-ttu-id="6535d-124">*end_expression*</span><span class="sxs-lookup"><span data-stu-id="6535d-124">*end_expression*</span></span>  <br/> |<span data-ttu-id="6535d-125">是</span><span class="sxs-lookup"><span data-stu-id="6535d-125">Yes</span></span>  <br/> |<span data-ttu-id="6535d-126">一个有效的表达式。</span><span class="sxs-lookup"><span data-stu-id="6535d-126">A valid expression.</span></span> <span data-ttu-id="6535d-127">必须与 数据类型 和  *test_expression begin_expression*  *相同*  。</span><span class="sxs-lookup"><span data-stu-id="6535d-127">Must be the same data type as both  *test_expression*  and  *begin_expression*  .</span></span>  <br/> |
| <span data-ttu-id="6535d-128">AND</span><span class="sxs-lookup"><span data-stu-id="6535d-128">*AND*</span></span>  <br/> |<span data-ttu-id="6535d-129">是</span><span class="sxs-lookup"><span data-stu-id="6535d-129">Yes</span></span>  <br/> |<span data-ttu-id="6535d-130">指示 *test_expression* 值应位于由 begin_expression 和 *end_expression* *指示的end_expression。*</span><span class="sxs-lookup"><span data-stu-id="6535d-130">Indicates  *test_expression*  should be within the range indicated by  *begin_expression*  and  *end_expression*  .</span></span>  <br/> |
   
## <a name="result-type"></a><span data-ttu-id="6535d-131">结果类型</span><span class="sxs-lookup"><span data-stu-id="6535d-131">Result Type</span></span>

 <span data-ttu-id="6535d-132">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="6535d-132">**Boolean**</span></span>
  
## <a name="remarks"></a><span data-ttu-id="6535d-133">说明</span><span class="sxs-lookup"><span data-stu-id="6535d-133">Remarks</span></span>

 <span data-ttu-id="6535d-134">**BETWEEN** 返回 **TRUE** test_expression *值大于或* 等于 *begin_expression* 小于或等于值 end_expression *。*</span><span class="sxs-lookup"><span data-stu-id="6535d-134">**BETWEEN** returns **TRUE** if the value of  *test_expression*  is greater than or equal to the value of  *begin_expression*  and less than or equal to the value of  *end_expression*  .</span></span> 
  
 <span data-ttu-id="6535d-135">**NOT BETWEEN** 返回 **TRUE** test_expression *值小于\*\*begin_expression值或* 大于值 *end_expression* 。</span><span class="sxs-lookup"><span data-stu-id="6535d-135">**NOT BETWEEN** returns **TRUE** if the value of  *test_expression*  is less than the value of  *begin_expression*  or greater than the value of  *end_expression*  .</span></span> 
  
<span data-ttu-id="6535d-136">若要指定独占区域，请使用大于 (\>) 运算符 () 。 \<</span><span class="sxs-lookup"><span data-stu-id="6535d-136">To specify an exclusive range, use the greater than (\>) and less than operators (\<).</span></span>
  

