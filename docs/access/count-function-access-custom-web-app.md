---
title: Count 函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: d931535b-428f-4300-93bf-cfe0ebcc2ac9
description: 返回查询或表中的记录数。
ms.openlocfilehash: 300fcbfd2aa927dd19516355ae28eec2adadf521
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773458"
---
# <a name="count-function-access-custom-web-app"></a><span data-ttu-id="5c9e7-103">Count 函数 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="5c9e7-103">Count function (Access custom web app)</span></span>

<span data-ttu-id="5c9e7-104">返回查询或表中的记录数。</span><span class="sxs-lookup"><span data-stu-id="5c9e7-104">Returns the number of records in a query or table.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5c9e7-p101"> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/zh-cn/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="5c9e7-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/zh-cn/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="5c9e7-107">语法</span><span class="sxs-lookup"><span data-stu-id="5c9e7-107">Syntax</span></span>

<span data-ttu-id="5c9e7-108">**计数**（*表达式*）</span><span class="sxs-lookup"><span data-stu-id="5c9e7-108">**Count** (*Expression*)</span></span> 
  
<span data-ttu-id="5c9e7-109">**Count**函数包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="5c9e7-109">The **Count** function contains the following argument.</span></span> 
  
|<span data-ttu-id="5c9e7-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="5c9e7-110">**Argument name**</span></span>|<span data-ttu-id="5c9e7-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="5c9e7-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="5c9e7-112">*Expression*</span><span class="sxs-lookup"><span data-stu-id="5c9e7-112">*Expression*</span></span>  <br/> |<span data-ttu-id="5c9e7-113">标识了包含数据的字段的字符串表达式要计数或表达式的计算使用字段中的数据。</span><span class="sxs-lookup"><span data-stu-id="5c9e7-113">A string expression identifying the field that contains the data you want to count or an expression that performs a calculation using the data in the field.</span></span> <span data-ttu-id="5c9e7-114">*表达式*中的操作数可以包括表字段或函数 （这可能是固有或用户定义但不是其他 SQL 聚合函数） 的名称。</span><span class="sxs-lookup"><span data-stu-id="5c9e7-114">Operands in  *Expression*  can include the name of a table field or function (which can be either intrinsic or user-defined but not other SQL aggregate functions).</span></span> <span data-ttu-id="5c9e7-115">可以计算包括文本在内的任何类型数据。</span><span class="sxs-lookup"><span data-stu-id="5c9e7-115">You can count any kind of data, including text.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5c9e7-116">说明</span><span class="sxs-lookup"><span data-stu-id="5c9e7-116">Remarks</span></span>

<span data-ttu-id="5c9e7-117">可以使用 Count 来统计基本查询的记录数。</span><span class="sxs-lookup"><span data-stu-id="5c9e7-117">You can use Count to count the number of records in an underlying query.</span></span> <span data-ttu-id="5c9e7-118">例如，可以使用 Count 来计算发往的特定国家或地区的订单数。</span><span class="sxs-lookup"><span data-stu-id="5c9e7-118">For example, you could use Count to count the number of orders shipped to a particular country or region.</span></span>
  
<span data-ttu-id="5c9e7-119">**计数**(\*) 返回组中的项目数。</span><span class="sxs-lookup"><span data-stu-id="5c9e7-119">**Count** (\*) returns the number of items in a group.</span></span> <span data-ttu-id="5c9e7-120">这包括 NULL 值和重复项。</span><span class="sxs-lookup"><span data-stu-id="5c9e7-120">This includes NULL values and duplicates.</span></span> 
  

