---
title: LookupRecord 数据块 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 001899f7-5b1a-4c0b-a0e4-e01985eea818
description: LookupRecord 数据块可对特定记录执行一组操作。
ms.openlocfilehash: 7012fecdf0e73647b2b8177473dd8b5540b5fcca
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773483"
---
# <a name="lookuprecord-data-block-access-custom-web-app"></a><span data-ttu-id="c4dd8-103">LookupRecord 数据块 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="c4dd8-103">LookupRecord Data Block (Access custom web app)</span></span>

<span data-ttu-id="c4dd8-104">**LookupRecord** 数据块可对特定记录执行一组操作。</span><span class="sxs-lookup"><span data-stu-id="c4dd8-104">A **LookupRecord** data block performs a set of actions on a specific record.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="c4dd8-p101">[!重要信息] Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="c4dd8-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c4dd8-107">[!注释] **LookupRecord** 数据块仅适用于数据宏。</span><span class="sxs-lookup"><span data-stu-id="c4dd8-107">The **LookupRecord** data block is available only in Data Macros.</span></span> 
  
## <a name="setting"></a><span data-ttu-id="c4dd8-108">设置</span><span class="sxs-lookup"><span data-stu-id="c4dd8-108">Setting</span></span>

<span data-ttu-id="c4dd8-109">**SetField** 操作具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="c4dd8-109">The **SetField** action has the following arguments.</span></span> 
  
|<span data-ttu-id="c4dd8-110">**参数**</span><span class="sxs-lookup"><span data-stu-id="c4dd8-110">**Argument**</span></span>|<span data-ttu-id="c4dd8-111">**必需**</span><span class="sxs-lookup"><span data-stu-id="c4dd8-111">**Required**</span></span>|<span data-ttu-id="c4dd8-112">**说明**</span><span class="sxs-lookup"><span data-stu-id="c4dd8-112">**Description**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="c4dd8-113">_In_</span><span class="sxs-lookup"><span data-stu-id="c4dd8-113">_In_</span></span> <br/> |<span data-ttu-id="c4dd8-114">可访问</span><span class="sxs-lookup"><span data-stu-id="c4dd8-114">Yes</span></span>  <br/> |<span data-ttu-id="c4dd8-115">一个字符串，标识的记录执行操作。</span><span class="sxs-lookup"><span data-stu-id="c4dd8-115">A string that identifies the record to operate on.</span></span> <span data-ttu-id="c4dd8-116">*在*参数可以包含表、 选择查询或 SQL 语句的名称。</span><span class="sxs-lookup"><span data-stu-id="c4dd8-116">The  *In*  argument can contain the name of the table, a select query, or a SQL statement.</span></span>  <br/> |
| <span data-ttu-id="c4dd8-117">_Where Condition_</span><span class="sxs-lookup"><span data-stu-id="c4dd8-117">_Where Condition_</span></span> <br/> |<span data-ttu-id="c4dd8-118">否</span><span class="sxs-lookup"><span data-stu-id="c4dd8-118">No</span></span>  <br/> |<span data-ttu-id="c4dd8-119">执行字符串表达式，用来限制在其上的数据区域**LookupRecord**数据块。</span><span class="sxs-lookup"><span data-stu-id="c4dd8-119">A string expression used to restrict the range of data on which the **LookupRecord** data block is performed.</span></span> <span data-ttu-id="c4dd8-120">例如，criteria通常是相当于 SQL 表达式中的 WHERE 子句位置，但是不使用 WHERE一词。</span><span class="sxs-lookup"><span data-stu-id="c4dd8-120">For example, criteria is often equivalent to the WHERE clause in an SQL expression, without the word WHERE.</span></span> <span data-ttu-id="c4dd8-121">如果省略条件， **LookupRecord**数据块运行上指定*中*参数的整个域。</span><span class="sxs-lookup"><span data-stu-id="c4dd8-121">If criteria is omitted, the **LookupRecord** data block operates on the entire domain specified by the  *In*  argument.</span></span> <span data-ttu-id="c4dd8-122">条件中包括的任何字段必须同时是*中*的字段。</span><span class="sxs-lookup"><span data-stu-id="c4dd8-122">Any field that is included in criteria must also be a field in  *In*  .</span></span>  <br/> |
| <span data-ttu-id="c4dd8-123">_Alias_</span><span class="sxs-lookup"><span data-stu-id="c4dd8-123">_Alias_</span></span> <br/> |<span data-ttu-id="c4dd8-124">否</span><span class="sxs-lookup"><span data-stu-id="c4dd8-124">No</span></span>  <br/> |<span data-ttu-id="c4dd8-125">提供*在*参数指定的记录的替代名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="c4dd8-125">A string that provides an alternative name for the record specified by the  *In*  argument.</span></span> <span data-ttu-id="c4dd8-126">通常用于缩短后续参考，以防止可能出现的不明确引用的表名称。</span><span class="sxs-lookup"><span data-stu-id="c4dd8-126">Often used to shorten the table name for subsequent references to prevent possible ambiguous references.</span></span> <span data-ttu-id="c4dd8-127">如果未指定*别名*，则表或查询名称将用作别名。</span><span class="sxs-lookup"><span data-stu-id="c4dd8-127">If  *Alias*  is not specified, the table or query name will be used as the alias.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c4dd8-128">注释</span><span class="sxs-lookup"><span data-stu-id="c4dd8-128">Remarks</span></span>

<span data-ttu-id="c4dd8-129">如果  *In*  和  *Where Condition*  参数指定的条件指定了多条记录， **LookupRecord** 数据块将只对第一条记录执行操作。</span><span class="sxs-lookup"><span data-stu-id="c4dd8-129">If the criteria specified by the  *In*  and  *Where Condition*  arguments specifies more than one record, then the **LookupRecord** data block will only operate on the first record.</span></span> 
  
<span data-ttu-id="c4dd8-130">如果没有记录满足*Where Condition*或如果*中*不包含任何记录， **LookupRecord**将创建一个空的记录，其中的所有字段包含**Null**值。</span><span class="sxs-lookup"><span data-stu-id="c4dd8-130">If no record satisfies  *Where Condition*  or if  *In*  contains no records, then **LookupRecord** creates a blank record in which all of the fields contain a **Null** value.</span></span> 
  

