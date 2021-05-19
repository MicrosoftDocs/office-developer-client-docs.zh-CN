---
title: 'Avg Function (Access 自定义 Web app) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: d432e823-a255-4860-9c8b-201b2e0476fd
description: 计算指定字段中包含的一组值的算术平均值。
ms.openlocfilehash: e67cde12e66f943d3b25fe9cb2fee4fe4aea760f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426721"
---
# <a name="avg-function-access-custom-web-app"></a><span data-ttu-id="9948d-103">Avg Function (Access 自定义 Web app) </span><span class="sxs-lookup"><span data-stu-id="9948d-103">Avg Function (Access custom web app)</span></span>

<span data-ttu-id="9948d-104">计算指定字段中包含的一组值的算术平均值。</span><span class="sxs-lookup"><span data-stu-id="9948d-104">Calculates the arithmetic mean of a set of values contained in a specified field.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9948d-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="9948d-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="9948d-107">语法</span><span class="sxs-lookup"><span data-stu-id="9948d-107">Syntax</span></span>

 <span data-ttu-id="9948d-108">**Avg** (*NumericExpression*) </span><span class="sxs-lookup"><span data-stu-id="9948d-108">**Avg** (*NumericExpression*)</span></span> 
  
<span data-ttu-id="9948d-109">**Avg 函数** 包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="9948d-109">The **Avg** function contains the following argument.</span></span> 
  
|<span data-ttu-id="9948d-110">**参数**</span><span class="sxs-lookup"><span data-stu-id="9948d-110">**Argument**</span></span>|<span data-ttu-id="9948d-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="9948d-111">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9948d-112">NumericExpression</span><span class="sxs-lookup"><span data-stu-id="9948d-112">NumericExpression</span></span>  <br/> |<span data-ttu-id="9948d-113">字符串表达式，用于标识包含要计算其平均值的数值数据的字段，或者是使用该字段的数据执行计算的表达式。</span><span class="sxs-lookup"><span data-stu-id="9948d-113">A string expression identifying the field that contains the numeric data you want to average or an expression that performs a calculation using the data in that field.</span></span> <span data-ttu-id="9948d-114">*NumericExpression* 中的操作数可以包括表字段、变量或函数 (可以是固有函数或用户定义的函数，但不能是其他 SQL 聚合函数) 。</span><span class="sxs-lookup"><span data-stu-id="9948d-114">Operands in  *NumericExpression*  can include the name of a table field, a variable, or a function (which can be either intrinsic or user-defined but not one of the other SQL aggregate functions).</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="9948d-115">备注</span><span class="sxs-lookup"><span data-stu-id="9948d-115">Remarks</span></span>

<span data-ttu-id="9948d-p103">使用 **Avg** 计算的平均值是算术平均值（值的总和除以值的数目）。例如，可以使用 **Avg** 计算运费的平均值。</span><span class="sxs-lookup"><span data-stu-id="9948d-p103">The average calculated by **Avg** is the arithmetic mean (the sum of the values divided by the number of values). You could use **Avg**, for example, to calculate average freight cost.</span></span> 
  
<span data-ttu-id="9948d-118">**Avg** 函数在计算中不包含任何 **Null** 值。</span><span class="sxs-lookup"><span data-stu-id="9948d-118">The **Avg** function does not include any **Null** values in the calculation.</span></span> 
  

