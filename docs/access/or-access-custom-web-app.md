---
title: 或者 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: e7190523-87cf-4e04-aef4-d229776cd16b
description: 结合以下两种情况。 当任一两个条件为 true，则返回 TRUE。
ms.openlocfilehash: 8ccf4a12644f45e80756f72013d42310fece07fd
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773576"
---
# <a name="or-access-custom-web-app"></a><span data-ttu-id="5d0a1-104">或者 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="5d0a1-104">OR (Access custom web app)</span></span>

<span data-ttu-id="5d0a1-105">结合以下两种情况。</span><span class="sxs-lookup"><span data-stu-id="5d0a1-105">Combines two conditions.</span></span> <span data-ttu-id="5d0a1-106">当任一两个条件为 true，则返回 TRUE。</span><span class="sxs-lookup"><span data-stu-id="5d0a1-106">Returns TRUE when either of the two conditions is true.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5d0a1-p103">[!重要信息] Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="5d0a1-p103">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="5d0a1-109">语法</span><span class="sxs-lookup"><span data-stu-id="5d0a1-109">Syntax</span></span>

 <span data-ttu-id="5d0a1-110">*布尔表达式***或***布尔表达式*</span><span class="sxs-lookup"><span data-stu-id="5d0a1-110">*BooleanExpression* **Or** *BooleanExpression*</span></span> 
  
<span data-ttu-id="5d0a1-111">**Or**运算符使用以下参数。</span><span class="sxs-lookup"><span data-stu-id="5d0a1-111">The **Or** operator uses the following argument.</span></span> 
  
|<span data-ttu-id="5d0a1-112">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="5d0a1-112">**Argument name**</span></span>|<span data-ttu-id="5d0a1-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="5d0a1-113">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="5d0a1-114">*布尔表达式*</span><span class="sxs-lookup"><span data-stu-id="5d0a1-114">*BooleanExpression*</span></span>  <br/> |<span data-ttu-id="5d0a1-115">返回 TRUE 或 FALSE 任何有效表达式。</span><span class="sxs-lookup"><span data-stu-id="5d0a1-115">Any valid expression that returns TRUE or FALSE.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5d0a1-116">备注</span><span class="sxs-lookup"><span data-stu-id="5d0a1-116">Remarks</span></span>

<span data-ttu-id="5d0a1-117">在语句中使用多个逻辑运算符时，**或**运算符计算后**和**运算符。</span><span class="sxs-lookup"><span data-stu-id="5d0a1-117">When more than one logical operator is used in a statement, **Or** operators are evaluated after **And** operators.</span></span> <span data-ttu-id="5d0a1-118">但是，您可以通过使用括号更改求值的顺序。</span><span class="sxs-lookup"><span data-stu-id="5d0a1-118">However, you can change the order of evaluation by using parentheses.</span></span> 
  
<span data-ttu-id="5d0a1-119">下表显示了**Or**运算符的结果。</span><span class="sxs-lookup"><span data-stu-id="5d0a1-119">The following table shows the result of the **Or** operator.</span></span> 
  
||<span data-ttu-id="5d0a1-120">**TRUE**</span><span class="sxs-lookup"><span data-stu-id="5d0a1-120">**TRUE**</span></span>|<span data-ttu-id="5d0a1-121">**FALSE**</span><span class="sxs-lookup"><span data-stu-id="5d0a1-121">**FALSE**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5d0a1-122">**TRUE**</span><span class="sxs-lookup"><span data-stu-id="5d0a1-122">**TRUE**</span></span> <br/> |<span data-ttu-id="5d0a1-123">TRUE</span><span class="sxs-lookup"><span data-stu-id="5d0a1-123">TRUE</span></span>  <br/> |<span data-ttu-id="5d0a1-124">TRUE</span><span class="sxs-lookup"><span data-stu-id="5d0a1-124">TRUE</span></span>  <br/> |
|<span data-ttu-id="5d0a1-125">**FALSE**</span><span class="sxs-lookup"><span data-stu-id="5d0a1-125">**FALSE**</span></span> <br/> |<span data-ttu-id="5d0a1-126">TRUE</span><span class="sxs-lookup"><span data-stu-id="5d0a1-126">TRUE</span></span>  <br/> |<span data-ttu-id="5d0a1-127">FALSE</span><span class="sxs-lookup"><span data-stu-id="5d0a1-127">FALSE</span></span>  <br/> |
   

