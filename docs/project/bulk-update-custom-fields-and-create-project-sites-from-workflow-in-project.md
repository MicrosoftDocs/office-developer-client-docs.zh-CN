---
title: 批量更新自定义字段并在 project Online 中创建项目网站
manager: soliver
ms.date: 08/10/2016
ms.audience: Developer
localization_priority: Normal
ms.assetid: 815131c6-190c-4f29-83bf-c853eee72821
description: 为帮助客户充分利用 project online 并提高服务可扩展性和灵活性, 我们为客户端对象模型添加了两种方法, 可在 Project Online 应用程序和工作流中使用。
ms.openlocfilehash: 4de42471cd8c2f12a982447ccffc27ec8104fa31
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355338"
---
# <a name="bulk-update-custom-fields-and-create-project-sites-from-a-workflow-in-project-online"></a><span data-ttu-id="224f3-103">批量更新自定义字段并通过 Project Online 中的工作流创建项目网站</span><span class="sxs-lookup"><span data-stu-id="224f3-103">Bulk update custom fields and create project sites from a workflow in Project Online</span></span>

<span data-ttu-id="224f3-104">为帮助客户充分利用 project online 并提高服务可扩展性和灵活性, 我们为客户端对象模型添加了两种方法, 可在 Project Online 应用程序和工作流中使用。</span><span class="sxs-lookup"><span data-stu-id="224f3-104">To help customers get the most out of Project Online and improve our service extensibility and flexibility, we've added two methods to the client-side object model that you can use in Project Online apps and workflows.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="224f3-105">**UpdateCustomFields**</span><span class="sxs-lookup"><span data-stu-id="224f3-105">**UpdateCustomFields**</span></span> <br/> |<span data-ttu-id="224f3-106">批量更新项目自定义域。</span><span class="sxs-lookup"><span data-stu-id="224f3-106">Bulk updates project custom fields.</span></span> <span data-ttu-id="224f3-107">仅适用于 Project Online。</span><span class="sxs-lookup"><span data-stu-id="224f3-107">For Project Online only.</span></span> <span data-ttu-id="224f3-108">仅适用于 REST API。</span><span class="sxs-lookup"><span data-stu-id="224f3-108">Available only in the REST API.</span></span>  <br/> |
|<span data-ttu-id="224f3-109">**CreateProjectSite**</span><span class="sxs-lookup"><span data-stu-id="224f3-109">**CreateProjectSite**</span></span> <br/> | <span data-ttu-id="224f3-110">创建项目网站。</span><span class="sxs-lookup"><span data-stu-id="224f3-110">Creates a Project site.</span></span> <span data-ttu-id="224f3-111">仅适用于 Project Online。</span><span class="sxs-lookup"><span data-stu-id="224f3-111">For Project Online only.</span></span> <span data-ttu-id="224f3-112">在 REST API、托管客户端对象模型和 JavaScript 客户端对象模型中可用。</span><span class="sxs-lookup"><span data-stu-id="224f3-112">Available in the REST API, managed client object model, and JavaScript client object model.</span></span>  <br/> |
   
<span data-ttu-id="224f3-113">除了提供更大的灵活性之外, 在工作流中保存和发布项目时, 这些方法还会显著提高性能。</span><span class="sxs-lookup"><span data-stu-id="224f3-113">In addition to providing more flexibility, these methods also offer significant performance improvements when saving and publishing projects in a workflow.</span></span> <span data-ttu-id="224f3-114">本文介绍如何使用 REST API 中的方法, 并提供有关创建批量更新自定义字段和创建项目网站的工作流的工作流的说明。</span><span class="sxs-lookup"><span data-stu-id="224f3-114">This article describes how to use the methods in the REST API and provides instructions for creating a workflow that bulk updates custom fields and a workflow that creates a Project site.</span></span>
  
