---
title: Sum 函数 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c2345092-ba5f-4030-9070-391233e70f92
description: 返回表达式中所有值的总和。
ms.openlocfilehash: b0fed86469b32ddcc7f60a388f5d42c7bbd48b6c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427099"
---
# <a name="sum-function-access-custom-web-app"></a><span data-ttu-id="934e5-103">Sum 函数 (Access 自定义 web 应用程序)</span><span class="sxs-lookup"><span data-stu-id="934e5-103">Sum Function (Access custom web app)</span></span>

<span data-ttu-id="934e5-104">返回表达式中所有值的总和。</span><span class="sxs-lookup"><span data-stu-id="934e5-104">Returns the sum of all the values in the expression.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="934e5-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="934e5-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="934e5-107">语法</span><span class="sxs-lookup"><span data-stu-id="934e5-107">Syntax</span></span>

 <span data-ttu-id="934e5-108">**Sum**(*NumericExpression*)</span><span class="sxs-lookup"><span data-stu-id="934e5-108">**Sum** (*NumericExpression*)</span></span> 
  
<span data-ttu-id="934e5-109">**Sum**函数包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="934e5-109">The **Sum** function contains the following argument.</span></span> 
  
|<span data-ttu-id="934e5-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="934e5-110">**Argument name**</span></span>|<span data-ttu-id="934e5-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="934e5-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="934e5-112">*NumericExpression*</span><span class="sxs-lookup"><span data-stu-id="934e5-112">*NumericExpression*</span></span>  <br/> |<span data-ttu-id="934e5-113">表达式, 用于标识包含要添加的数值数据的字段, 或者是使用该字段中的数据执行计算的表达式。</span><span class="sxs-lookup"><span data-stu-id="934e5-113">An expression identifying the field that contains the numeric data you want to add or an expression that performs a calculation using the data in that field.</span></span> <span data-ttu-id="934e5-114">*NumericExpression*中的操作数可以包括表字段、常量或函数 (可以是固有的, 也可以是用户定义的, 但不能是其他 SQL 聚合函数) 的名称。</span><span class="sxs-lookup"><span data-stu-id="934e5-114">Operands in  *NumericExpression*  can include the name of a table field, a constant, or a function (which can be either intrinsic or user-defined but not one of the other SQL aggregate functions).</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="934e5-115">说明</span><span class="sxs-lookup"><span data-stu-id="934e5-115">Remarks</span></span>

<span data-ttu-id="934e5-116">**Sum**函数将忽略包含 Null 值的记录。</span><span class="sxs-lookup"><span data-stu-id="934e5-116">The **Sum** function ignores records that contain Null values.</span></span> 
  
<span data-ttu-id="934e5-117">**Sum**函数仅可用于数字列。</span><span class="sxs-lookup"><span data-stu-id="934e5-117">The **Sum** function can only be used with numeric columns.</span></span> 
  

