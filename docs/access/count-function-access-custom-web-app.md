---
title: Count 函数 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: d931535b-428f-4300-93bf-cfe0ebcc2ac9
description: 返回查询或表中的记录数。
ms.openlocfilehash: 98dbed393bf2f6dc401119f6c5dc7ab6b5ff7864
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32282234"
---
# <a name="count-function-access-custom-web-app"></a><span data-ttu-id="41970-103">Count 函数 (Access 自定义 web 应用程序)</span><span class="sxs-lookup"><span data-stu-id="41970-103">Count function (Access custom web app)</span></span>

<span data-ttu-id="41970-104">返回查询或表中的记录数。</span><span class="sxs-lookup"><span data-stu-id="41970-104">Returns the number of records in a query or table.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="41970-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="41970-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="41970-107">语法</span><span class="sxs-lookup"><span data-stu-id="41970-107">Syntax</span></span>

<span data-ttu-id="41970-108">**计数**(*表达式*)</span><span class="sxs-lookup"><span data-stu-id="41970-108">**Count** (*Expression*)</span></span> 
  
<span data-ttu-id="41970-109">**Count**函数包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="41970-109">The **Count** function contains the following argument.</span></span> 
  
|<span data-ttu-id="41970-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="41970-110">**Argument name**</span></span>|<span data-ttu-id="41970-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="41970-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="41970-112">*Expression*</span><span class="sxs-lookup"><span data-stu-id="41970-112">*Expression*</span></span>  <br/> |<span data-ttu-id="41970-113">字符串表达式, 用于标识包含要计数的数据的字段, 或使用字段中的数据执行计算的表达式。</span><span class="sxs-lookup"><span data-stu-id="41970-113">A string expression identifying the field that contains the data you want to count or an expression that performs a calculation using the data in the field.</span></span> <span data-ttu-id="41970-114">*表达式*中的操作数可以包括表字段或函数的名称 (可以是固有的, 也可以是用户定义的, 但不能是其他 SQL 聚合函数)。</span><span class="sxs-lookup"><span data-stu-id="41970-114">Operands in  *Expression*  can include the name of a table field or function (which can be either intrinsic or user-defined but not other SQL aggregate functions).</span></span> <span data-ttu-id="41970-115">可以计算包括文本在内的任何类型数据。</span><span class="sxs-lookup"><span data-stu-id="41970-115">You can count any kind of data, including text.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="41970-116">注解</span><span class="sxs-lookup"><span data-stu-id="41970-116">Remarks</span></span>

<span data-ttu-id="41970-117">可以使用 Count 来统计基本查询的记录数。</span><span class="sxs-lookup"><span data-stu-id="41970-117">You can use Count to count the number of records in an underlying query.</span></span> <span data-ttu-id="41970-118">例如, 可以使用 count 计算发往特定国家或地区的订单数。</span><span class="sxs-lookup"><span data-stu-id="41970-118">For example, you could use Count to count the number of orders shipped to a particular country or region.</span></span>
  
<span data-ttu-id="41970-119">**计数**(\*) 返回组中的项目数。</span><span class="sxs-lookup"><span data-stu-id="41970-119">**Count** (\*) returns the number of items in a group.</span></span> <span data-ttu-id="41970-120">这包括 NULL 值和重复项。</span><span class="sxs-lookup"><span data-stu-id="41970-120">This includes NULL values and duplicates.</span></span> 
  

