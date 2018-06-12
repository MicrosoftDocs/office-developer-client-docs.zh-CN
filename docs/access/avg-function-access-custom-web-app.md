---
title: Avg 函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: d432e823-a255-4860-9c8b-201b2e0476fd
description: 计算的一组指定的字段中包含的值的算术平均值。
ms.openlocfilehash: afe832a51fc9cd3b224087a0b06fe539f6a7004b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773438"
---
# <a name="avg-function-access-custom-web-app"></a><span data-ttu-id="0c393-103">Avg 函数 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="0c393-103">Avg Function (Access custom web app)</span></span>

<span data-ttu-id="0c393-104">计算的一组指定的字段中包含的值的算术平均值。</span><span class="sxs-lookup"><span data-stu-id="0c393-104">Calculates the arithmetic mean of a set of values contained in a specified field.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0c393-p101">[!重要信息] Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="0c393-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="0c393-107">语法</span><span class="sxs-lookup"><span data-stu-id="0c393-107">Syntax</span></span>

 <span data-ttu-id="0c393-108">**平均**(*NumericExpression*)</span><span class="sxs-lookup"><span data-stu-id="0c393-108">**Avg** (*NumericExpression*)</span></span> 
  
<span data-ttu-id="0c393-109">**Avg**函数包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="0c393-109">The **Avg** function contains the following argument.</span></span> 
  
|<span data-ttu-id="0c393-110">**参数**</span><span class="sxs-lookup"><span data-stu-id="0c393-110">**Argument**</span></span>|<span data-ttu-id="0c393-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="0c393-111">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0c393-112">NumericExpression</span><span class="sxs-lookup"><span data-stu-id="0c393-112">NumericExpression</span></span>  <br/> |<span data-ttu-id="0c393-113">标识包含数值数据的字段的字符串表达式要平均值或表达式的计算使用该字段中的数据。</span><span class="sxs-lookup"><span data-stu-id="0c393-113">A string expression identifying the field that contains the numeric data you want to average or an expression that performs a calculation using the data in that field.</span></span> <span data-ttu-id="0c393-114">*NumericExpression*中可以包括表字段、 变量或函数 （这可能是固有或用户定义但不是其他 SQL 聚合函数） 的名称。</span><span class="sxs-lookup"><span data-stu-id="0c393-114">Operands in  *NumericExpression*  can include the name of a table field, a variable, or a function (which can be either intrinsic or user-defined but not one of the other SQL aggregate functions).</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0c393-115">备注</span><span class="sxs-lookup"><span data-stu-id="0c393-115">Remarks</span></span>

<span data-ttu-id="0c393-116">计算**平均**的平均值是算术平均值 （值的总和的值的数量的比率）。</span><span class="sxs-lookup"><span data-stu-id="0c393-116">The average calculated by **Avg** is the arithmetic mean (the sum of the values divided by the number of values).</span></span> <span data-ttu-id="0c393-117">您可以使用**Avg**，例如，计算平均运货成本。</span><span class="sxs-lookup"><span data-stu-id="0c393-117">You could use **Avg**, for example, to calculate average freight cost.</span></span> 
  
<span data-ttu-id="0c393-118">**Avg**函数不包括**Null**值的计算中。</span><span class="sxs-lookup"><span data-stu-id="0c393-118">The **Avg** function does not include any **Null** values in the calculation.</span></span> 
  

