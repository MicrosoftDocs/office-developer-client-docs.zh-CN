---
title: LookupRecord 数据块 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 001899f7-5b1a-4c0b-a0e4-e01985eea818
description: LookupRecord 数据块可对特定记录执行一组操作。
ms.openlocfilehash: a6d89b1700a47f88086fd8c4e7b594b90425912c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434359"
---
# <a name="lookuprecord-data-block-access-custom-web-app"></a><span data-ttu-id="707c3-103">LookupRecord 数据块 (Access 自定义 web 应用程序)</span><span class="sxs-lookup"><span data-stu-id="707c3-103">LookupRecord Data Block (Access custom web app)</span></span>

<span data-ttu-id="707c3-104">**LookupRecord** 数据块可对特定记录执行一组操作。</span><span class="sxs-lookup"><span data-stu-id="707c3-104">A **LookupRecord** data block performs a set of actions on a specific record.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="707c3-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="707c3-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="707c3-107">**LookupRecord** 数据块仅适用于数据宏。</span><span class="sxs-lookup"><span data-stu-id="707c3-107">The **LookupRecord** data block is available only in Data Macros.</span></span> 
  
## <a name="setting"></a><span data-ttu-id="707c3-108">Setting</span><span class="sxs-lookup"><span data-stu-id="707c3-108">Setting</span></span>

<span data-ttu-id="707c3-109">**SetField** 操作具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="707c3-109">The **SetField** action has the following arguments.</span></span> 
  
|<span data-ttu-id="707c3-110">**参数**</span><span class="sxs-lookup"><span data-stu-id="707c3-110">**Argument**</span></span>|<span data-ttu-id="707c3-111">**必需**</span><span class="sxs-lookup"><span data-stu-id="707c3-111">**Required**</span></span>|<span data-ttu-id="707c3-112">**描述**</span><span class="sxs-lookup"><span data-stu-id="707c3-112">**Description**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="707c3-113">_实时_</span><span class="sxs-lookup"><span data-stu-id="707c3-113">_In_</span></span> <br/> |<span data-ttu-id="707c3-114">是</span><span class="sxs-lookup"><span data-stu-id="707c3-114">Yes</span></span>  <br/> |<span data-ttu-id="707c3-115">一个用于标识要对其执行操作的记录的字符串。</span><span class="sxs-lookup"><span data-stu-id="707c3-115">A string that identifies the record to operate on.</span></span> <span data-ttu-id="707c3-116">*In*参数可以包含表、选择查询或 SQL 语句的名称。</span><span class="sxs-lookup"><span data-stu-id="707c3-116">The  *In*  argument can contain the name of the table, a select query, or a SQL statement.</span></span>  <br/> |
| <span data-ttu-id="707c3-117">_Where 条件_</span><span class="sxs-lookup"><span data-stu-id="707c3-117">_Where Condition_</span></span> <br/> |<span data-ttu-id="707c3-118">否</span><span class="sxs-lookup"><span data-stu-id="707c3-118">No</span></span>  <br/> |<span data-ttu-id="707c3-119">一个字符串表达式，用于限制对其执行 **LookupRecord** 数据块的数据的范围。</span><span class="sxs-lookup"><span data-stu-id="707c3-119">A string expression used to restrict the range of data on which the **LookupRecord** data block is performed.</span></span> <span data-ttu-id="707c3-120">例如，条件通常相当于 SQL 表达式中的 WHERE 子句（无单词 WHERE）。</span><span class="sxs-lookup"><span data-stu-id="707c3-120">For example, criteria is often equivalent to the WHERE clause in an SQL expression, without the word WHERE.</span></span> <span data-ttu-id="707c3-121">如果省略条件, 则**LookupRecord**数据块在由*In*参数指定的整个域上运行。</span><span class="sxs-lookup"><span data-stu-id="707c3-121">If criteria is omitted, the **LookupRecord** data block operates on the entire domain specified by the  *In*  argument.</span></span> <span data-ttu-id="707c3-122">条件中包含的任何字段都必须也是中的字段\*\* 。</span><span class="sxs-lookup"><span data-stu-id="707c3-122">Any field that is included in criteria must also be a field in  *In*  .</span></span>  <br/> |
| <span data-ttu-id="707c3-123">_Alias_</span><span class="sxs-lookup"><span data-stu-id="707c3-123">_Alias_</span></span> <br/> |<span data-ttu-id="707c3-124">否</span><span class="sxs-lookup"><span data-stu-id="707c3-124">No</span></span>  <br/> |<span data-ttu-id="707c3-125">为*In*参数所指定的记录提供可选名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="707c3-125">A string that provides an alternative name for the record specified by the  *In*  argument.</span></span> <span data-ttu-id="707c3-126">通常用于缩短后续引用的表名称，以防止可能出现的不明引用。</span><span class="sxs-lookup"><span data-stu-id="707c3-126">Often used to shorten the table name for subsequent references to prevent possible ambiguous references.</span></span> <span data-ttu-id="707c3-127">如果未指定*alias* , 则表或查询名称将用作别名。</span><span class="sxs-lookup"><span data-stu-id="707c3-127">If  *Alias*  is not specified, the table or query name will be used as the alias.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="707c3-128">说明</span><span class="sxs-lookup"><span data-stu-id="707c3-128">Remarks</span></span>

<span data-ttu-id="707c3-129">如果  *In*  和  *Where Condition*  参数指定的条件指定了多条记录， **LookupRecord** 数据块将只对第一条记录执行操作。</span><span class="sxs-lookup"><span data-stu-id="707c3-129">If the criteria specified by the  *In*  and  *Where Condition*  arguments specifies more than one record, then the **LookupRecord** data block will only operate on the first record.</span></span> 
  
<span data-ttu-id="707c3-130">如果没有记录满足*Where 条件*或*In*不包含记录, 则**LookupRecord**将创建一个空白记录, 其中所有字段都包含一个**Null**值。</span><span class="sxs-lookup"><span data-stu-id="707c3-130">If no record satisfies  *Where Condition*  or if  *In*  contains no records, then **LookupRecord** creates a blank record in which all of the fields contain a **Null** value.</span></span> 
  

