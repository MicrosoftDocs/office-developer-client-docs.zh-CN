---
title: /(除) (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 3d296730-197b-44db-853b-881597dd9b48
description: 将一个数除以另一个数。
ms.openlocfilehash: 48d43b224743949f86c5d206d9919a9e2d6fbcae
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308258"
---
# <a name="-divide-access-custom-web-app"></a><span data-ttu-id="46e0d-103">/(除) (Access 自定义 web 应用程序)</span><span class="sxs-lookup"><span data-stu-id="46e0d-103">/ (Divide) (Access custom web app)</span></span>

<span data-ttu-id="46e0d-104">将一个数除以另一个数。</span><span class="sxs-lookup"><span data-stu-id="46e0d-104">Divides one number by another.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="46e0d-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="46e0d-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="46e0d-107">语法</span><span class="sxs-lookup"><span data-stu-id="46e0d-107">Syntax</span></span>

 <span data-ttu-id="46e0d-108">*除数*  /  *除数*</span><span class="sxs-lookup"><span data-stu-id="46e0d-108">*dividend*  /  *divisor*</span></span> 
  
 <span data-ttu-id="46e0d-109">被*除数* 是要进行除法运算的数值表达式。</span><span class="sxs-lookup"><span data-stu-id="46e0d-109">*dividend*  Is the numeric expression to divide.</span></span> <span data-ttu-id="46e0d-110">可以是数值数据类型类别的任意一种数据类型的任何有效表达式, datetime 数据类型除外。</span><span class="sxs-lookup"><span data-stu-id="46e0d-110">Can be any valid expression of any one of the data types of the numeric data type category, except the datetime data type.</span></span> 
  
 <span data-ttu-id="46e0d-111">*除数* 是用来除以除数的数值表达式。</span><span class="sxs-lookup"><span data-stu-id="46e0d-111">*Divisor*  Is the numeric expression by which to divide the dividend.</span></span> <span data-ttu-id="46e0d-112">可以是数值数据类型类别的任意一种数据类型的任何有效表达式, datetime 数据类型除外。</span><span class="sxs-lookup"><span data-stu-id="46e0d-112">Can be any valid expression of any one of the data types of the numeric data type category, except the datetime data type.</span></span> 
  
## <a name="return-type"></a><span data-ttu-id="46e0d-113">返回类型</span><span class="sxs-lookup"><span data-stu-id="46e0d-113">Return Type</span></span>

<span data-ttu-id="46e0d-114">返回优先级较高的参数的数据类型。</span><span class="sxs-lookup"><span data-stu-id="46e0d-114">Returns the data type of the argument with the higher precedence.</span></span> 
  
<span data-ttu-id="46e0d-115">如果用整数\*\* *除数*除以整数, 则结果是一个整数, 其中包含结果的任何小数部分截断。</span><span class="sxs-lookup"><span data-stu-id="46e0d-115">If an integer  *dividend*  is divided by an integer  *divisor*  , the result is an integer that has any fractional part of the result truncated.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="46e0d-116">注解</span><span class="sxs-lookup"><span data-stu-id="46e0d-116">Remarks</span></span>

<span data-ttu-id="46e0d-117">由/运算符返回的实际值是第一个表达式的商除以第二个表达式。</span><span class="sxs-lookup"><span data-stu-id="46e0d-117">The actual value returned by the / operator is the quotient of the first expression divided by the second expression.</span></span>
  

