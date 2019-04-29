---
title: Var 函数 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: cb2aace1-fa2d-480e-bfc7-44ae399943f5
description: 返回总体样本的统计方差, 表示为查询中指定字段中包含的一组值。
ms.openlocfilehash: 80cea512b0386d9b0461c927675ae51be3e0dcda
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437754"
---
# <a name="var-function-access-custom-web-app"></a><span data-ttu-id="d6f21-103">Var 函数 (Access 自定义 web 应用程序)</span><span class="sxs-lookup"><span data-stu-id="d6f21-103">Var Function (Access custom web app)</span></span>

<span data-ttu-id="d6f21-104">返回总体样本的统计方差, 表示为查询中指定字段中包含的一组值。</span><span class="sxs-lookup"><span data-stu-id="d6f21-104">Returns the statistical variance for a population sample represented as a set of values contained in a specified field in a query.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d6f21-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="d6f21-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="d6f21-107">语法</span><span class="sxs-lookup"><span data-stu-id="d6f21-107">Syntax</span></span>

 <span data-ttu-id="d6f21-108">**Var**(*NumericExpression*)</span><span class="sxs-lookup"><span data-stu-id="d6f21-108">**Var** (*NumericExpression*)</span></span> 
  
<span data-ttu-id="d6f21-109">**Var**函数包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="d6f21-109">The **Var** function contains the following argument.</span></span> 
  
|<span data-ttu-id="d6f21-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="d6f21-110">**Argument name**</span></span>|<span data-ttu-id="d6f21-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="d6f21-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="d6f21-112">*NumericExpression*</span><span class="sxs-lookup"><span data-stu-id="d6f21-112">*NumericExpression*</span></span>  <br/> |<span data-ttu-id="d6f21-113">文本表达式, 用于标识包含要计算的数值数据的字段, 或者是使用该字段中的数据执行计算的表达式。</span><span class="sxs-lookup"><span data-stu-id="d6f21-113">A text expression identifying the field that contains the numeric data you want to evaluate or an expression that performs a calculation using the data in that field.</span></span> <span data-ttu-id="d6f21-114">*NumericExpression*中的操作数可以包括表字段、常量或函数 (可以是固有的, 也可以是用户定义的, 但不能是其他 SQL 聚合函数) 的名称。</span><span class="sxs-lookup"><span data-stu-id="d6f21-114">Operands in  *NumericExpression*  can include the name of a table field, a constant, or a function (which can be either intrinsic or user-defined but not one of the other SQL aggregate functions).</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d6f21-115">说明</span><span class="sxs-lookup"><span data-stu-id="d6f21-115">Remarks</span></span>

 <span data-ttu-id="d6f21-116">**Var**仅可用于数字列。</span><span class="sxs-lookup"><span data-stu-id="d6f21-116">**Var** can be used with numeric columns only.</span></span> <span data-ttu-id="d6f21-117">Null 值将被忽略。</span><span class="sxs-lookup"><span data-stu-id="d6f21-117">Null values are ignored.</span></span> 
  

