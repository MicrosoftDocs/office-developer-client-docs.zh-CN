---
title: 或 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: e7190523-87cf-4e04-aef4-d229776cd16b
description: 组合了两个条件。 如果两个条件中的任何一个为 true, 则返回 true。
ms.openlocfilehash: ffa605d2403c5aa8396d89f78d0bb7dd11343540
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414758"
---
# <a name="or-access-custom-web-app"></a><span data-ttu-id="7a446-104">或 (Access 自定义 web 应用程序)</span><span class="sxs-lookup"><span data-stu-id="7a446-104">OR (Access custom web app)</span></span>

<span data-ttu-id="7a446-105">组合了两个条件。</span><span class="sxs-lookup"><span data-stu-id="7a446-105">Combines two conditions.</span></span> <span data-ttu-id="7a446-106">如果两个条件中的任何一个为 true, 则返回 true。</span><span class="sxs-lookup"><span data-stu-id="7a446-106">Returns TRUE when either of the two conditions is true.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7a446-p103">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="7a446-p103">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="7a446-109">语法</span><span class="sxs-lookup"><span data-stu-id="7a446-109">Syntax</span></span>

 <span data-ttu-id="7a446-110">*BooleanExpression***或***BooleanExpression*</span><span class="sxs-lookup"><span data-stu-id="7a446-110">*BooleanExpression* **Or** *BooleanExpression*</span></span> 
  
<span data-ttu-id="7a446-111">**Or**运算符使用以下参数。</span><span class="sxs-lookup"><span data-stu-id="7a446-111">The **Or** operator uses the following argument.</span></span> 
  
|<span data-ttu-id="7a446-112">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="7a446-112">**Argument name**</span></span>|<span data-ttu-id="7a446-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="7a446-113">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="7a446-114">*BooleanExpression*</span><span class="sxs-lookup"><span data-stu-id="7a446-114">*BooleanExpression*</span></span>  <br/> |<span data-ttu-id="7a446-115">返回 TRUE 或 FALSE 的任何有效表达式。</span><span class="sxs-lookup"><span data-stu-id="7a446-115">Any valid expression that returns TRUE or FALSE.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7a446-116">说明</span><span class="sxs-lookup"><span data-stu-id="7a446-116">Remarks</span></span>

<span data-ttu-id="7a446-117">当在一个语句中使用多个逻辑运算符时,**或**在**And**运算符之后计算运算符。</span><span class="sxs-lookup"><span data-stu-id="7a446-117">When more than one logical operator is used in a statement, **Or** operators are evaluated after **And** operators.</span></span> <span data-ttu-id="7a446-118">不过, 您可以使用括号更改求值的顺序。</span><span class="sxs-lookup"><span data-stu-id="7a446-118">However, you can change the order of evaluation by using parentheses.</span></span> 
  
<span data-ttu-id="7a446-119">下表显示了**Or**运算符的结果。</span><span class="sxs-lookup"><span data-stu-id="7a446-119">The following table shows the result of the **Or** operator.</span></span> 
  
||<span data-ttu-id="7a446-120">**TRUE**</span><span class="sxs-lookup"><span data-stu-id="7a446-120">**TRUE**</span></span>|<span data-ttu-id="7a446-121">**该值**</span><span class="sxs-lookup"><span data-stu-id="7a446-121">**FALSE**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7a446-122">**TRUE**</span><span class="sxs-lookup"><span data-stu-id="7a446-122">**TRUE**</span></span> <br/> |<span data-ttu-id="7a446-123">TRUE</span><span class="sxs-lookup"><span data-stu-id="7a446-123">TRUE</span></span>  <br/> |<span data-ttu-id="7a446-124">TRUE</span><span class="sxs-lookup"><span data-stu-id="7a446-124">TRUE</span></span>  <br/> |
|<span data-ttu-id="7a446-125">**该值**</span><span class="sxs-lookup"><span data-stu-id="7a446-125">**FALSE**</span></span> <br/> |<span data-ttu-id="7a446-126">TRUE</span><span class="sxs-lookup"><span data-stu-id="7a446-126">TRUE</span></span>  <br/> |<span data-ttu-id="7a446-127">FALSE</span><span class="sxs-lookup"><span data-stu-id="7a446-127">FALSE</span></span>  <br/> |
   

