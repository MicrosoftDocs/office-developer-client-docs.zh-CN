---
title: ForEachRecord 数据块 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 8ffa0de2-5abb-4375-9fb5-042ce3c21506
description: ForEachRecord 数据块的域中的每个记录都重复一组语句。
ms.openlocfilehash: 8ad14a01be05de9fb34299e49a9737f2009ef5ef
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773459"
---
# <a name="foreachrecord-data-block-access-custom-web-app"></a><span data-ttu-id="2e054-103">ForEachRecord 数据块 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="2e054-103">ForEachRecord Data Block (Access custom web app)</span></span>

<span data-ttu-id="2e054-104">**ForEachRecord**数据块的域中的每个记录都重复一组语句。</span><span class="sxs-lookup"><span data-stu-id="2e054-104">A **ForEachRecord** data block repeats a set of statements for each record in a domain.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="2e054-p101"> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/zh-cn/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="2e054-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/zh-cn/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="2e054-107"> **ForEachRecord** 数据块仅适用于数据宏。</span><span class="sxs-lookup"><span data-stu-id="2e054-107">The **ForEachRecord** data block is available only in Data Macros.</span></span> 
  
## <a name="setting"></a><span data-ttu-id="2e054-108">设置</span><span class="sxs-lookup"><span data-stu-id="2e054-108">Setting</span></span>

<span data-ttu-id="2e054-109">**ForEachRecord** 操作具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="2e054-109">The **ForEachRecord** action has the following arguments.</span></span> 
  
|<span data-ttu-id="2e054-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="2e054-110">**Argument name**</span></span>|<span data-ttu-id="2e054-111">**必需**</span><span class="sxs-lookup"><span data-stu-id="2e054-111">**Required**</span></span>|<span data-ttu-id="2e054-112">**说明**</span><span class="sxs-lookup"><span data-stu-id="2e054-112">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2e054-113">**In**</span><span class="sxs-lookup"><span data-stu-id="2e054-113">**In**</span></span> <br/> |<span data-ttu-id="2e054-114">可访问</span><span class="sxs-lookup"><span data-stu-id="2e054-114">Yes</span></span>  <br/> |<span data-ttu-id="2e054-115">一个字符串，标识的记录执行操作的域。</span><span class="sxs-lookup"><span data-stu-id="2e054-115">A string that identifies the domain of records to operate on.</span></span> <span data-ttu-id="2e054-116">*在*参数可以包含表、 选择查询或 SQL 语句的名称。</span><span class="sxs-lookup"><span data-stu-id="2e054-116">The  *In*  argument can contain the name of the table, a select query, or a SQL statement.</span></span>  <br/> <span data-ttu-id="2e054-117">**注意**： 指定的域不能包括链接的表或 ODBC 数据源中存储的数据。</span><span class="sxs-lookup"><span data-stu-id="2e054-117">**NOTE**: The specified domain cannot include data stored in a linked table or ODBC data source.</span></span>           |
|<span data-ttu-id="2e054-118">**Where Condition**</span><span class="sxs-lookup"><span data-stu-id="2e054-118">**Where Condition**</span></span> <br/> |<span data-ttu-id="2e054-119">否</span><span class="sxs-lookup"><span data-stu-id="2e054-119">No</span></span>  <br/> |<span data-ttu-id="2e054-120">执行字符串表达式，用来限制在其上的数据区域**ForEachRecord**数据块。</span><span class="sxs-lookup"><span data-stu-id="2e054-120">A string expression used to restrict the range of data on which the **ForEachRecord** data block is performed.</span></span> <span data-ttu-id="2e054-121">例如，criteria通常是相当于 SQL 表达式中的 WHERE 子句位置，但是不使用 WHERE一词。</span><span class="sxs-lookup"><span data-stu-id="2e054-121">For example, criteria is often equivalent to the WHERE clause in an SQL expression, without the word WHERE.</span></span> <span data-ttu-id="2e054-122">如果条件都被忽略， **ForEachRecord**数据块运行上指定*中*参数的整个域。</span><span class="sxs-lookup"><span data-stu-id="2e054-122">If criteria are omitted, the **ForEachRecord** data block operates on the entire domain specified by the  *In*  argument.</span></span> <span data-ttu-id="2e054-123">条件中包括的任何字段必须同时是*中*的字段。</span><span class="sxs-lookup"><span data-stu-id="2e054-123">Any field that is included in criteria must also be a field in  *In*  .</span></span>  <br/> |
|<span data-ttu-id="2e054-124">**Alias**</span><span class="sxs-lookup"><span data-stu-id="2e054-124">**Alias**</span></span> <br/> |<span data-ttu-id="2e054-125">否</span><span class="sxs-lookup"><span data-stu-id="2e054-125">No</span></span>  <br/> |<span data-ttu-id="2e054-126">提供*在*参数指定的域的替代名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="2e054-126">A string that provides an alternative name for the domain specified by the  *In*  argument.</span></span> <span data-ttu-id="2e054-127">通常用于缩短后续参考，以防止可能出现的不明确引用的表名称。</span><span class="sxs-lookup"><span data-stu-id="2e054-127">Often used to shorten the table name for subsequent references to prevent possible ambiguous references.</span></span> <span data-ttu-id="2e054-128">如果未指定*别名*，则表或查询名称将用作别名。</span><span class="sxs-lookup"><span data-stu-id="2e054-128">If  *Alias*  is not specified, the table or query name will be used as the alias.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2e054-129">注释</span><span class="sxs-lookup"><span data-stu-id="2e054-129">Remarks</span></span>

<span data-ttu-id="2e054-130">使用 **[ExitForEachRecord](exitforeachrecord-macro-action-access-custom-web-app.md)** 操作可立即退出 **ForEachRecord** 数据块。</span><span class="sxs-lookup"><span data-stu-id="2e054-130">Use the **[ExitForEachRecord](exitforeachrecord-macro-action-access-custom-web-app.md)** action to exit a **ForEachRecord** data block immediately.</span></span> 
  

