---
title: Exp 函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 09385b75-ec0e-4dde-b9c3-9ade4a7a2b74
description: 返回指定表达式的指数值。
ms.openlocfilehash: 9c4929a25da6a8eec5984f9e9a1a6695a049614d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773427"
---
# <a name="exp-function-access-custom-web-app"></a><span data-ttu-id="e7bf0-103">Exp 函数 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="e7bf0-103">Exp Function (Access custom web app)</span></span>

<span data-ttu-id="e7bf0-104">返回指定表达式的指数值。</span><span class="sxs-lookup"><span data-stu-id="e7bf0-104">Returns the exponential value of the specified expression.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e7bf0-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="e7bf0-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="e7bf0-107">语法</span><span class="sxs-lookup"><span data-stu-id="e7bf0-107">Syntax</span></span>

 <span data-ttu-id="e7bf0-108">**Exp**(*NumericExpression*)</span><span class="sxs-lookup"><span data-stu-id="e7bf0-108">**Exp** (*NumericExpression*)</span></span> 
  
<span data-ttu-id="e7bf0-109">**Exp**函数包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="e7bf0-109">The **Exp** function contains the following argument.</span></span> 
  
|<span data-ttu-id="e7bf0-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="e7bf0-110">**Argument name**</span></span>|<span data-ttu-id="e7bf0-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="e7bf0-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="e7bf0-112">*NumericExpression*</span><span class="sxs-lookup"><span data-stu-id="e7bf0-112">*NumericExpression*</span></span>  <br/> |<span data-ttu-id="e7bf0-113">Double 类型时，或者可以隐式转换为 Double 类型的表达式。</span><span class="sxs-lookup"><span data-stu-id="e7bf0-113">An expression of type Double or of a type that can be implicitly converted to Double.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e7bf0-114">备注</span><span class="sxs-lookup"><span data-stu-id="e7bf0-114">Remarks</span></span>

<span data-ttu-id="e7bf0-115">**E** (2.718281...)，该常量是自然对数的。</span><span class="sxs-lookup"><span data-stu-id="e7bf0-115">The constant **e** (2.718281…), is the base of natural logarithms.</span></span> 
  
<span data-ttu-id="e7bf0-116">一个数指数是常量**e**号码的幂。</span><span class="sxs-lookup"><span data-stu-id="e7bf0-116">The exponent of a number is the constant **e** raised to the power of the number.</span></span> <span data-ttu-id="e7bf0-117">例如**Exp** (1.0) = e ^1.0 = 2.71828182845905 和**Exp** (10) = e ^10 = 22026.4657948067。</span><span class="sxs-lookup"><span data-stu-id="e7bf0-117">For example **Exp** (1.0) = e^1.0 = 2.71828182845905 and **Exp** (10) = e^10 = 22026.4657948067.</span></span> 
  
<span data-ttu-id="e7bf0-118">数字的自然对数的指数是号本身： **Exp** （日志 (n)） = n。</span><span class="sxs-lookup"><span data-stu-id="e7bf0-118">The exponential of the natural logarithm of a number is the number itself: **Exp** (LOG (n)) = n.</span></span> <span data-ttu-id="e7bf0-119">指数的数字的自然对数，数本身： 日志 (**Exp** (n)) = n。</span><span class="sxs-lookup"><span data-stu-id="e7bf0-119">And the natural logarithm of the exponential of a number is the number itself: LOG (**Exp** (n)) = n.</span></span> 
  

