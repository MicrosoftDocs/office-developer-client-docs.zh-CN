---
title: '/ (Divide)  (Access 自定义 Web 应用) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 3d296730-197b-44db-853b-881597dd9b48
description: 将一个数字除以另一个数字。
ms.openlocfilehash: 48d43b224743949f86c5d206d9919a9e2d6fbcae
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435185"
---
# <a name="-divide-access-custom-web-app"></a><span data-ttu-id="e6dd6-103">/ (Divide)  (Access 自定义 Web 应用) </span><span class="sxs-lookup"><span data-stu-id="e6dd6-103">/ (Divide) (Access custom web app)</span></span>

<span data-ttu-id="e6dd6-104">将一个数字除以另一个数字。</span><span class="sxs-lookup"><span data-stu-id="e6dd6-104">Divides one number by another.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e6dd6-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="e6dd6-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="e6dd6-107">语法</span><span class="sxs-lookup"><span data-stu-id="e6dd6-107">Syntax</span></span>

 <span data-ttu-id="e6dd6-108">*一个*   /  *divisor*</span><span class="sxs-lookup"><span data-stu-id="e6dd6-108">*dividend*  /  *divisor*</span></span> 
  
 <span data-ttu-id="e6dd6-109">*一个*  要除以的数值表达式。</span><span class="sxs-lookup"><span data-stu-id="e6dd6-109">*dividend*  Is the numeric expression to divide.</span></span> <span data-ttu-id="e6dd6-110">可以是数值数据类别的任何数据类型的任何有效数据类型，但 datetime 数据类型。</span><span class="sxs-lookup"><span data-stu-id="e6dd6-110">Can be any valid expression of any one of the data types of the numeric data type category, except the datetime data type.</span></span> 
  
 <span data-ttu-id="e6dd6-111">*Divisor*  是除数的数值表达式。</span><span class="sxs-lookup"><span data-stu-id="e6dd6-111">*Divisor*  Is the numeric expression by which to divide the dividend.</span></span> <span data-ttu-id="e6dd6-112">可以是数值数据类别的任何数据类型的任何有效数据类型，但 datetime 数据类型。</span><span class="sxs-lookup"><span data-stu-id="e6dd6-112">Can be any valid expression of any one of the data types of the numeric data type category, except the datetime data type.</span></span> 
  
## <a name="return-type"></a><span data-ttu-id="e6dd6-113">返回类型</span><span class="sxs-lookup"><span data-stu-id="e6dd6-113">Return Type</span></span>

<span data-ttu-id="e6dd6-114">返回数据类型优先级较高的参数的变量。</span><span class="sxs-lookup"><span data-stu-id="e6dd6-114">Returns the data type of the argument with the higher precedence.</span></span> 
  
<span data-ttu-id="e6dd6-115">如果整数 *除* 数除以整数除数，则结果是结果的任何小数部分被截断的整数。</span><span class="sxs-lookup"><span data-stu-id="e6dd6-115">If an integer  *dividend*  is divided by an integer  *divisor*  , the result is an integer that has any fractional part of the result truncated.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="e6dd6-116">备注</span><span class="sxs-lookup"><span data-stu-id="e6dd6-116">Remarks</span></span>

<span data-ttu-id="e6dd6-117">/ 实际值返回的值是第一个表达式除以第二个表达式的商。</span><span class="sxs-lookup"><span data-stu-id="e6dd6-117">The actual value returned by the / operator is the quotient of the first expression divided by the second expression.</span></span>
  

