---
title: ForEachRecord 数据块 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 8ffa0de2-5abb-4375-9fb5-042ce3c21506
description: ForEachRecord 数据块为域中的每条记录重复一组语句。
ms.openlocfilehash: 9715824bff7d478fa2880ada5e8770f7a0c88883
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32302455"
---
# <a name="foreachrecord-data-block-access-custom-web-app"></a><span data-ttu-id="d8621-103">ForEachRecord 数据块 (Access 自定义 web 应用程序)</span><span class="sxs-lookup"><span data-stu-id="d8621-103">ForEachRecord Data Block (Access custom web app)</span></span>

<span data-ttu-id="d8621-104">**ForEachRecord**数据块为域中的每条记录重复一组语句。</span><span class="sxs-lookup"><span data-stu-id="d8621-104">A **ForEachRecord** data block repeats a set of statements for each record in a domain.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="d8621-p101">[!重要信息] Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="d8621-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d8621-107">**ForEachRecord** 数据块仅适用于数据宏。</span><span class="sxs-lookup"><span data-stu-id="d8621-107">The **ForEachRecord** data block is available only in Data Macros.</span></span> 
  
## <a name="setting"></a><span data-ttu-id="d8621-108">Setting</span><span class="sxs-lookup"><span data-stu-id="d8621-108">Setting</span></span>

<span data-ttu-id="d8621-109">**ForEachRecord** 操作具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="d8621-109">The **ForEachRecord** action has the following arguments.</span></span> 
  
|<span data-ttu-id="d8621-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="d8621-110">**Argument name**</span></span>|<span data-ttu-id="d8621-111">**必需**</span><span class="sxs-lookup"><span data-stu-id="d8621-111">**Required**</span></span>|<span data-ttu-id="d8621-112">**描述**</span><span class="sxs-lookup"><span data-stu-id="d8621-112">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d8621-113">**实时**</span><span class="sxs-lookup"><span data-stu-id="d8621-113">**In**</span></span> <br/> |<span data-ttu-id="d8621-114">是</span><span class="sxs-lookup"><span data-stu-id="d8621-114">Yes</span></span>  <br/> |<span data-ttu-id="d8621-115">一个用于标识要对其执行操作的记录域的字符串。</span><span class="sxs-lookup"><span data-stu-id="d8621-115">A string that identifies the domain of records to operate on.</span></span> <span data-ttu-id="d8621-116">*In*参数可以包含表、选择查询或 SQL 语句的名称。</span><span class="sxs-lookup"><span data-stu-id="d8621-116">The  *In*  argument can contain the name of the table, a select query, or a SQL statement.</span></span>  <br/> <span data-ttu-id="d8621-117">**注意**: 指定的域不能包含存储在链接表或 ODBC 数据源中的数据。</span><span class="sxs-lookup"><span data-stu-id="d8621-117">**NOTE**: The specified domain cannot include data stored in a linked table or ODBC data source.</span></span>           |
|<span data-ttu-id="d8621-118">**Where 条件**</span><span class="sxs-lookup"><span data-stu-id="d8621-118">**Where Condition**</span></span> <br/> |<span data-ttu-id="d8621-119">否</span><span class="sxs-lookup"><span data-stu-id="d8621-119">No</span></span>  <br/> |<span data-ttu-id="d8621-120">一个字符串表达式, 用于限制要对其执行**ForEachRecord**数据块的数据的范围。</span><span class="sxs-lookup"><span data-stu-id="d8621-120">A string expression used to restrict the range of data on which the **ForEachRecord** data block is performed.</span></span> <span data-ttu-id="d8621-121">例如，条件通常相当于 SQL 表达式中的 WHERE 子句（无单词 WHERE）。</span><span class="sxs-lookup"><span data-stu-id="d8621-121">For example, criteria is often equivalent to the WHERE clause in an SQL expression, without the word WHERE.</span></span> <span data-ttu-id="d8621-122">如果省略条件, 则**ForEachRecord**数据块在由*In*参数指定的整个域上运行。</span><span class="sxs-lookup"><span data-stu-id="d8621-122">If criteria are omitted, the **ForEachRecord** data block operates on the entire domain specified by the  *In*  argument.</span></span> <span data-ttu-id="d8621-123">条件中包含的任何字段都必须也是中的字段\*\* 。</span><span class="sxs-lookup"><span data-stu-id="d8621-123">Any field that is included in criteria must also be a field in  *In*  .</span></span>  <br/> |
|<span data-ttu-id="d8621-124">**Alias**</span><span class="sxs-lookup"><span data-stu-id="d8621-124">**Alias**</span></span> <br/> |<span data-ttu-id="d8621-125">否</span><span class="sxs-lookup"><span data-stu-id="d8621-125">No</span></span>  <br/> |<span data-ttu-id="d8621-126">为*In*参数指定的域提供备用名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="d8621-126">A string that provides an alternative name for the domain specified by the  *In*  argument.</span></span> <span data-ttu-id="d8621-127">通常用于缩短后续引用的表名称，以防止可能出现的不明引用。</span><span class="sxs-lookup"><span data-stu-id="d8621-127">Often used to shorten the table name for subsequent references to prevent possible ambiguous references.</span></span> <span data-ttu-id="d8621-128">如果未指定*alias* , 则表或查询名称将用作别名。</span><span class="sxs-lookup"><span data-stu-id="d8621-128">If  *Alias*  is not specified, the table or query name will be used as the alias.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d8621-129">注解</span><span class="sxs-lookup"><span data-stu-id="d8621-129">Remarks</span></span>

<span data-ttu-id="d8621-130">使用 **[ExitForEachRecord](exitforeachrecord-macro-action-access-custom-web-app.md)** 操作可立即退出 **ForEachRecord** 数据块。</span><span class="sxs-lookup"><span data-stu-id="d8621-130">Use the **[ExitForEachRecord](exitforeachrecord-macro-action-access-custom-web-app.md)** action to exit a **ForEachRecord** data block immediately.</span></span> 
  

