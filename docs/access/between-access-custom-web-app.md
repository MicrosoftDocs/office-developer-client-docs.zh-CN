---
title: BETWEEN (Access 自定义 web 应用)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 9dcb32c6-ed9b-4a09-9e6a-48cc50063a6f
description: 指定要测试的范围。
ms.openlocfilehash: fd67d1163f6a39779e0202b5ca1ba998ba8650a7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32280741"
---
# <a name="between-access-custom-web-app"></a><span data-ttu-id="e5afe-103">BETWEEN (Access 自定义 web 应用)</span><span class="sxs-lookup"><span data-stu-id="e5afe-103">BETWEEN (Access custom web app)</span></span>

<span data-ttu-id="e5afe-104">指定要测试的范围。</span><span class="sxs-lookup"><span data-stu-id="e5afe-104">Specifies a range to test.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e5afe-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="e5afe-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="e5afe-107">语法</span><span class="sxs-lookup"><span data-stu-id="e5afe-107">Syntax</span></span>

 <span data-ttu-id="e5afe-108">*test_expression* 不要\**介于***begin_expression***,\*\*\*end_expression*</span><span class="sxs-lookup"><span data-stu-id="e5afe-108">*test_expression*  [ NOT ] **BETWEEN** *begin_expression* **AND** *end_expression*</span></span> 
  
<span data-ttu-id="e5afe-109">**Between**运算符包含下列参数。</span><span class="sxs-lookup"><span data-stu-id="e5afe-109">The **Between** operator contains the following arguments.</span></span> 
  
|<span data-ttu-id="e5afe-110">**参数**</span><span class="sxs-lookup"><span data-stu-id="e5afe-110">**Argument**</span></span>|<span data-ttu-id="e5afe-111">**必需**</span><span class="sxs-lookup"><span data-stu-id="e5afe-111">**Required**</span></span>|<span data-ttu-id="e5afe-112">**描述**</span><span class="sxs-lookup"><span data-stu-id="e5afe-112">**Description**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="e5afe-113">*test_expression*</span><span class="sxs-lookup"><span data-stu-id="e5afe-113">*test_expression*</span></span>  <br/> |<span data-ttu-id="e5afe-114">是</span><span class="sxs-lookup"><span data-stu-id="e5afe-114">Yes</span></span>  <br/> |<span data-ttu-id="e5afe-115">要在*begin_expression*和*end_expression*定义的范围内进行测试的表达式。</span><span class="sxs-lookup"><span data-stu-id="e5afe-115">The expression to test for in the range defined by  *begin_expression*  and  *end_expression*  .</span></span> <span data-ttu-id="e5afe-116">必须与*begin_expression*和*end_expression*的数据类型相同。</span><span class="sxs-lookup"><span data-stu-id="e5afe-116">Must be the same data type as both  *begin_expression*  and  *end_expression*  .</span></span>  <br/> |
| <span data-ttu-id="e5afe-117">*NOT*</span><span class="sxs-lookup"><span data-stu-id="e5afe-117">*NOT*</span></span>  <br/> |<span data-ttu-id="e5afe-118">否</span><span class="sxs-lookup"><span data-stu-id="e5afe-118">No</span></span>  <br/> |<span data-ttu-id="e5afe-119">指定将谓词的结果取反。</span><span class="sxs-lookup"><span data-stu-id="e5afe-119">Specifies that the result of the predicate be negated.</span></span>  <br/> |
| <span data-ttu-id="e5afe-120">*begin_expression*</span><span class="sxs-lookup"><span data-stu-id="e5afe-120">*begin_expression*</span></span>  <br/> |<span data-ttu-id="e5afe-121">是</span><span class="sxs-lookup"><span data-stu-id="e5afe-121">Yes</span></span>  <br/> |<span data-ttu-id="e5afe-122">一个有效的表达式。</span><span class="sxs-lookup"><span data-stu-id="e5afe-122">A valid expression.</span></span> <span data-ttu-id="e5afe-123">必须与*test_expression*和*end_expression*的数据类型相同。</span><span class="sxs-lookup"><span data-stu-id="e5afe-123">Must be the same data type as both  *test_expression*  and  *end_expression*  .</span></span>  <br/> |
| <span data-ttu-id="e5afe-124">*end_expression*</span><span class="sxs-lookup"><span data-stu-id="e5afe-124">*end_expression*</span></span>  <br/> |<span data-ttu-id="e5afe-125">是</span><span class="sxs-lookup"><span data-stu-id="e5afe-125">Yes</span></span>  <br/> |<span data-ttu-id="e5afe-126">一个有效的表达式。</span><span class="sxs-lookup"><span data-stu-id="e5afe-126">A valid expression.</span></span> <span data-ttu-id="e5afe-127">必须与*test_expression*和*begin_expression*的数据类型相同。</span><span class="sxs-lookup"><span data-stu-id="e5afe-127">Must be the same data type as both  *test_expression*  and  *begin_expression*  .</span></span>  <br/> |
| <span data-ttu-id="e5afe-128">*AND*</span><span class="sxs-lookup"><span data-stu-id="e5afe-128">*AND*</span></span>  <br/> |<span data-ttu-id="e5afe-129">是</span><span class="sxs-lookup"><span data-stu-id="e5afe-129">Yes</span></span>  <br/> |<span data-ttu-id="e5afe-130">指示*test_expression*应位于*begin_expression*和*end_expression*指示的范围内。</span><span class="sxs-lookup"><span data-stu-id="e5afe-130">Indicates  *test_expression*  should be within the range indicated by  *begin_expression*  and  *end_expression*  .</span></span>  <br/> |
   
## <a name="result-type"></a><span data-ttu-id="e5afe-131">结果类型</span><span class="sxs-lookup"><span data-stu-id="e5afe-131">Result Type</span></span>

 <span data-ttu-id="e5afe-132">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="e5afe-132">**Boolean**</span></span>
  
## <a name="remarks"></a><span data-ttu-id="e5afe-133">备注</span><span class="sxs-lookup"><span data-stu-id="e5afe-133">Remarks</span></span>

 <span data-ttu-id="e5afe-134">**BETWEEN**如果*test_expression*的值大于或等于*begin_expression*的值, 小于或等于*end_expression*的值,**则返回 TRUE** 。</span><span class="sxs-lookup"><span data-stu-id="e5afe-134">**BETWEEN** returns **TRUE** if the value of  *test_expression*  is greater than or equal to the value of  *begin_expression*  and less than or equal to the value of  *end_expression*  .</span></span> 
  
 <span data-ttu-id="e5afe-135">**NOT BETWEEN**如果*test_expression*的值小于*begin_expression*的值或大于*end_expression*的值,**则返回 TRUE** 。</span><span class="sxs-lookup"><span data-stu-id="e5afe-135">**NOT BETWEEN** returns **TRUE** if the value of  *test_expression*  is less than the value of  *begin_expression*  or greater than the value of  *end_expression*  .</span></span> 
  
<span data-ttu-id="e5afe-136">若要指定独占区域, 请使用大于号 (\>) 和小于运算符 (\<)。</span><span class="sxs-lookup"><span data-stu-id="e5afe-136">To specify an exclusive range, use the greater than (\>) and less than operators (\<).</span></span>
  