> [!NOTE]
> <span data-ttu-id="224f3-115">若要了解有关从 sharepoint 2013 工作流调用 REST api 的详细信息, 请参阅[使用 sharepoint REST 服务从具有 POST 方法的工作流](https://mysharepointinsight.blogspot.com/2013/05/using-sharepoint-rest-services-from.mdl)和[从 sharepoint Designer 工作流调用 sharepoint 2013 REST API](https://sergeluca.wordpress.com/2013/04/09/calling-the-sharepoint-2013-rest-api-from-a-sharepoint-designer-workflow/)。</span><span class="sxs-lookup"><span data-stu-id="224f3-115">To learn more about calling REST APIs from SharePoint 2013 workflows, see [Using SharePoint REST services from workflow with POST method](https://mysharepointinsight.blogspot.com/2013/05/using-sharepoint-rest-services-from.mdl) and [Calling the SharePoint 2013 Rest API from a SharePoint Designer Workflow](https://sergeluca.wordpress.com/2013/04/09/calling-the-sharepoint-2013-rest-api-from-a-sharepoint-designer-workflow/).</span></span> 
  
## <a name="bulk-update-project-custom-fields-from-a-workflow"></a><span data-ttu-id="224f3-116">从工作流批量更新项目自定义域</span><span class="sxs-lookup"><span data-stu-id="224f3-116">Bulk update project custom fields from a workflow</span></span>
<span data-ttu-id="224f3-117"><a name="BulkUpdateCustomFields"> </a></span><span class="sxs-lookup"><span data-stu-id="224f3-117"></span></span>

<span data-ttu-id="224f3-118">以前, 工作流一次只能更新一个自定义字段。</span><span class="sxs-lookup"><span data-stu-id="224f3-118">Previously, workflows could only update one custom field at a time.</span></span> <span data-ttu-id="224f3-119">一次更新一个项目自定义域会导致用户在项目详细信息页面之间过渡时遇到较差的最终用户体验。</span><span class="sxs-lookup"><span data-stu-id="224f3-119">Updating project custom fields one at a time can result in a poor end-user experience when users transition between Project Detail Pages.</span></span> <span data-ttu-id="224f3-120">每次更新都需要使用**设置项目域**操作和更新多个自定义字段在高延迟 (低带宽网络) 上的单独服务器请求, 从而产生无意义的开销。</span><span class="sxs-lookup"><span data-stu-id="224f3-120">Each update required a separate server request using the **Set Project Field** action, and updating multiple custom fields on a high-latency, low-bandwidth network resulted in a non-trivial overhead.</span></span> <span data-ttu-id="224f3-121">若要解决此问题, 我们向 REST API 添加了**UpdateCustomFields**方法, 该方法允许您批量更新自定义字段。</span><span class="sxs-lookup"><span data-stu-id="224f3-121">To resolve this issue, we added the **UpdateCustomFields** method to the REST API that lets you bulk update custom fields.</span></span> <span data-ttu-id="224f3-122">若要使用**UpdateCustomFields**, 请在包含要更新的所有自定义域的名称和值的词典中进行传递。</span><span class="sxs-lookup"><span data-stu-id="224f3-122">To use **UpdateCustomFields**, you pass in a dictionary that contains the names and values of all the custom fields you want to update.</span></span>
  
<span data-ttu-id="224f3-123">可以在以下终结点找到 REST 方法:</span><span class="sxs-lookup"><span data-stu-id="224f3-123">The REST method can be found at the following endpoint:</span></span>
  
`https://<site-url>/_api/ProjectServer/Projects('<guid>')/Draft/UpdateCustomFields()`
  
> [!NOTE]
> <span data-ttu-id="224f3-124">将示例`<site-url>`中的占位符替换为 project Web App (PWA) 网站的 URL, 并将`<guid>`占位符替换为项目 UID。</span><span class="sxs-lookup"><span data-stu-id="224f3-124">Replace the  `<site-url>` placeholder in the examples with the URL of your Project Web App (PWA) site and the  `<guid>` placeholder with your project UID.</span></span> 
  
<span data-ttu-id="224f3-125">本节介绍如何创建批量更新项目的自定义字段的工作流。</span><span class="sxs-lookup"><span data-stu-id="224f3-125">This section describes how to create a workflow that bulk updates custom fields for a project.</span></span> <span data-ttu-id="224f3-126">工作流遵循以下高级别步骤:</span><span class="sxs-lookup"><span data-stu-id="224f3-126">The workflow follows these high-level steps:</span></span>
  
- <span data-ttu-id="224f3-127">等待要更新的项目以供签入</span><span class="sxs-lookup"><span data-stu-id="224f3-127">Wait for the project that you want to update to get checked in</span></span>
    
- <span data-ttu-id="224f3-128">构建一个定义项目的所有自定义字段更新的数据集</span><span class="sxs-lookup"><span data-stu-id="224f3-128">Build a data set that defines all your custom field updates for the project</span></span>
    
- <span data-ttu-id="224f3-129">签出项目</span><span class="sxs-lookup"><span data-stu-id="224f3-129">Check out the project</span></span>
    
- <span data-ttu-id="224f3-130">调用**UpdateCustomFields**以将自定义字段更新应用于项目</span><span class="sxs-lookup"><span data-stu-id="224f3-130">Call **UpdateCustomFields** to apply the custom field updates to the project</span></span> 
    
- <span data-ttu-id="224f3-131">将相关信息记录到工作流历史记录列表中 (如果需要)</span><span class="sxs-lookup"><span data-stu-id="224f3-131">Log relevant information to the workflow history list (if required)</span></span>
    
- <span data-ttu-id="224f3-132">发布项目</span><span class="sxs-lookup"><span data-stu-id="224f3-132">Publish the project</span></span>
    
- <span data-ttu-id="224f3-133">签入项目</span><span class="sxs-lookup"><span data-stu-id="224f3-133">Check in the project</span></span>
    
<span data-ttu-id="224f3-134">最终的端到端工作流如下所示:</span><span class="sxs-lookup"><span data-stu-id="224f3-134">The final, end-to-end workflow looks like this:</span></span>
  
<span data-ttu-id="224f3-135">![端到端工作流](media/8c0741f9-7f76-409d-8c00-e7a8c3ddb89f.png "端到端工作流")</span><span class="sxs-lookup"><span data-stu-id="224f3-135">![End-to-end workflow](media/8c0741f9-7f76-409d-8c00-e7a8c3ddb89f.png "End-to-end workflow")</span></span>
  
### <a name="to-create-a-workflow-that-bulk-updates-custom-fields"></a><span data-ttu-id="224f3-136">创建批量更新自定义字段的工作流</span><span class="sxs-lookup"><span data-stu-id="224f3-136">To create a workflow that bulk updates custom fields</span></span>

1. <span data-ttu-id="224f3-137">可选。</span><span class="sxs-lookup"><span data-stu-id="224f3-137">Optional.</span></span> <span data-ttu-id="224f3-138">将项目的完整 URL 存储在可在整个工作流中使用的变量中。</span><span class="sxs-lookup"><span data-stu-id="224f3-138">Store the full URL of your project in a variable that you can use throughout the workflow.</span></span>
    
    <span data-ttu-id="224f3-139">![将项目的 URL 存储在变量中](media/a880c5c6-8e7a-44dd-87e9-7e532169d489.png "将项目的 URL 存储在变量中")</span><span class="sxs-lookup"><span data-stu-id="224f3-139">![Store the URL of the project in a variable](media/a880c5c6-8e7a-44dd-87e9-7e532169d489.png "Store the URL of the project in a variable")</span></span>
  
2. <span data-ttu-id="224f3-140">将 "**等待项目事件**" 操作添加到工作流, 并选择 "在事件**中检查项目时**"。</span><span class="sxs-lookup"><span data-stu-id="224f3-140">Add the **Wait for Project Event** action to the workflow and choose the **When a project is checked in** event.</span></span> 
    
    <span data-ttu-id="224f3-141">![等待项目签入](media/699aa9c7-b3c9-426e-a775-96993a13559c.png "等待项目签入")</span><span class="sxs-lookup"><span data-stu-id="224f3-141">![Wait for the project to be checked in](media/699aa9c7-b3c9-426e-a775-96993a13559c.png "Wait for the project to be checked in")</span></span>
  
3. <span data-ttu-id="224f3-142">使用 "**生成字典**" 操作创建**requestHeader**字典。</span><span class="sxs-lookup"><span data-stu-id="224f3-142">Create a **requestHeader** dictionary using the **Build dictionary** action.</span></span> <span data-ttu-id="224f3-143">您将对此工作流中的所有 web 服务调用使用相同的请求标头。</span><span class="sxs-lookup"><span data-stu-id="224f3-143">You'll use the same request header for all the web service calls in this workflow.</span></span> 
    
    <span data-ttu-id="224f3-144">![生成 requestHeader 词典](media/83b0aa10-9ab7-43dd-800d-a738bb815876.png "生成 requestHeader 词典")</span><span class="sxs-lookup"><span data-stu-id="224f3-144">![Build the requestHeader dictionary](media/83b0aa10-9ab7-43dd-800d-a738bb815876.png "Build the requestHeader dictionary")</span></span>
  
4. <span data-ttu-id="224f3-145">将以下两个项添加到字典中。</span><span class="sxs-lookup"><span data-stu-id="224f3-145">Add the following two items to the dictionary.</span></span>
    
    |<span data-ttu-id="224f3-146">名称</span><span class="sxs-lookup"><span data-stu-id="224f3-146">Name</span></span>|<span data-ttu-id="224f3-147">类型</span><span class="sxs-lookup"><span data-stu-id="224f3-147">Type</span></span>|<span data-ttu-id="224f3-148">值</span><span class="sxs-lookup"><span data-stu-id="224f3-148">Value</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="224f3-149">Accept</span><span class="sxs-lookup"><span data-stu-id="224f3-149">Accept</span></span>  <br/> |<span data-ttu-id="224f3-150">字符串</span><span class="sxs-lookup"><span data-stu-id="224f3-150">String</span></span>  <br/> |<span data-ttu-id="224f3-151">application/json;odata = verbose</span><span class="sxs-lookup"><span data-stu-id="224f3-151">application/json; odata=verbose</span></span>  <br/> |
    |<span data-ttu-id="224f3-152">Content-Type</span><span class="sxs-lookup"><span data-stu-id="224f3-152">Content-Type</span></span>  <br/> |<span data-ttu-id="224f3-153">字符串</span><span class="sxs-lookup"><span data-stu-id="224f3-153">String</span></span>  <br/> |<span data-ttu-id="224f3-154">application/json;odata = verbose</span><span class="sxs-lookup"><span data-stu-id="224f3-154">application/json; odata=verbose</span></span>  <br/> |
   
    <span data-ttu-id="224f3-155">![添加接受标头](media/2f2e2016-3c49-4cac-b1e7-f2b8118b840c.png "添加接受标头")</span><span class="sxs-lookup"><span data-stu-id="224f3-155">![Adding an Accept header](media/2f2e2016-3c49-4cac-b1e7-f2b8118b840c.png "Adding an Accept header")</span></span>
  
5. <span data-ttu-id="224f3-156">使用 "**生成字典**" 操作创建**requestBody**字典。</span><span class="sxs-lookup"><span data-stu-id="224f3-156">Create a **requestBody** dictionary using the **Build dictionary** action.</span></span> <span data-ttu-id="224f3-157">此字典存储要应用的所有域更新。</span><span class="sxs-lookup"><span data-stu-id="224f3-157">This dictionary stores all the field updates that you want to apply.</span></span> 
    
    <span data-ttu-id="224f3-158">每个自定义字段更新需要四行: 字段的 (1) 元数据类型、(2) 键、(3) 值和 (4) 值类型。</span><span class="sxs-lookup"><span data-stu-id="224f3-158">Each custom field update requires four rows: the field's (1) metadata type, (2) key, (3) value, and (4) value type.</span></span>
    
    - <span data-ttu-id="224f3-159">**__metadata/type**字段的元数据类型。</span><span class="sxs-lookup"><span data-stu-id="224f3-159">**__metadata/type** The field's metadata type.</span></span> <span data-ttu-id="224f3-160">此记录始终是相同的, 并使用以下值:</span><span class="sxs-lookup"><span data-stu-id="224f3-160">This record is always the same and uses the following values:</span></span> 
    
       - <span data-ttu-id="224f3-161">Name: customFieldDictionary (i)/__metadata/type (其中**i**是字典中每个自定义字段的索引, 从0开始)</span><span class="sxs-lookup"><span data-stu-id="224f3-161">Name: customFieldDictionary(i)/__metadata/type (where **i** is the index of each custom field in the dictionary, starting with 0)</span></span> 
            
       - <span data-ttu-id="224f3-162">类型：字符串</span><span class="sxs-lookup"><span data-stu-id="224f3-162">Type: String</span></span>
            
       - <span data-ttu-id="224f3-163">Value: SP。键值</span><span class="sxs-lookup"><span data-stu-id="224f3-163">Value: SP.KeyValue</span></span>
    
       <span data-ttu-id="224f3-164">![定义自定义字段更新](media/a4423493-6603-42ee-ae50-1ef74c5c59bd.png "定义自定义字段更新")</span><span class="sxs-lookup"><span data-stu-id="224f3-164">![Defining a custom field update](media/a4423493-6603-42ee-ae50-1ef74c5c59bd.png "Defining a custom field update")</span></span>
  
    - <span data-ttu-id="224f3-165">**键**自定义字段的内部名称, 格式为: *Custom_ce23fbf43fa0e411941000155d3c8201*</span><span class="sxs-lookup"><span data-stu-id="224f3-165">**Key** The internal name of the custom field, in the format: *Custom_ce23fbf43fa0e411941000155d3c8201*</span></span> 
    
       <span data-ttu-id="224f3-166">您可以通过导航到自定义字段的**InternalName**终结点来查找该自定义字段的内部名称:`https://<site-url>/_api/ProjectServer/CustomFields('<guid>')/InternalName`</span><span class="sxs-lookup"><span data-stu-id="224f3-166">You can find the internal name of a custom field by navigating to it's **InternalName** endpoint: `https://<site-url>/_api/ProjectServer/CustomFields('<guid>')/InternalName`</span></span>
    
       <span data-ttu-id="224f3-167">如果手动创建自定义字段, 则这些值将不同于网站。</span><span class="sxs-lookup"><span data-stu-id="224f3-167">If you created your custom fields manually, the values will differ from site to site.</span></span> <span data-ttu-id="224f3-168">如果您计划跨多个网站重用工作流, 请确保自定义域 id 正确。</span><span class="sxs-lookup"><span data-stu-id="224f3-168">If you plan to reuse the workflow across multiple sites, make sure the custom field IDs are correct.</span></span>
    
    - <span data-ttu-id="224f3-169">**值**要分配给自定义域的值。</span><span class="sxs-lookup"><span data-stu-id="224f3-169">**Value** The value to assign to the custom field.</span></span> <span data-ttu-id="224f3-170">对于链接到查阅表格的自定义域, 您需要使用查阅表格条目的内部名称, 而不是实际的查阅表格值。</span><span class="sxs-lookup"><span data-stu-id="224f3-170">For custom fields that are linked to lookup tables, you need to use the internal names of the lookup table entries instead of the actual lookup table values.</span></span> 
    
       <span data-ttu-id="224f3-171">您可以在以下终结点查找查找表条目的内部名称:`https://<site-url>/_api/ProjectServer/CustomFields('<guid>')/LookupEntries('<guid>')/InternalName`</span><span class="sxs-lookup"><span data-stu-id="224f3-171">You can find the internal name of the lookup table entry at the following endpoint: `https://<site-url>/_api/ProjectServer/CustomFields('<guid>')/LookupEntries('<guid>')/InternalName`</span></span>
    
       <span data-ttu-id="224f3-172">如果有一个查阅表格自定义字段设置为接受多个值, 请`;#`使用连接值 (如下面的示例字典所示)。</span><span class="sxs-lookup"><span data-stu-id="224f3-172">If you have a lookup table custom field set up to accept multiple values, use  `;#` to concatenate values (as shown in the example dictionary below).</span></span> 
    
    - <span data-ttu-id="224f3-173">**ValueType**您要更新的自定义域的类型。</span><span class="sxs-lookup"><span data-stu-id="224f3-173">**ValueType** The type of the custom field you are updating.</span></span> 
    
       - <span data-ttu-id="224f3-174">对于 "文本"、"持续时间"、"标志" 和 "LookupTable" 字段, 使用 Edm. String</span><span class="sxs-lookup"><span data-stu-id="224f3-174">For Text, Duration, Flag, and LookupTable fields, use Edm.String</span></span>
    
       - <span data-ttu-id="224f3-175">对于 Number 字段, 请使用 Edm、edm 或任何其他 OData-接受的数字类型</span><span class="sxs-lookup"><span data-stu-id="224f3-175">For Number fields, use Edm.Int32, Edm.Double, or any other OData-accepted number type</span></span>
    
       - <span data-ttu-id="224f3-176">对于 "日期" 字段, 使用 Edm. DateTime</span><span class="sxs-lookup"><span data-stu-id="224f3-176">For Date fields, use Edm.DateTime</span></span>
    
       <span data-ttu-id="224f3-177">下面的示例字典定义了三个自定义域的更新。</span><span class="sxs-lookup"><span data-stu-id="224f3-177">The example dictionary below defines updates for three custom fields.</span></span> <span data-ttu-id="224f3-178">第一个是针对多值查阅表格自定义域, 第二个用于 "数字" 字段, 第三个用于 "日期" 字段。</span><span class="sxs-lookup"><span data-stu-id="224f3-178">The first is for a multiple value lookup table custom field, the second is for a number field, and the third is for a date field.</span></span> <span data-ttu-id="224f3-179">请注意**customFieldDictionary**索引是如何递增的。</span><span class="sxs-lookup"><span data-stu-id="224f3-179">Note how the **customFieldDictionary** index increments.</span></span> 
    
       > [!NOTE]
       > <span data-ttu-id="224f3-180">这些值仅用于说明目的。</span><span class="sxs-lookup"><span data-stu-id="224f3-180">These values are for illustration purposes only.</span></span> <span data-ttu-id="224f3-181">您将使用的键值对取决于 PWA 数据。</span><span class="sxs-lookup"><span data-stu-id="224f3-181">The key-value pairs you'll use depend on your PWA data.</span></span> 
  
       |<span data-ttu-id="224f3-182">名称</span><span class="sxs-lookup"><span data-stu-id="224f3-182">Name</span></span>|<span data-ttu-id="224f3-183">类型</span><span class="sxs-lookup"><span data-stu-id="224f3-183">Type</span></span>|<span data-ttu-id="224f3-184">值</span><span class="sxs-lookup"><span data-stu-id="224f3-184">Value</span></span>|
       |:-----|:-----|:-----|
       |<span data-ttu-id="224f3-185">customFieldDictionary (0)/__metadata/type</span><span class="sxs-lookup"><span data-stu-id="224f3-185">customFieldDictionary(0)/__metadata/type</span></span>  <br/> |<span data-ttu-id="224f3-186">字符串</span><span class="sxs-lookup"><span data-stu-id="224f3-186">String</span></span>  <br/> |<span data-ttu-id="224f3-187">SP.键值</span><span class="sxs-lookup"><span data-stu-id="224f3-187">SP.KeyValue</span></span>  <br/> |
       |<span data-ttu-id="224f3-188">customFieldDictionary (0)/Key</span><span class="sxs-lookup"><span data-stu-id="224f3-188">customFieldDictionary(0)/Key</span></span>  <br/> |<span data-ttu-id="224f3-189">字符串</span><span class="sxs-lookup"><span data-stu-id="224f3-189">String</span></span>  <br/> |<span data-ttu-id="224f3-190">自\_定义 ce23fbf43fa0e411941000155d3c8201</span><span class="sxs-lookup"><span data-stu-id="224f3-190">Custom\_ce23fbf43fa0e411941000155d3c8201</span></span>  <br/> |
       |<span data-ttu-id="224f3-191">customFieldDictionary (0)/Value</span><span class="sxs-lookup"><span data-stu-id="224f3-191">customFieldDictionary(0)/Value</span></span>  <br/> |<span data-ttu-id="224f3-192">字符串</span><span class="sxs-lookup"><span data-stu-id="224f3-192">String</span></span>  <br/> |<span data-ttu-id="224f3-193">条目\_b9a2fd69279de411940f00155d3c8201; #Entry\_baa2fd69279de411940f00155d3c8201</span><span class="sxs-lookup"><span data-stu-id="224f3-193">Entry\_b9a2fd69279de411940f00155d3c8201;#Entry\_baa2fd69279de411940f00155d3c8201</span></span>  <br/> |
       |<span data-ttu-id="224f3-194">customFieldDictionary (0)/ValueType</span><span class="sxs-lookup"><span data-stu-id="224f3-194">customFieldDictionary(0)/ValueType</span></span>  <br/> |<span data-ttu-id="224f3-195">字符串</span><span class="sxs-lookup"><span data-stu-id="224f3-195">String</span></span>  <br/> |<span data-ttu-id="224f3-196">Edm.String</span><span class="sxs-lookup"><span data-stu-id="224f3-196">Edm.String</span></span>  <br/> |
       |<span data-ttu-id="224f3-197">customFieldDictionary (1)/__metadata/type</span><span class="sxs-lookup"><span data-stu-id="224f3-197">customFieldDictionary(1)/__metadata/type</span></span>  <br/> |<span data-ttu-id="224f3-198">字符串</span><span class="sxs-lookup"><span data-stu-id="224f3-198">String</span></span>  <br/> |<span data-ttu-id="224f3-199">SP.键值</span><span class="sxs-lookup"><span data-stu-id="224f3-199">SP.KeyValue</span></span>  <br/> |
       |<span data-ttu-id="224f3-200">customFieldDictionary (1)/Key</span><span class="sxs-lookup"><span data-stu-id="224f3-200">customFieldDictionary(1)/Key</span></span>  <br/> |<span data-ttu-id="224f3-201">字符串</span><span class="sxs-lookup"><span data-stu-id="224f3-201">String</span></span>  <br/> |<span data-ttu-id="224f3-202">Custom_c7f114c97098e411940f00155d3c8201</span><span class="sxs-lookup"><span data-stu-id="224f3-202">Custom_c7f114c97098e411940f00155d3c8201</span></span>  <br/> |
       |<span data-ttu-id="224f3-203">customFieldDictionary (1)/Value</span><span class="sxs-lookup"><span data-stu-id="224f3-203">customFieldDictionary(1)/Value</span></span>  <br/> |<span data-ttu-id="224f3-204">字符串</span><span class="sxs-lookup"><span data-stu-id="224f3-204">String</span></span>  <br/> |<span data-ttu-id="224f3-205">90。5</span><span class="sxs-lookup"><span data-stu-id="224f3-205">90.5</span></span>  <br/> |
       |<span data-ttu-id="224f3-206">customFieldDictionary (1)/ValueType</span><span class="sxs-lookup"><span data-stu-id="224f3-206">customFieldDictionary(1)/ValueType</span></span>  <br/> |<span data-ttu-id="224f3-207">字符串</span><span class="sxs-lookup"><span data-stu-id="224f3-207">String</span></span>  <br/> |<span data-ttu-id="224f3-208">Edm.Double</span><span class="sxs-lookup"><span data-stu-id="224f3-208">Edm.Double</span></span>  <br/> |
       |<span data-ttu-id="224f3-209">customFieldDictionary (2)/__metadata/type</span><span class="sxs-lookup"><span data-stu-id="224f3-209">customFieldDictionary(2)/__metadata/type</span></span>  <br/> |<span data-ttu-id="224f3-210">字符串</span><span class="sxs-lookup"><span data-stu-id="224f3-210">String</span></span>  <br/> |<span data-ttu-id="224f3-211">SP.键值</span><span class="sxs-lookup"><span data-stu-id="224f3-211">SP.KeyValue</span></span>  <br/> |
       |<span data-ttu-id="224f3-212">customFieldDictionary (2)/Key</span><span class="sxs-lookup"><span data-stu-id="224f3-212">customFieldDictionary(2)/Key</span></span>  <br/> |<span data-ttu-id="224f3-213">字符串</span><span class="sxs-lookup"><span data-stu-id="224f3-213">String</span></span>  <br/> |<span data-ttu-id="224f3-214">Custom_c6fb67e0b9a1e411941000155d3c8201</span><span class="sxs-lookup"><span data-stu-id="224f3-214">Custom_c6fb67e0b9a1e411941000155d3c8201</span></span>  <br/> |
       |<span data-ttu-id="224f3-215">customFieldDictionary (2)/Value</span><span class="sxs-lookup"><span data-stu-id="224f3-215">customFieldDictionary(2)/Value</span></span>  <br/> |<span data-ttu-id="224f3-216">字符串</span><span class="sxs-lookup"><span data-stu-id="224f3-216">String</span></span>  <br/> |<span data-ttu-id="224f3-217">2015-04-01T00:00: 00.0000000</span><span class="sxs-lookup"><span data-stu-id="224f3-217">2015-04-01T00:00:00.0000000</span></span>  <br/> |
       |<span data-ttu-id="224f3-218">customFieldDictionary (2)/ValueType</span><span class="sxs-lookup"><span data-stu-id="224f3-218">customFieldDictionary(2)/ValueType</span></span>  <br/> |<span data-ttu-id="224f3-219">字符串</span><span class="sxs-lookup"><span data-stu-id="224f3-219">String</span></span>  <br/> |<span data-ttu-id="224f3-220">Edm.DateTime</span><span class="sxs-lookup"><span data-stu-id="224f3-220">Edm.DateTime</span></span>  <br/> |
   
       <span data-ttu-id="224f3-221">![定义自定义字段更新的字典](media/41a1f18f-a6b2-40ff-904b-437baf962621.png "定义自定义字段更新的字典")</span><span class="sxs-lookup"><span data-stu-id="224f3-221">![Dictionary that defines custom field updates](media/41a1f18f-a6b2-40ff-904b-437baf962621.png "Dictionary that defines custom field updates")</span></span>
  
6. <span data-ttu-id="224f3-222">添加 "**调用 HTTP Web 服务**" 操作以签出项目。</span><span class="sxs-lookup"><span data-stu-id="224f3-222">Add a **Call HTTP Web Service** action to check the project out.</span></span> 
    
    <span data-ttu-id="224f3-223">![调用 Checkout 方法](media/8ce56014-0317-419b-afa7-229d05c86885.png "调用 Checkout 方法")</span><span class="sxs-lookup"><span data-stu-id="224f3-223">![Call the Checkout method](media/8ce56014-0317-419b-afa7-229d05c86885.png "Call the Checkout method")</span></span>
  
7. <span data-ttu-id="224f3-224">编辑 web 服务调用的属性, 以指定请求标头。</span><span class="sxs-lookup"><span data-stu-id="224f3-224">Edit the properties of the web service call to specify the request header.</span></span> <span data-ttu-id="224f3-225">若要打开 "**属性**" 对话框, 请右键单击该操作, 然后选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="224f3-225">To open the **Properties** dialog box, right-click the action and choose **Properties**.</span></span>
    
    <span data-ttu-id="224f3-226">![在 web 服务调用属性中指定请求标头](media/d81e92b1-43df-42ad-9cd0-a693f93b164e.png "在 web 服务调用属性中指定请求标头")</span><span class="sxs-lookup"><span data-stu-id="224f3-226">![Specify the request header in web service call properties](media/d81e92b1-43df-42ad-9cd0-a693f93b164e.png "Specify the request header in web service call properties")</span></span>
  
8. <span data-ttu-id="224f3-227">添加 "**调用 HTTP Web 服务**" 操作以调用**UpdateCustomFields**方法。</span><span class="sxs-lookup"><span data-stu-id="224f3-227">Add a **Call HTTP Web Service** action to call the **UpdateCustomFields** method.</span></span> 
    
    <span data-ttu-id="224f3-228">![创建呼叫 HTTP Web 服务操作](media/9a73a201-c035-41b4-8798-506ac48b90f8.png "创建呼叫 HTTP Web 服务操作")</span><span class="sxs-lookup"><span data-stu-id="224f3-228">![Create a Call HTTP Web Service action](media/9a73a201-c035-41b4-8798-506ac48b90f8.png "Create a Call HTTP Web Service action")</span></span>
  
    <span data-ttu-id="224f3-229">记下`/Draft/` web 服务 URL 中的段。</span><span class="sxs-lookup"><span data-stu-id="224f3-229">Note the  `/Draft/` segment in the web service URL.</span></span> <span data-ttu-id="224f3-230">完整的 URL 应如下所示:`https://<site-url>/_api/ProjectServer/Projects('<guid>')/Draft/UpdateCustomFields()`</span><span class="sxs-lookup"><span data-stu-id="224f3-230">The full URL should look like this: `https://<site-url>/_api/ProjectServer/Projects('<guid>')/Draft/UpdateCustomFields()`</span></span>
    
    <span data-ttu-id="224f3-231">![调用 UpdateCustomFields 方法](media/03b323f1-8e99-4b18-be18-be505d7cec7e.png "调用 UpdateCustomFields 方法")</span><span class="sxs-lookup"><span data-stu-id="224f3-231">![Call the UpdateCustomFields method](media/03b323f1-8e99-4b18-be18-be505d7cec7e.png "Call the UpdateCustomFields method")</span></span>
  
9. <span data-ttu-id="224f3-232">编辑 web 服务调用的属性, 将**RequestHeader**和**RequestContent**参数绑定到您创建的词典。</span><span class="sxs-lookup"><span data-stu-id="224f3-232">Edit the properties of the web service call to bind the **RequestHeader** and **RequestContent** parameters to the dictionaries you created.</span></span> <span data-ttu-id="224f3-233">您还可以创建新变量来存储**ResponseContent**。</span><span class="sxs-lookup"><span data-stu-id="224f3-233">You can also create a new variable to store the **ResponseContent**.</span></span>
    
    <span data-ttu-id="224f3-234">![将词典绑定到请求标头和内容](media/f96bec92-138e-4eab-b1e7-1ab83d0428a5.png "将词典绑定到请求标头和内容")</span><span class="sxs-lookup"><span data-stu-id="224f3-234">![Bind the dictionaries to the request header and content](media/f96bec92-138e-4eab-b1e7-1ab83d0428a5.png "Bind the dictionaries to the request header and content")</span></span>
  
10. <span data-ttu-id="224f3-235">可选。</span><span class="sxs-lookup"><span data-stu-id="224f3-235">Optional.</span></span> <span data-ttu-id="224f3-236">从响应字典中读取以检查队列作业的状态, 并将信息记录在 "工作流历史记录" 列表中。</span><span class="sxs-lookup"><span data-stu-id="224f3-236">Read from the response dictionary to check the state of the queue job and log the information in the workflow history list.</span></span>
    
    <span data-ttu-id="224f3-237">![设置日志记录](media/7d2f4936-61d7-4906-83e8-7478a5935af5.png "设置日志记录")</span><span class="sxs-lookup"><span data-stu-id="224f3-237">![Setting up logging](media/7d2f4936-61d7-4906-83e8-7478a5935af5.png "Setting up logging")</span></span>
  
11. <span data-ttu-id="224f3-238">将 web 服务调用添加到**发布**终结点以发布项目。</span><span class="sxs-lookup"><span data-stu-id="224f3-238">Add a web service call to the **Publish** endpoint to publish the project.</span></span> <span data-ttu-id="224f3-239">始终使用相同的请求标头。</span><span class="sxs-lookup"><span data-stu-id="224f3-239">Always use the same request header.</span></span> 
    
    <span data-ttu-id="224f3-240">![调用 Publish 方法](media/3b661091-ffae-4d7e-a0bb-5b96a6292731.png "调用 Publish 方法")</span><span class="sxs-lookup"><span data-stu-id="224f3-240">![Call the Publish method](media/3b661091-ffae-4d7e-a0bb-5b96a6292731.png "Call the Publish method")</span></span>
  
    <span data-ttu-id="224f3-241">![发布 web 服务调用的属性](media/6a80a5d3-7e29-4398-993c-f78b3faca8b1.png "发布 web 服务调用的属性")</span><span class="sxs-lookup"><span data-stu-id="224f3-241">![Properties for the Publish web service call](media/6a80a5d3-7e29-4398-993c-f78b3faca8b1.png "Properties for the Publish web service call")</span></span>
  
12. <span data-ttu-id="224f3-242">向**签入**终结点添加最终 web 服务调用, 以检查中的项目。</span><span class="sxs-lookup"><span data-stu-id="224f3-242">Add a final web service call to the **Checkin** endpoint to check the project in.</span></span> 
    
    <span data-ttu-id="224f3-243">![调用签入方法](media/430510cb-0774-4911-af7f-b565b83eba0e.png "调用签入方法")</span><span class="sxs-lookup"><span data-stu-id="224f3-243">![Call the Checkin method](media/430510cb-0774-4911-af7f-b565b83eba0e.png "Call the Checkin method")</span></span>
  
    <span data-ttu-id="224f3-244">![签入 web 服务调用的属性](media/485f48d6-bbb8-4568-9dc3-aae3218f6bd1.png "签入 web 服务调用的属性")</span><span class="sxs-lookup"><span data-stu-id="224f3-244">![Properties for the Checkin web service call](media/485f48d6-bbb8-4568-9dc3-aae3218f6bd1.png "Properties for the Checkin web service call")</span></span>

<span data-ttu-id="224f3-245"><a name="CreateProjectSite"> </a></span><span class="sxs-lookup"><span data-stu-id="224f3-245"></span></span>

## <a name="create-a-project-site-from-a-workflow"></a><span data-ttu-id="224f3-246">从工作流创建项目网站</span><span class="sxs-lookup"><span data-stu-id="224f3-246">Create a Project site from a workflow</span></span>

<span data-ttu-id="224f3-247">每个项目都可以拥有自己的专用 SharePoint 网站, 工作组成员可以在其中进行协作、共享文档、提出问题等。</span><span class="sxs-lookup"><span data-stu-id="224f3-247">Every project can have its own dedicated SharePoint sites where team members can collaborate, share documents, raise issues, and so on.</span></span> <span data-ttu-id="224f3-248">以前, 只有在 project Professional 中的项目经理或由 PWA 设置中的管理员手动发布或手动创建网站时, 才能自动创建网站, 否则这些网站可能会被禁用。</span><span class="sxs-lookup"><span data-stu-id="224f3-248">Previously, sites could only be created automatically on first publish or manually by the project manager in Project Professional or by the administrator in PWA settings, or they could be disabled.</span></span>
  
<span data-ttu-id="224f3-249">我们已经添加了**CreateProjectSite**方法, 以便您可以选择何时创建项目网站。</span><span class="sxs-lookup"><span data-stu-id="224f3-249">We've added the **CreateProjectSite** method so you can choose when to create project sites.</span></span> <span data-ttu-id="224f3-250">对于希望在项目建议到达预定义工作流中的特定阶段 (而不是第一次发布) 时自动创建其网站的组织而言, 这一点尤其有用。</span><span class="sxs-lookup"><span data-stu-id="224f3-250">This is particularly useful for organizations who want to create their sites automatically when a project proposal reaches a specific stage in a pre-defined workflow, rather than on first publish.</span></span> <span data-ttu-id="224f3-251">推迟创建项目网站可大大提高项目的创建性能。</span><span class="sxs-lookup"><span data-stu-id="224f3-251">Postponing project site creation significantly improves the performance of creating a project.</span></span> 
  
<span data-ttu-id="224f3-252">**先决条件:** 在使用**CreateProjectSite**之前, 必须为在**PWA 设置**> \* \* 连接的 SharePoint 网站 \* \* >**设置**中的项目网站创建设置 "**允许用户选择**设置"。</span><span class="sxs-lookup"><span data-stu-id="224f3-252">**Prerequisite:** Before you can use **CreateProjectSite**, the **Allow users to choose** setting must be set for project site creation in **PWA Settings** > \*\* Connected SharePoint Sites \*\* > **Settings**.</span></span>
  
<span data-ttu-id="224f3-253">![在 PWA 设置中设置 "允许用户选择"](media/6c6c8175-eb10-431d-8056-cea55718fdb4.png "设置允许用户在 PWA 设置中进行选择")</span><span class="sxs-lookup"><span data-stu-id="224f3-253">![Setting "Allow users to choose" in PWA settings](media/6c6c8175-eb10-431d-8056-cea55718fdb4.png "Setting Allow users to choose in PWA settings")</span></span>
  
### <a name="to-create-a-workflow-that-creates-a-project-site"></a><span data-ttu-id="224f3-254">创建创建项目网站的工作流</span><span class="sxs-lookup"><span data-stu-id="224f3-254">To create a workflow that creates a Project site</span></span>

1. <span data-ttu-id="224f3-255">创建或编辑现有工作流, 然后选择要在其中创建项目网站的步骤。</span><span class="sxs-lookup"><span data-stu-id="224f3-255">Create or edit an existing workflow and select the step where you want to create your Project sites.</span></span>
    
2. <span data-ttu-id="224f3-256">使用 "**生成字典**" 操作创建**requestHeader**字典。</span><span class="sxs-lookup"><span data-stu-id="224f3-256">Create a **requestHeader** dictionary using the **Build dictionary** action.</span></span> 
    
    <span data-ttu-id="224f3-257">![生成 requestHeader 词典](media/83b0aa10-9ab7-43dd-800d-a738bb815876.png "生成 requestHeader 词典")</span><span class="sxs-lookup"><span data-stu-id="224f3-257">![Build the requestHeader dictionary](media/83b0aa10-9ab7-43dd-800d-a738bb815876.png "Build the requestHeader dictionary")</span></span>
  
3. <span data-ttu-id="224f3-258">将以下两个项添加到字典中。</span><span class="sxs-lookup"><span data-stu-id="224f3-258">Add the following two items to the dictionary.</span></span>
    
    |<span data-ttu-id="224f3-259">名称</span><span class="sxs-lookup"><span data-stu-id="224f3-259">Name</span></span>|<span data-ttu-id="224f3-260">类型</span><span class="sxs-lookup"><span data-stu-id="224f3-260">Type</span></span>|<span data-ttu-id="224f3-261">值</span><span class="sxs-lookup"><span data-stu-id="224f3-261">Value</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="224f3-262">Accept</span><span class="sxs-lookup"><span data-stu-id="224f3-262">Accept</span></span>  <br/> |<span data-ttu-id="224f3-263">字符串</span><span class="sxs-lookup"><span data-stu-id="224f3-263">String</span></span>  <br/> |<span data-ttu-id="224f3-264">application/json;odata = verbose</span><span class="sxs-lookup"><span data-stu-id="224f3-264">application/json; odata=verbose</span></span>  <br/> |
    |<span data-ttu-id="224f3-265">Content-Type</span><span class="sxs-lookup"><span data-stu-id="224f3-265">Content-Type</span></span>  <br/> |<span data-ttu-id="224f3-266">字符串</span><span class="sxs-lookup"><span data-stu-id="224f3-266">String</span></span>  <br/> |<span data-ttu-id="224f3-267">application/json;odata = verbose</span><span class="sxs-lookup"><span data-stu-id="224f3-267">application/json; odata=verbose</span></span>  <br/> |
   
    <span data-ttu-id="224f3-268">![添加接受标头](media/2f2e2016-3c49-4cac-b1e7-f2b8118b840c.png "添加接受标头")</span><span class="sxs-lookup"><span data-stu-id="224f3-268">![Adding an Accept header](media/2f2e2016-3c49-4cac-b1e7-f2b8118b840c.png "Adding an Accept header")</span></span>
  
4. <span data-ttu-id="224f3-269">添加 "**调用 HTTP Web 服务**" 操作。</span><span class="sxs-lookup"><span data-stu-id="224f3-269">Add the **Call HTTP Web Service** action.</span></span> <span data-ttu-id="224f3-270">将请求类型更改为使用**POST**, 并使用以下格式设置 URL:</span><span class="sxs-lookup"><span data-stu-id="224f3-270">Change the request type to use **POST**, and set the URL using the following format:</span></span>
    
    `https://<site-url>/_api/ProjectServer/Projects('<guid>')/CreateProjectSite('New web name')`
    
    <span data-ttu-id="224f3-271">![生成 CreateProjectSite 终结点 URI](media/42a90a5e-8d1b-4667-a933-785175212847.png "生成 CreateProjectSite 终结点 URI")</span><span class="sxs-lookup"><span data-stu-id="224f3-271">![Building the CreateProjectSite endpoint URI](media/42a90a5e-8d1b-4667-a933-785175212847.png "Building the CreateProjectSite endpoint URI")</span></span>
  
    <span data-ttu-id="224f3-272">将项目网站的名称作为字符串传递给**CreateProjectSite**方法。</span><span class="sxs-lookup"><span data-stu-id="224f3-272">Pass the name of the Project site to the **CreateProjectSite** method as a string.</span></span> <span data-ttu-id="224f3-273">若要将项目名称用作网站名称, 请传递一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="224f3-273">To use the project name as the site name, pass an empty string.</span></span> <span data-ttu-id="224f3-274">请务必使用唯一名称, 以便您创建的下一个项目网站能够正常工作。</span><span class="sxs-lookup"><span data-stu-id="224f3-274">Be sure to use unique names so the next project site you create will work.</span></span> 
    
5. <span data-ttu-id="224f3-275">编辑 web 服务调用的属性, 将**RequestHeader**参数绑定到您创建的词典。</span><span class="sxs-lookup"><span data-stu-id="224f3-275">Edit the properties of the web service call to bind the **RequestHeader** parameter to the dictionary you created.</span></span> 
    
    <span data-ttu-id="224f3-276">将![字典绑定到请求]将(media/61a5a0a8-405f-44eb-b5e7-80b11f7caec3.png "字典绑定到请求")</span><span class="sxs-lookup"><span data-stu-id="224f3-276">![Binding the dictionary to the request](media/61a5a0a8-405f-44eb-b5e7-80b11f7caec3.png "Binding the dictionary to the request")</span></span>
  
## <a name="see-also"></a><span data-ttu-id="224f3-277">另请参阅</span><span class="sxs-lookup"><span data-stu-id="224f3-277">See also</span></span>

- [<span data-ttu-id="224f3-278">Project 编程任务</span><span class="sxs-lookup"><span data-stu-id="224f3-278">Project programming tasks</span></span>](project-programming-tasks.md)
- [<span data-ttu-id="224f3-279">Project 2013 的客户端对象模型 (CSOM)</span><span class="sxs-lookup"><span data-stu-id="224f3-279">Client-side object model (CSOM) for Project 2013</span></span>](client-side-object-model-csom-for-project-2013.md)
- [<span data-ttu-id="224f3-280">SharePoint 2013 中的工作流</span><span class="sxs-lookup"><span data-stu-id="224f3-280">Workflows in SharePoint 2013</span></span>](https://msdn.microsoft.com/library/e0602371-ae22-44be-8a7e-9e47e9f046d6%28Office.15%29.aspx)
    

