---
title: / （划分） （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 3d296730-197b-44db-853b-881597dd9b48
description: 用由另一个数。
ms.openlocfilehash: fd5ce0f26d6ea03f14103cd76779a95ca8a34b1f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773465"
---
# <a name="-divide-access-custom-web-app"></a><span data-ttu-id="3b2e2-103">/ （划分） （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="3b2e2-103">/ (Divide) (Access custom web app)</span></span>

<span data-ttu-id="3b2e2-104">用由另一个数。</span><span class="sxs-lookup"><span data-stu-id="3b2e2-104">Divides one number by another.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3b2e2-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="3b2e2-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="3b2e2-107">语法</span><span class="sxs-lookup"><span data-stu-id="3b2e2-107">Syntax</span></span>

 <span data-ttu-id="3b2e2-108">*被除数*  /  *除数*</span><span class="sxs-lookup"><span data-stu-id="3b2e2-108">*dividend*  /  *divisor*</span></span> 
  
 <span data-ttu-id="3b2e2-109">*被除数* 划分的数值表达式。</span><span class="sxs-lookup"><span data-stu-id="3b2e2-109">*dividend*  Is the numeric expression to divide.</span></span> <span data-ttu-id="3b2e2-110">可以是任何有效的数字数据类型分类，除 datetime 数据类型的数据类型之一的表达式。</span><span class="sxs-lookup"><span data-stu-id="3b2e2-110">Can be any valid expression of any one of the data types of the numeric data type category, except the datetime data type.</span></span> 
  
 <span data-ttu-id="3b2e2-111">*除数* 是要除数的数值表达式。</span><span class="sxs-lookup"><span data-stu-id="3b2e2-111">*Divisor*  Is the numeric expression by which to divide the dividend.</span></span> <span data-ttu-id="3b2e2-112">可以是任何有效的数字数据类型分类，除 datetime 数据类型的数据类型之一的表达式。</span><span class="sxs-lookup"><span data-stu-id="3b2e2-112">Can be any valid expression of any one of the data types of the numeric data type category, except the datetime data type.</span></span> 
  
## <a name="return-type"></a><span data-ttu-id="3b2e2-113">返回类型</span><span class="sxs-lookup"><span data-stu-id="3b2e2-113">Return Type</span></span>

<span data-ttu-id="3b2e2-114">返回具有更高的优先级参数的数据类型。</span><span class="sxs-lookup"><span data-stu-id="3b2e2-114">Returns the data type of the argument with the higher precedence.</span></span> 
  
<span data-ttu-id="3b2e2-115">如果整数*被除数*除以整数*除数*，结果将为整数类型的值已被截断结果的小数部分。</span><span class="sxs-lookup"><span data-stu-id="3b2e2-115">If an integer  *dividend*  is divided by an integer  *divisor*  , the result is an integer that has any fractional part of the result truncated.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="3b2e2-116">备注</span><span class="sxs-lookup"><span data-stu-id="3b2e2-116">Remarks</span></span>

<span data-ttu-id="3b2e2-117">返回的实际值 / 运算符为除以第二个表达式的第一个表达式的商。</span><span class="sxs-lookup"><span data-stu-id="3b2e2-117">The actual value returned by the / operator is the quotient of the first expression divided by the second expression.</span></span>
  

