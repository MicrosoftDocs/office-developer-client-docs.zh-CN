---
title: RequeryRecords 宏操作 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 1dab102f-24af-4984-8020-a9fb06355639
description: 您可以使用 RequeryRecords 操作通过重新查询视图的源来刷新、排序和筛选活动视图中的数据。
ms.openlocfilehash: 69d88401abc0de417f7dc58e275c66f2037212aa
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32311009"
---
# <a name="requeryrecords-macro-action-access-custom-web-app"></a><span data-ttu-id="3ba84-103">RequeryRecords 宏操作 (Access 自定义 web 应用程序)</span><span class="sxs-lookup"><span data-stu-id="3ba84-103">RequeryRecords Macro Action (Access custom web app)</span></span>

<span data-ttu-id="3ba84-104">您可以使用**RequeryRecords**操作通过重新查询视图的源来刷新、排序和筛选活动视图中的数据。</span><span class="sxs-lookup"><span data-stu-id="3ba84-104">You can use the **RequeryRecords** action to refresh, sort, and filter the data in the active view by requerying the source of the view.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="3ba84-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="3ba84-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="setting"></a><span data-ttu-id="3ba84-107">设置</span><span class="sxs-lookup"><span data-stu-id="3ba84-107">Setting</span></span>

<span data-ttu-id="3ba84-108">**RequeryRecords**操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="3ba84-108">The **RequeryRecords** action has the following arguments.</span></span> 
  
|<span data-ttu-id="3ba84-109">**参数**</span><span class="sxs-lookup"><span data-stu-id="3ba84-109">**Parameter**</span></span>|<span data-ttu-id="3ba84-110">**必需**</span><span class="sxs-lookup"><span data-stu-id="3ba84-110">**Required**</span></span>|<span data-ttu-id="3ba84-111">**描述**</span><span class="sxs-lookup"><span data-stu-id="3ba84-111">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3ba84-112">**Where =**</span><span class="sxs-lookup"><span data-stu-id="3ba84-112">**Where=**</span></span> <br/> |<span data-ttu-id="3ba84-113">否</span><span class="sxs-lookup"><span data-stu-id="3ba84-113">No</span></span>  <br/> |<span data-ttu-id="3ba84-114">限制视图中的记录的 SQL WHERE 子句。</span><span class="sxs-lookup"><span data-stu-id="3ba84-114">A SQL WHERE clause that restricts the records in the view.</span></span> <span data-ttu-id="3ba84-115">默认情况下, 此参数为空。</span><span class="sxs-lookup"><span data-stu-id="3ba84-115">By default, this argument is blank.</span></span>  <br/> |
|<span data-ttu-id="3ba84-116">**OrderBy**</span><span class="sxs-lookup"><span data-stu-id="3ba84-116">**OrderBy**</span></span> <br/> |<span data-ttu-id="3ba84-117">否</span><span class="sxs-lookup"><span data-stu-id="3ba84-117">No</span></span>  <br/> |<span data-ttu-id="3ba84-118">一个字符串表达式，包含作为记录排序依据的一个或多个字段的名称或可选的 ASC 或 DESC 关键字。</span><span class="sxs-lookup"><span data-stu-id="3ba84-118">A string expression that includes the name of the field or fields on which to sort records and the optional ASC or DESC keywords.</span></span> <span data-ttu-id="3ba84-119">默认情况下, 此参数为空。</span><span class="sxs-lookup"><span data-stu-id="3ba84-119">By default, this argument is blank.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3ba84-120">注解</span><span class="sxs-lookup"><span data-stu-id="3ba84-120">Remarks</span></span>

<span data-ttu-id="3ba84-121">调用**RequeryRecords**操作时, 将清除用户应用的任何排序或筛选。</span><span class="sxs-lookup"><span data-stu-id="3ba84-121">Any sorting or filtering applied by the user is cleared when the **RequeryRecords** action is called.</span></span> 
  
<span data-ttu-id="3ba84-122">*OrderBy*参数是要对记录进行排序所依据的一个或多个字段的名称。</span><span class="sxs-lookup"><span data-stu-id="3ba84-122">The  *OrderBy*  argument is the name of the field or fields on which you want to sort records.</span></span> <span data-ttu-id="3ba84-123">如果使用多个字段名称，需用逗号 (,) 分隔每个名称。</span><span class="sxs-lookup"><span data-stu-id="3ba84-123">When you use more than one field name, separate the names with a comma (,).</span></span> 
  
<span data-ttu-id="3ba84-124">在设置*OrderBy*参数时, 默认情况下将按升序对记录进行排序。</span><span class="sxs-lookup"><span data-stu-id="3ba84-124">When you set the  *OrderBy*  argument, the records are sorted by default in ascending order.</span></span> 
  
<span data-ttu-id="3ba84-125">若要按降序顺序对记录进行排序, 请在*OrderBy*参数表达式的末尾输入 DESC。</span><span class="sxs-lookup"><span data-stu-id="3ba84-125">To sort records in descending order, enter DESC at the end of the  *OrderBy*  argument expression.</span></span> <span data-ttu-id="3ba84-126">例如, 若要按联系人姓名的降序对客户记录进行排序, 请将*OrderBy*参数设置为 "联系人姓名 DESC"。</span><span class="sxs-lookup"><span data-stu-id="3ba84-126">For example, to sort customer records in descending order by contact name, set the  *OrderBy*  argument to "ContactName DESC".</span></span> 
  
<span data-ttu-id="3ba84-127">若要按姓氏降序以及名字升序对名称进行排序, 请将*OrderBy*参数设置为 "LastName DESC, FirstName ASC"。</span><span class="sxs-lookup"><span data-stu-id="3ba84-127">To sort names by LastName descending, and FirstName ascending, set the  *OrderBy*  argument to "LastName DESC, FirstName ASC".</span></span> 
  

