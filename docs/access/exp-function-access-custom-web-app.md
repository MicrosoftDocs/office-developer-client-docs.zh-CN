---
title: Exp 函数 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 09385b75-ec0e-4dde-b9c3-9ade4a7a2b74
description: 返回指定表达式的指数值。
ms.openlocfilehash: 30777c41005dfcf1caad896e9e60f0bcfd9d4361
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436410"
---
# <a name="exp-function-access-custom-web-app"></a><span data-ttu-id="322dd-103">Exp 函数 (Access 自定义 web 应用程序)</span><span class="sxs-lookup"><span data-stu-id="322dd-103">Exp Function (Access custom web app)</span></span>

<span data-ttu-id="322dd-104">返回指定表达式的指数值。</span><span class="sxs-lookup"><span data-stu-id="322dd-104">Returns the exponential value of the specified expression.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="322dd-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="322dd-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="322dd-107">语法</span><span class="sxs-lookup"><span data-stu-id="322dd-107">Syntax</span></span>

 <span data-ttu-id="322dd-108">**Exp**(*NumericExpression*)</span><span class="sxs-lookup"><span data-stu-id="322dd-108">**Exp** (*NumericExpression*)</span></span> 
  
<span data-ttu-id="322dd-109">**Exp**函数包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="322dd-109">The **Exp** function contains the following argument.</span></span> 
  
|<span data-ttu-id="322dd-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="322dd-110">**Argument name**</span></span>|<span data-ttu-id="322dd-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="322dd-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="322dd-112">*NumericExpression*</span><span class="sxs-lookup"><span data-stu-id="322dd-112">*NumericExpression*</span></span>  <br/> |<span data-ttu-id="322dd-113">一种类型为 double 的表达式, 或可隐式转换为双精度型的类型的表达式。</span><span class="sxs-lookup"><span data-stu-id="322dd-113">An expression of type Double or of a type that can be implicitly converted to Double.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="322dd-114">说明</span><span class="sxs-lookup"><span data-stu-id="322dd-114">Remarks</span></span>

<span data-ttu-id="322dd-115">常量**e** (2.718281 ...) 是自然对数的底数。</span><span class="sxs-lookup"><span data-stu-id="322dd-115">The constant **e** (2.718281…), is the base of natural logarithms.</span></span> 
  
<span data-ttu-id="322dd-116">数字的指数表示的是常量**e**的幂的乘号。</span><span class="sxs-lookup"><span data-stu-id="322dd-116">The exponent of a number is the constant **e** raised to the power of the number.</span></span> <span data-ttu-id="322dd-117">例如**Exp** (1.0) = e ^ 1.0 = 2.71828182845905 and **Exp** (10) = e ^ 10 = 22026.4657948067。</span><span class="sxs-lookup"><span data-stu-id="322dd-117">For example **Exp** (1.0) = e^1.0 = 2.71828182845905 and **Exp** (10) = e^10 = 22026.4657948067.</span></span> 
  
<span data-ttu-id="322dd-118">数字的自然对数的指数是数字本身: **Exp** (LOG (n)) = n。</span><span class="sxs-lookup"><span data-stu-id="322dd-118">The exponential of the natural logarithm of a number is the number itself: **Exp** (LOG (n)) = n.</span></span> <span data-ttu-id="322dd-119">数字的指数的自然对数是数字本身: LOG (**Exp** (n)) = n。</span><span class="sxs-lookup"><span data-stu-id="322dd-119">And the natural logarithm of the exponential of a number is the number itself: LOG (**Exp** (n)) = n.</span></span> 
  

