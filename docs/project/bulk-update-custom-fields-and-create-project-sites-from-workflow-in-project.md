---
title: 批量更新自定义字段和 Project Online 中创建项目网站
manager: soliver
ms.date: 08/10/2016
ms.audience: Developer
localization_priority: Normal
ms.assetid: 815131c6-190c-4f29-83bf-c853eee72821
description: 为帮助客户充分利用 Project Online 和改进我们的服务扩展性和灵活性，我们为添加了两种方法可以在 Project Online 的应用程序和工作流中使用的客户端对象模型。
ms.openlocfilehash: 4de42471cd8c2f12a982447ccffc27ec8104fa31
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25386157"
---
# <a name="bulk-update-custom-fields-and-create-project-sites-from-a-workflow-in-project-online"></a><span data-ttu-id="f8d6c-103">批量更新自定义字段并从 Project Online 中的工作流创建项目网站</span><span class="sxs-lookup"><span data-stu-id="f8d6c-103">Bulk update custom fields and create project sites from a workflow in Project Online</span></span>

<span data-ttu-id="f8d6c-104">为帮助客户充分利用 Project Online 和改进我们的服务扩展性和灵活性，我们为添加了两种方法可以在 Project Online 的应用程序和工作流中使用的客户端对象模型。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-104">To help customers get the most out of Project Online and improve our service extensibility and flexibility, we've added two methods to the client-side object model that you can use in Project Online apps and workflows.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f8d6c-105">**UpdateCustomFields**</span><span class="sxs-lookup"><span data-stu-id="f8d6c-105">**UpdateCustomFields**</span></span> <br/> |<span data-ttu-id="f8d6c-106">批量更新项目自定义域。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-106">Bulk updates project custom fields.</span></span> <span data-ttu-id="f8d6c-107">对于仅 Project Online。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-107">For Project Online only.</span></span> <span data-ttu-id="f8d6c-108">仅在 REST API 中可用。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-108">Available only in the REST API.</span></span>  <br/> |
|<span data-ttu-id="f8d6c-109">**CreateProjectSite**</span><span class="sxs-lookup"><span data-stu-id="f8d6c-109">**CreateProjectSite**</span></span> <br/> | <span data-ttu-id="f8d6c-110">创建项目网站。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-110">Creates a Project site.</span></span> <span data-ttu-id="f8d6c-111">对于仅 Project Online。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-111">For Project Online only.</span></span> <span data-ttu-id="f8d6c-112">在 REST API、 托管客户端对象模型和 JavaScript 客户端对象模型中可用。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-112">Available in the REST API, managed client object model, and JavaScript client object model.</span></span>  <br/> |
   
<span data-ttu-id="f8d6c-113">除了提供更大的灵活性，这些方法还提供了显著的性能改进保存和发布工作流中的项目时。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-113">In addition to providing more flexibility, these methods also offer significant performance improvements when saving and publishing projects in a workflow.</span></span> <span data-ttu-id="f8d6c-114">本文介绍如何使用 REST API 中的方法，并提供用于创建工作流的批量更新自定义字段和创建项目网站的工作流的说明。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-114">This article describes how to use the methods in the REST API and provides instructions for creating a workflow that bulk updates custom fields and a workflow that creates a Project site.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f8d6c-115">若要了解更多 REST Api 调用从 SharePoint 2013 工作流，请参阅[从 POST 方法与工作流的使用 SharePoint REST 服务](https://mysharepointinsight.blogspot.com/2013/05/using-sharepoint-rest-services-from.mdl)和[调用从 SharePoint Designer 工作流的 SharePoint 2013 Rest API](https://sergeluca.wordpress.com/2013/04/09/calling-the-sharepoint-2013-rest-api-from-a-sharepoint-designer-workflow/)。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-115">To learn more about calling REST APIs from SharePoint 2013 workflows, see [Using SharePoint REST services from workflow with POST method](https://mysharepointinsight.blogspot.com/2013/05/using-sharepoint-rest-services-from.mdl) and [Calling the SharePoint 2013 Rest API from a SharePoint Designer Workflow](https://sergeluca.wordpress.com/2013/04/09/calling-the-sharepoint-2013-rest-api-from-a-sharepoint-designer-workflow/).</span></span> 
  
## <a name="bulk-update-project-custom-fields-from-a-workflow"></a><span data-ttu-id="f8d6c-116">批量更新项目从工作流的自定义字段</span><span class="sxs-lookup"><span data-stu-id="f8d6c-116">Bulk update project custom fields from a workflow</span></span>
<span data-ttu-id="f8d6c-117"><a name="BulkUpdateCustomFields"> </a></span><span class="sxs-lookup"><span data-stu-id="f8d6c-117"></span></span>

<span data-ttu-id="f8d6c-118">以前，工作流仅一次更新一个自定义字段。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-118">Previously, workflows could only update one custom field at a time.</span></span> <span data-ttu-id="f8d6c-119">一次更新项目自定义域一个会导致时用户转换项目详细信息页面之间的差的最终用户体验。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-119">Updating project custom fields one at a time can result in a poor end-user experience when users transition between Project Detail Pages.</span></span> <span data-ttu-id="f8d6c-120">每个更新所需使用**设置项目域**操作，一个单独的服务器请求和更新多个自定义字段在高延迟低带宽网络导致不常用的开销。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-120">Each update required a separate server request using the **Set Project Field** action, and updating multiple custom fields on a high-latency, low-bandwidth network resulted in a non-trivial overhead.</span></span> <span data-ttu-id="f8d6c-121">若要解决此问题，我们**UpdateCustomFields**方法添加到允许您批量更新自定义字段 REST API。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-121">To resolve this issue, we added the **UpdateCustomFields** method to the REST API that lets you bulk update custom fields.</span></span> <span data-ttu-id="f8d6c-122">若要使用**UpdateCustomFields**，您将传递包含的名称和您要更新的所有自定义字段值词典中。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-122">To use **UpdateCustomFields**, you pass in a dictionary that contains the names and values of all the custom fields you want to update.</span></span>
  
<span data-ttu-id="f8d6c-123">下面的终结点上可以找到 REST 方法：</span><span class="sxs-lookup"><span data-stu-id="f8d6c-123">The REST method can be found at the following endpoint:</span></span>
  
`https://<site-url>/_api/ProjectServer/Projects('<guid>')/Draft/UpdateCustomFields()`
  
> [!NOTE]
> <span data-ttu-id="f8d6c-124">替换`<site-url>`的 Project Web App (PWA) 网站的 url 示例中的占位符和`<guid>`与您的项目 UID 的占位符。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-124">Replace the  `<site-url>` placeholder in the examples with the URL of your Project Web App (PWA) site and the  `<guid>` placeholder with your project UID.</span></span> 
  
<span data-ttu-id="f8d6c-125">本节介绍如何创建工作流的批量更新项目的自定义域。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-125">This section describes how to create a workflow that bulk updates custom fields for a project.</span></span> <span data-ttu-id="f8d6c-126">工作流包括以下高级步骤：</span><span class="sxs-lookup"><span data-stu-id="f8d6c-126">The workflow follows these high-level steps:</span></span>
  
- <span data-ttu-id="f8d6c-127">等待要更新，以获取签入项目</span><span class="sxs-lookup"><span data-stu-id="f8d6c-127">Wait for the project that you want to update to get checked in</span></span>
    
- <span data-ttu-id="f8d6c-128">构建一个定义项目的所有自定义字段更新的数据集</span><span class="sxs-lookup"><span data-stu-id="f8d6c-128">Build a data set that defines all your custom field updates for the project</span></span>
    
- <span data-ttu-id="f8d6c-129">签出项目</span><span class="sxs-lookup"><span data-stu-id="f8d6c-129">Check out the project</span></span>
    
- <span data-ttu-id="f8d6c-130">调用**UpdateCustomFields**自定义字段更新应用到项目</span><span class="sxs-lookup"><span data-stu-id="f8d6c-130">Call **UpdateCustomFields** to apply the custom field updates to the project</span></span> 
    
- <span data-ttu-id="f8d6c-131">登录相关信息的工作流历史记录列表 （如果需要）</span><span class="sxs-lookup"><span data-stu-id="f8d6c-131">Log relevant information to the workflow history list (if required)</span></span>
    
- <span data-ttu-id="f8d6c-132">发布项目</span><span class="sxs-lookup"><span data-stu-id="f8d6c-132">Publish the project</span></span>
    
- <span data-ttu-id="f8d6c-133">签入项目</span><span class="sxs-lookup"><span data-stu-id="f8d6c-133">Check in the project</span></span>
    
<span data-ttu-id="f8d6c-134">最终的端到端工作流如下所示：</span><span class="sxs-lookup"><span data-stu-id="f8d6c-134">The final, end-to-end workflow looks like this:</span></span>
  
<span data-ttu-id="f8d6c-135">![端到端工作流](media/8c0741f9-7f76-409d-8c00-e7a8c3ddb89f.png "端到端工作流")</span><span class="sxs-lookup"><span data-stu-id="f8d6c-135">![End-to-end workflow](media/8c0741f9-7f76-409d-8c00-e7a8c3ddb89f.png "End-to-end workflow")</span></span>
  
### <a name="to-create-a-workflow-that-bulk-updates-custom-fields"></a><span data-ttu-id="f8d6c-136">创建工作流的批量更新自定义字段</span><span class="sxs-lookup"><span data-stu-id="f8d6c-136">To create a workflow that bulk updates custom fields</span></span>

1. <span data-ttu-id="f8d6c-137">可选。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-137">Optional.</span></span> <span data-ttu-id="f8d6c-138">您可以使用整个工作流变量中存储项目的完整的 URL。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-138">Store the full URL of your project in a variable that you can use throughout the workflow.</span></span>
    
    <span data-ttu-id="f8d6c-139">![存储在变量中的项目的 URL](media/a880c5c6-8e7a-44dd-87e9-7e532169d489.png "存储在变量中的项目的 URL")</span><span class="sxs-lookup"><span data-stu-id="f8d6c-139">![Store the URL of the project in a variable](media/a880c5c6-8e7a-44dd-87e9-7e532169d489.png "Store the URL of the project in a variable")</span></span>
  
2. <span data-ttu-id="f8d6c-140">将**等待项目事件**操作添加到工作流，并选择**一个项目签入时**事件。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-140">Add the **Wait for Project Event** action to the workflow and choose the **When a project is checked in** event.</span></span> 
    
    <span data-ttu-id="f8d6c-141">![等待要签入的项目](media/699aa9c7-b3c9-426e-a775-96993a13559c.png "等待要签入的项目")</span><span class="sxs-lookup"><span data-stu-id="f8d6c-141">![Wait for the project to be checked in](media/699aa9c7-b3c9-426e-a775-96993a13559c.png "Wait for the project to be checked in")</span></span>
  
3. <span data-ttu-id="f8d6c-142">创建使用**生成字典**操作**requestHeader**词典。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-142">Create a **requestHeader** dictionary using the **Build dictionary** action.</span></span> <span data-ttu-id="f8d6c-143">所有 web 服务调用该工作流中，您可以使用相同的请求标头。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-143">You'll use the same request header for all the web service calls in this workflow.</span></span> 
    
    <span data-ttu-id="f8d6c-144">![生成字典 requestHeader](media/83b0aa10-9ab7-43dd-800d-a738bb815876.png "生成字典 requestHeader")</span><span class="sxs-lookup"><span data-stu-id="f8d6c-144">![Build the requestHeader dictionary](media/83b0aa10-9ab7-43dd-800d-a738bb815876.png "Build the requestHeader dictionary")</span></span>
  
4. <span data-ttu-id="f8d6c-145">将以下两项添加到词典。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-145">Add the following two items to the dictionary.</span></span>
    
    |<span data-ttu-id="f8d6c-146">名称</span><span class="sxs-lookup"><span data-stu-id="f8d6c-146">Name</span></span>|<span data-ttu-id="f8d6c-147">类型</span><span class="sxs-lookup"><span data-stu-id="f8d6c-147">Type</span></span>|<span data-ttu-id="f8d6c-148">值</span><span class="sxs-lookup"><span data-stu-id="f8d6c-148">Value</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="f8d6c-149">Accept</span><span class="sxs-lookup"><span data-stu-id="f8d6c-149">Accept</span></span>  <br/> |<span data-ttu-id="f8d6c-150">String</span><span class="sxs-lookup"><span data-stu-id="f8d6c-150">String</span></span>  <br/> |<span data-ttu-id="f8d6c-151">应用程序/json;odata = verbose</span><span class="sxs-lookup"><span data-stu-id="f8d6c-151">application/json; odata=verbose</span></span>  <br/> |
    |<span data-ttu-id="f8d6c-152">Content-Type</span><span class="sxs-lookup"><span data-stu-id="f8d6c-152">Content-Type</span></span>  <br/> |<span data-ttu-id="f8d6c-153">String</span><span class="sxs-lookup"><span data-stu-id="f8d6c-153">String</span></span>  <br/> |<span data-ttu-id="f8d6c-154">应用程序/json;odata = verbose</span><span class="sxs-lookup"><span data-stu-id="f8d6c-154">application/json; odata=verbose</span></span>  <br/> |
   
    <span data-ttu-id="f8d6c-155">![添加 Accept 标头](media/2f2e2016-3c49-4cac-b1e7-f2b8118b840c.png "添加 Accept 标头")</span><span class="sxs-lookup"><span data-stu-id="f8d6c-155">![Adding an Accept header](media/2f2e2016-3c49-4cac-b1e7-f2b8118b840c.png "Adding an Accept header")</span></span>
  
5. <span data-ttu-id="f8d6c-156">创建使用**生成字典**操作**requestBody**词典。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-156">Create a **requestBody** dictionary using the **Build dictionary** action.</span></span> <span data-ttu-id="f8d6c-157">该词典存储要应用的所有字段更新。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-157">This dictionary stores all the field updates that you want to apply.</span></span> 
    
    <span data-ttu-id="f8d6c-158">每个自定义字段更新需要四行： 该字段的 （1） 元数据类型、 （2） 密钥、 （3） 值和 （4） 值类型。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-158">Each custom field update requires four rows: the field's (1) metadata type, (2) key, (3) value, and (4) value type.</span></span>
    
    - <span data-ttu-id="f8d6c-159">**__metadata/类型**该字段的元数据类型。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-159">**__metadata/type** The field's metadata type.</span></span> <span data-ttu-id="f8d6c-160">此记录始终是相同，并使用以下值：</span><span class="sxs-lookup"><span data-stu-id="f8d6c-160">This record is always the same and uses the following values:</span></span> 
    
       - <span data-ttu-id="f8d6c-161">名称： customFieldDictionary （i）/__metadata/类型 （其中**i**是中每个自定义字段的词典，从 0 开始进行索引）</span><span class="sxs-lookup"><span data-stu-id="f8d6c-161">Name: customFieldDictionary(i)/__metadata/type (where **i** is the index of each custom field in the dictionary, starting with 0)</span></span> 
            
       - <span data-ttu-id="f8d6c-162">类型：字符串</span><span class="sxs-lookup"><span data-stu-id="f8d6c-162">Type: String</span></span>
            
       - <span data-ttu-id="f8d6c-163">值： sp。KeyValue</span><span class="sxs-lookup"><span data-stu-id="f8d6c-163">Value: SP.KeyValue</span></span>
    
       <span data-ttu-id="f8d6c-164">![定义自定义字段更新](media/a4423493-6603-42ee-ae50-1ef74c5c59bd.png "定义自定义字段更新")</span><span class="sxs-lookup"><span data-stu-id="f8d6c-164">![Defining a custom field update](media/a4423493-6603-42ee-ae50-1ef74c5c59bd.png "Defining a custom field update")</span></span>
  
    - <span data-ttu-id="f8d6c-165">**键**格式中的自定义字段的内部名称： *Custom_ce23fbf43fa0e411941000155d3c8201*</span><span class="sxs-lookup"><span data-stu-id="f8d6c-165">**Key** The internal name of the custom field, in the format: *Custom_ce23fbf43fa0e411941000155d3c8201*</span></span> 
    
       <span data-ttu-id="f8d6c-166">您可以通过导航到它的**InternalName**终结点中找到的自定义字段的内部名称：`https://<site-url>/_api/ProjectServer/CustomFields('<guid>')/InternalName`</span><span class="sxs-lookup"><span data-stu-id="f8d6c-166">You can find the internal name of a custom field by navigating to it's **InternalName** endpoint: `https://<site-url>/_api/ProjectServer/CustomFields('<guid>')/InternalName`</span></span>
    
       <span data-ttu-id="f8d6c-167">如果手动创建自定义域，值将不同站点到站点。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-167">If you created your custom fields manually, the values will differ from site to site.</span></span> <span data-ttu-id="f8d6c-168">如果您打算在多个网站重用工作流，请确保自定义字段 Id 正确。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-168">If you plan to reuse the workflow across multiple sites, make sure the custom field IDs are correct.</span></span>
    
    - <span data-ttu-id="f8d6c-169">**值**要分配自定义域的值。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-169">**Value** The value to assign to the custom field.</span></span> <span data-ttu-id="f8d6c-170">链接到查阅表格的自定义域，您需要使用而不是实际的查阅表格值的查找表条目的内部名称。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-170">For custom fields that are linked to lookup tables, you need to use the internal names of the lookup table entries instead of the actual lookup table values.</span></span> 
    
       <span data-ttu-id="f8d6c-171">您可以找到以下端点处的查阅表格项的内部名称：`https://<site-url>/_api/ProjectServer/CustomFields('<guid>')/LookupEntries('<guid>')/InternalName`</span><span class="sxs-lookup"><span data-stu-id="f8d6c-171">You can find the internal name of the lookup table entry at the following endpoint: `https://<site-url>/_api/ProjectServer/CustomFields('<guid>')/LookupEntries('<guid>')/InternalName`</span></span>
    
       <span data-ttu-id="f8d6c-172">如果您具有查找表自定义字段设置为接受多个值，请使用`;#`来连接值 （如下面的示例词典中所示）。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-172">If you have a lookup table custom field set up to accept multiple values, use  `;#` to concatenate values (as shown in the example dictionary below).</span></span> 
    
    - <span data-ttu-id="f8d6c-173">**ValueType**要更新的自定义字段类型。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-173">**ValueType** The type of the custom field you are updating.</span></span> 
    
       - <span data-ttu-id="f8d6c-174">对于文本、 工期、 标志和 LookupTable 字段，使用 Edm.String</span><span class="sxs-lookup"><span data-stu-id="f8d6c-174">For Text, Duration, Flag, and LookupTable fields, use Edm.String</span></span>
    
       - <span data-ttu-id="f8d6c-175">对于数字字段，使用 Edm.Int32、 Edm.Double 或任何其他 OData 接受数字类型</span><span class="sxs-lookup"><span data-stu-id="f8d6c-175">For Number fields, use Edm.Int32, Edm.Double, or any other OData-accepted number type</span></span>
    
       - <span data-ttu-id="f8d6c-176">对于日期字段中，使用 Edm.DateTime</span><span class="sxs-lookup"><span data-stu-id="f8d6c-176">For Date fields, use Edm.DateTime</span></span>
    
       <span data-ttu-id="f8d6c-177">下面的示例词典定义三个自定义域的更新。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-177">The example dictionary below defines updates for three custom fields.</span></span> <span data-ttu-id="f8d6c-178">第一个是多值查找表自定义字段、 第二个是数字字段，和第三个是日期字段。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-178">The first is for a multiple value lookup table custom field, the second is for a number field, and the third is for a date field.</span></span> <span data-ttu-id="f8d6c-179">注意如何**customFieldDictionary**索引增量。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-179">Note how the **customFieldDictionary** index increments.</span></span> 
    
       > [!NOTE]
       > <span data-ttu-id="f8d6c-180">这些值是仅用于图。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-180">These values are for illustration purposes only.</span></span> <span data-ttu-id="f8d6c-181">您可以使用的键 / 值对取决于您的 PWA 数据。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-181">The key-value pairs you'll use depend on your PWA data.</span></span> 
  
       |<span data-ttu-id="f8d6c-182">名称</span><span class="sxs-lookup"><span data-stu-id="f8d6c-182">Name</span></span>|<span data-ttu-id="f8d6c-183">类型</span><span class="sxs-lookup"><span data-stu-id="f8d6c-183">Type</span></span>|<span data-ttu-id="f8d6c-184">值</span><span class="sxs-lookup"><span data-stu-id="f8d6c-184">Value</span></span>|
       |:-----|:-----|:-----|
       |<span data-ttu-id="f8d6c-185">customFieldDictionary (0) / __metadata/类型</span><span class="sxs-lookup"><span data-stu-id="f8d6c-185">customFieldDictionary(0)/__metadata/type</span></span>  <br/> |<span data-ttu-id="f8d6c-186">String</span><span class="sxs-lookup"><span data-stu-id="f8d6c-186">String</span></span>  <br/> |<span data-ttu-id="f8d6c-187">SP。KeyValue</span><span class="sxs-lookup"><span data-stu-id="f8d6c-187">SP.KeyValue</span></span>  <br/> |
       |<span data-ttu-id="f8d6c-188">customFieldDictionary (0) / 键</span><span class="sxs-lookup"><span data-stu-id="f8d6c-188">customFieldDictionary(0)/Key</span></span>  <br/> |<span data-ttu-id="f8d6c-189">String</span><span class="sxs-lookup"><span data-stu-id="f8d6c-189">String</span></span>  <br/> |<span data-ttu-id="f8d6c-190">自定义\_ce23fbf43fa0e411941000155d3c8201</span><span class="sxs-lookup"><span data-stu-id="f8d6c-190">Custom\_ce23fbf43fa0e411941000155d3c8201</span></span>  <br/> |
       |<span data-ttu-id="f8d6c-191">customFieldDictionary (0) / 值</span><span class="sxs-lookup"><span data-stu-id="f8d6c-191">customFieldDictionary(0)/Value</span></span>  <br/> |<span data-ttu-id="f8d6c-192">String</span><span class="sxs-lookup"><span data-stu-id="f8d6c-192">String</span></span>  <br/> |<span data-ttu-id="f8d6c-193">条目\_b9a2fd69279de411940f00155d3c8201; #Entry\_baa2fd69279de411940f00155d3c8201</span><span class="sxs-lookup"><span data-stu-id="f8d6c-193">Entry\_b9a2fd69279de411940f00155d3c8201;#Entry\_baa2fd69279de411940f00155d3c8201</span></span>  <br/> |
       |<span data-ttu-id="f8d6c-194">customFieldDictionary (0) / ValueType</span><span class="sxs-lookup"><span data-stu-id="f8d6c-194">customFieldDictionary(0)/ValueType</span></span>  <br/> |<span data-ttu-id="f8d6c-195">String</span><span class="sxs-lookup"><span data-stu-id="f8d6c-195">String</span></span>  <br/> |<span data-ttu-id="f8d6c-196">Edm.String</span><span class="sxs-lookup"><span data-stu-id="f8d6c-196">Edm.String</span></span>  <br/> |
       |<span data-ttu-id="f8d6c-197">customFieldDictionary （1）/__metadata/类型</span><span class="sxs-lookup"><span data-stu-id="f8d6c-197">customFieldDictionary(1)/__metadata/type</span></span>  <br/> |<span data-ttu-id="f8d6c-198">String</span><span class="sxs-lookup"><span data-stu-id="f8d6c-198">String</span></span>  <br/> |<span data-ttu-id="f8d6c-199">SP。KeyValue</span><span class="sxs-lookup"><span data-stu-id="f8d6c-199">SP.KeyValue</span></span>  <br/> |
       |<span data-ttu-id="f8d6c-200">customFieldDictionary （1）/键</span><span class="sxs-lookup"><span data-stu-id="f8d6c-200">customFieldDictionary(1)/Key</span></span>  <br/> |<span data-ttu-id="f8d6c-201">String</span><span class="sxs-lookup"><span data-stu-id="f8d6c-201">String</span></span>  <br/> |<span data-ttu-id="f8d6c-202">Custom_c7f114c97098e411940f00155d3c8201</span><span class="sxs-lookup"><span data-stu-id="f8d6c-202">Custom_c7f114c97098e411940f00155d3c8201</span></span>  <br/> |
       |<span data-ttu-id="f8d6c-203">customFieldDictionary （1）/值</span><span class="sxs-lookup"><span data-stu-id="f8d6c-203">customFieldDictionary(1)/Value</span></span>  <br/> |<span data-ttu-id="f8d6c-204">String</span><span class="sxs-lookup"><span data-stu-id="f8d6c-204">String</span></span>  <br/> |<span data-ttu-id="f8d6c-205">90.5</span><span class="sxs-lookup"><span data-stu-id="f8d6c-205">90.5</span></span>  <br/> |
       |<span data-ttu-id="f8d6c-206">customFieldDictionary （1) / ValueType</span><span class="sxs-lookup"><span data-stu-id="f8d6c-206">customFieldDictionary(1)/ValueType</span></span>  <br/> |<span data-ttu-id="f8d6c-207">String</span><span class="sxs-lookup"><span data-stu-id="f8d6c-207">String</span></span>  <br/> |<span data-ttu-id="f8d6c-208">Edm.Double</span><span class="sxs-lookup"><span data-stu-id="f8d6c-208">Edm.Double</span></span>  <br/> |
       |<span data-ttu-id="f8d6c-209">customFieldDictionary （2）/__metadata/类型</span><span class="sxs-lookup"><span data-stu-id="f8d6c-209">customFieldDictionary(2)/__metadata/type</span></span>  <br/> |<span data-ttu-id="f8d6c-210">String</span><span class="sxs-lookup"><span data-stu-id="f8d6c-210">String</span></span>  <br/> |<span data-ttu-id="f8d6c-211">SP。KeyValue</span><span class="sxs-lookup"><span data-stu-id="f8d6c-211">SP.KeyValue</span></span>  <br/> |
       |<span data-ttu-id="f8d6c-212">customFieldDictionary （2）/键</span><span class="sxs-lookup"><span data-stu-id="f8d6c-212">customFieldDictionary(2)/Key</span></span>  <br/> |<span data-ttu-id="f8d6c-213">String</span><span class="sxs-lookup"><span data-stu-id="f8d6c-213">String</span></span>  <br/> |<span data-ttu-id="f8d6c-214">Custom_c6fb67e0b9a1e411941000155d3c8201</span><span class="sxs-lookup"><span data-stu-id="f8d6c-214">Custom_c6fb67e0b9a1e411941000155d3c8201</span></span>  <br/> |
       |<span data-ttu-id="f8d6c-215">customFieldDictionary （2）/值</span><span class="sxs-lookup"><span data-stu-id="f8d6c-215">customFieldDictionary(2)/Value</span></span>  <br/> |<span data-ttu-id="f8d6c-216">String</span><span class="sxs-lookup"><span data-stu-id="f8d6c-216">String</span></span>  <br/> |<span data-ttu-id="f8d6c-217">2015-04-01T00:00:00.0000000</span><span class="sxs-lookup"><span data-stu-id="f8d6c-217">2015-04-01T00:00:00.0000000</span></span>  <br/> |
       |<span data-ttu-id="f8d6c-218">customFieldDictionary （2) / ValueType</span><span class="sxs-lookup"><span data-stu-id="f8d6c-218">customFieldDictionary(2)/ValueType</span></span>  <br/> |<span data-ttu-id="f8d6c-219">String</span><span class="sxs-lookup"><span data-stu-id="f8d6c-219">String</span></span>  <br/> |<span data-ttu-id="f8d6c-220">Edm.DateTime</span><span class="sxs-lookup"><span data-stu-id="f8d6c-220">Edm.DateTime</span></span>  <br/> |
   
       <span data-ttu-id="f8d6c-221">![定义自定义字段更新的字典](media/41a1f18f-a6b2-40ff-904b-437baf962621.png "定义自定义字段更新的字典")</span><span class="sxs-lookup"><span data-stu-id="f8d6c-221">![Dictionary that defines custom field updates](media/41a1f18f-a6b2-40ff-904b-437baf962621.png "Dictionary that defines custom field updates")</span></span>
  
6. <span data-ttu-id="f8d6c-222">添加**调用 HTTP Web 服务**操作签出的项目。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-222">Add a **Call HTTP Web Service** action to check the project out.</span></span> 
    
    <span data-ttu-id="f8d6c-223">![调用 Checkout 方法](media/8ce56014-0317-419b-afa7-229d05c86885.png "调用 Checkout 方法")</span><span class="sxs-lookup"><span data-stu-id="f8d6c-223">![Call the Checkout method](media/8ce56014-0317-419b-afa7-229d05c86885.png "Call the Checkout method")</span></span>
  
7. <span data-ttu-id="f8d6c-224">编辑 web 服务调用指定请求标头的属性。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-224">Edit the properties of the web service call to specify the request header.</span></span> <span data-ttu-id="f8d6c-225">要打开**属性**对话框，请右键单击操作，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-225">To open the **Properties** dialog box, right-click the action and choose **Properties**.</span></span>
    
    <span data-ttu-id="f8d6c-226">![指定在 web 服务请求标头调用属性](media/d81e92b1-43df-42ad-9cd0-a693f93b164e.png "指定在 web 服务请求标头调用属性")</span><span class="sxs-lookup"><span data-stu-id="f8d6c-226">![Specify the request header in web service call properties](media/d81e92b1-43df-42ad-9cd0-a693f93b164e.png "Specify the request header in web service call properties")</span></span>
  
8. <span data-ttu-id="f8d6c-227">添加**调用 HTTP Web 服务**操作调用**UpdateCustomFields**方法。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-227">Add a **Call HTTP Web Service** action to call the **UpdateCustomFields** method.</span></span> 
    
    <span data-ttu-id="f8d6c-228">![创建一个调用 HTTP Web 服务操作](media/9a73a201-c035-41b4-8798-506ac48b90f8.png "创建一个调用 HTTP Web 服务操作")</span><span class="sxs-lookup"><span data-stu-id="f8d6c-228">![Create a Call HTTP Web Service action](media/9a73a201-c035-41b4-8798-506ac48b90f8.png "Create a Call HTTP Web Service action")</span></span>
  
    <span data-ttu-id="f8d6c-229">注意`/Draft/`段中的 web 服务 URL。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-229">Note the  `/Draft/` segment in the web service URL.</span></span> <span data-ttu-id="f8d6c-230">完整的 URL 应如下所示：`https://<site-url>/_api/ProjectServer/Projects('<guid>')/Draft/UpdateCustomFields()`</span><span class="sxs-lookup"><span data-stu-id="f8d6c-230">The full URL should look like this: `https://<site-url>/_api/ProjectServer/Projects('<guid>')/Draft/UpdateCustomFields()`</span></span>
    
    <span data-ttu-id="f8d6c-231">![调用 UpdateCustomFields 方法](media/03b323f1-8e99-4b18-be18-be505d7cec7e.png "调用 UpdateCustomFields 方法")</span><span class="sxs-lookup"><span data-stu-id="f8d6c-231">![Call the UpdateCustomFields method](media/03b323f1-8e99-4b18-be18-be505d7cec7e.png "Call the UpdateCustomFields method")</span></span>
  
9. <span data-ttu-id="f8d6c-232">编辑 web 服务调用将**RequestHeader**和**RequestContent**参数绑定词典您创建的属性。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-232">Edit the properties of the web service call to bind the **RequestHeader** and **RequestContent** parameters to the dictionaries you created.</span></span> <span data-ttu-id="f8d6c-233">您还可以创建的新变量来存储**ResponseContent**。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-233">You can also create a new variable to store the **ResponseContent**.</span></span>
    
    <span data-ttu-id="f8d6c-234">![绑定到的请求标头和内容的词典](media/f96bec92-138e-4eab-b1e7-1ab83d0428a5.png "绑定到的请求标头和内容的词典")</span><span class="sxs-lookup"><span data-stu-id="f8d6c-234">![Bind the dictionaries to the request header and content](media/f96bec92-138e-4eab-b1e7-1ab83d0428a5.png "Bind the dictionaries to the request header and content")</span></span>
  
10. <span data-ttu-id="f8d6c-235">可选。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-235">Optional.</span></span> <span data-ttu-id="f8d6c-236">读取响应字典来检查队列作业的状态和日志中的工作流历史记录列表的信息。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-236">Read from the response dictionary to check the state of the queue job and log the information in the workflow history list.</span></span>
    
    <span data-ttu-id="f8d6c-237">![设置日志记录](media/7d2f4936-61d7-4906-83e8-7478a5935af5.png "设置日志记录")</span><span class="sxs-lookup"><span data-stu-id="f8d6c-237">![Setting up logging](media/7d2f4936-61d7-4906-83e8-7478a5935af5.png "Setting up logging")</span></span>
  
11. <span data-ttu-id="f8d6c-238">添加到**发布**的终结点的 web 服务调用，以发布项目。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-238">Add a web service call to the **Publish** endpoint to publish the project.</span></span> <span data-ttu-id="f8d6c-239">始终使用相同的请求标头。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-239">Always use the same request header.</span></span> 
    
    <span data-ttu-id="f8d6c-240">![调用发布方法](media/3b661091-ffae-4d7e-a0bb-5b96a6292731.png "调用发布方法")</span><span class="sxs-lookup"><span data-stu-id="f8d6c-240">![Call the Publish method](media/3b661091-ffae-4d7e-a0bb-5b96a6292731.png "Call the Publish method")</span></span>
  
    <span data-ttu-id="f8d6c-241">![发布 web 服务的属性呼叫](media/6a80a5d3-7e29-4398-993c-f78b3faca8b1.png "发布 web 服务的属性呼叫")</span><span class="sxs-lookup"><span data-stu-id="f8d6c-241">![Properties for the Publish web service call](media/6a80a5d3-7e29-4398-993c-f78b3faca8b1.png "Properties for the Publish web service call")</span></span>
  
12. <span data-ttu-id="f8d6c-242">添加对**Checkin**终结点的最后一个 web 服务调用，签入项目。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-242">Add a final web service call to the **Checkin** endpoint to check the project in.</span></span> 
    
    <span data-ttu-id="f8d6c-243">![调用 Checkin 方法](media/430510cb-0774-4911-af7f-b565b83eba0e.png "调用 Checkin 方法")</span><span class="sxs-lookup"><span data-stu-id="f8d6c-243">![Call the Checkin method](media/430510cb-0774-4911-af7f-b565b83eba0e.png "Call the Checkin method")</span></span>
  
    <span data-ttu-id="f8d6c-244">![签入 web 服务的属性呼叫](media/485f48d6-bbb8-4568-9dc3-aae3218f6bd1.png "签入 web 服务的属性呼叫")</span><span class="sxs-lookup"><span data-stu-id="f8d6c-244">![Properties for the Checkin web service call](media/485f48d6-bbb8-4568-9dc3-aae3218f6bd1.png "Properties for the Checkin web service call")</span></span>

<span data-ttu-id="f8d6c-245"><a name="CreateProjectSite"> </a></span><span class="sxs-lookup"><span data-stu-id="f8d6c-245"></span></span>

## <a name="create-a-project-site-from-a-workflow"></a><span data-ttu-id="f8d6c-246">从工作流创建项目网站</span><span class="sxs-lookup"><span data-stu-id="f8d6c-246">Create a Project site from a workflow</span></span>

<span data-ttu-id="f8d6c-247">每个项目都可以具有自己专用的 SharePoint 网站，其中工作组成员可以协作、 共享文档、 提出问题，等等。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-247">Every project can have its own dedicated SharePoint sites where team members can collaborate, share documents, raise issues, and so on.</span></span> <span data-ttu-id="f8d6c-248">以前，无法仅创建网站上自动首先发布或手动按项目经理在 Project Professional 或 PWA 中的管理员设置，也无法被禁用。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-248">Previously, sites could only be created automatically on first publish or manually by the project manager in Project Professional or by the administrator in PWA settings, or they could be disabled.</span></span>
  
<span data-ttu-id="f8d6c-249">我们已添加**CreateProjectSite**方法，以便您可以选择何时创建项目网站。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-249">We've added the **CreateProjectSite** method so you can choose when to create project sites.</span></span> <span data-ttu-id="f8d6c-250">这是对要项目建议达到预定义工作流中的特定容器时自动创建其网站，而不是第一个发布的组织特别有用。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-250">This is particularly useful for organizations who want to create their sites automatically when a project proposal reaches a specific stage in a pre-defined workflow, rather than on first publish.</span></span> <span data-ttu-id="f8d6c-251">推迟项目网站创建会显著提高了创建项目的性能。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-251">Postponing project site creation significantly improves the performance of creating a project.</span></span> 
  
<span data-ttu-id="f8d6c-252">**必备：** 您可以使用**CreateProjectSite**之前，必须**设置 PWA**中创建的项目网站设置**允许用户选择**设置 > \* \* 连接的 SharePoint 网站 \* \* >**设置**。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-252">**Prerequisite:** Before you can use **CreateProjectSite**, the **Allow users to choose** setting must be set for project site creation in **PWA Settings** > \*\* Connected SharePoint Sites \*\* > **Settings**.</span></span>
  
<span data-ttu-id="f8d6c-253">![设置 PWA 设置中的"允许用户选择"](media/6c6c8175-eb10-431d-8056-cea55718fdb4.png "设置允许用户选择在 PWA 的设置")</span><span class="sxs-lookup"><span data-stu-id="f8d6c-253">![Setting "Allow users to choose" in PWA settings](media/6c6c8175-eb10-431d-8056-cea55718fdb4.png "Setting Allow users to choose in PWA settings")</span></span>
  
### <a name="to-create-a-workflow-that-creates-a-project-site"></a><span data-ttu-id="f8d6c-254">创建工作流创建项目网站</span><span class="sxs-lookup"><span data-stu-id="f8d6c-254">To create a workflow that creates a Project site</span></span>

1. <span data-ttu-id="f8d6c-255">创建或编辑现有工作流和选择想要创建项目网站的步骤。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-255">Create or edit an existing workflow and select the step where you want to create your Project sites.</span></span>
    
2. <span data-ttu-id="f8d6c-256">创建使用**生成字典**操作**requestHeader**词典。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-256">Create a **requestHeader** dictionary using the **Build dictionary** action.</span></span> 
    
    <span data-ttu-id="f8d6c-257">![生成字典 requestHeader](media/83b0aa10-9ab7-43dd-800d-a738bb815876.png "生成字典 requestHeader")</span><span class="sxs-lookup"><span data-stu-id="f8d6c-257">![Build the requestHeader dictionary](media/83b0aa10-9ab7-43dd-800d-a738bb815876.png "Build the requestHeader dictionary")</span></span>
  
3. <span data-ttu-id="f8d6c-258">将以下两项添加到词典。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-258">Add the following two items to the dictionary.</span></span>
    
    |<span data-ttu-id="f8d6c-259">名称</span><span class="sxs-lookup"><span data-stu-id="f8d6c-259">Name</span></span>|<span data-ttu-id="f8d6c-260">类型</span><span class="sxs-lookup"><span data-stu-id="f8d6c-260">Type</span></span>|<span data-ttu-id="f8d6c-261">值</span><span class="sxs-lookup"><span data-stu-id="f8d6c-261">Value</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="f8d6c-262">Accept</span><span class="sxs-lookup"><span data-stu-id="f8d6c-262">Accept</span></span>  <br/> |<span data-ttu-id="f8d6c-263">String</span><span class="sxs-lookup"><span data-stu-id="f8d6c-263">String</span></span>  <br/> |<span data-ttu-id="f8d6c-264">应用程序/json;odata = verbose</span><span class="sxs-lookup"><span data-stu-id="f8d6c-264">application/json; odata=verbose</span></span>  <br/> |
    |<span data-ttu-id="f8d6c-265">Content-Type</span><span class="sxs-lookup"><span data-stu-id="f8d6c-265">Content-Type</span></span>  <br/> |<span data-ttu-id="f8d6c-266">String</span><span class="sxs-lookup"><span data-stu-id="f8d6c-266">String</span></span>  <br/> |<span data-ttu-id="f8d6c-267">应用程序/json;odata = verbose</span><span class="sxs-lookup"><span data-stu-id="f8d6c-267">application/json; odata=verbose</span></span>  <br/> |
   
    <span data-ttu-id="f8d6c-268">![添加 Accept 标头](media/2f2e2016-3c49-4cac-b1e7-f2b8118b840c.png "添加 Accept 标头")</span><span class="sxs-lookup"><span data-stu-id="f8d6c-268">![Adding an Accept header](media/2f2e2016-3c49-4cac-b1e7-f2b8118b840c.png "Adding an Accept header")</span></span>
  
4. <span data-ttu-id="f8d6c-269">添加**调用 HTTP Web 服务**操作。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-269">Add the **Call HTTP Web Service** action.</span></span> <span data-ttu-id="f8d6c-270">更改要使用**POST**请求类型，并设置使用以下格式的 URL:</span><span class="sxs-lookup"><span data-stu-id="f8d6c-270">Change the request type to use **POST**, and set the URL using the following format:</span></span>
    
    `https://<site-url>/_api/ProjectServer/Projects('<guid>')/CreateProjectSite('New web name')`
    
    <span data-ttu-id="f8d6c-271">![构建 CreateProjectSite 终结点 URI](media/42a90a5e-8d1b-4667-a933-785175212847.png "构建 CreateProjectSite 终结点 URI")</span><span class="sxs-lookup"><span data-stu-id="f8d6c-271">![Building the CreateProjectSite endpoint URI](media/42a90a5e-8d1b-4667-a933-785175212847.png "Building the CreateProjectSite endpoint URI")</span></span>
  
    <span data-ttu-id="f8d6c-272">作为字符串传递给**CreateProjectSite**方法的项目网站的名称。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-272">Pass the name of the Project site to the **CreateProjectSite** method as a string.</span></span> <span data-ttu-id="f8d6c-273">若要作为网站名称中使用的项目名称，传递一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-273">To use the project name as the site name, pass an empty string.</span></span> <span data-ttu-id="f8d6c-274">请务必使用唯一的名称，因此您创建的下一个项目网站将起作用。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-274">Be sure to use unique names so the next project site you create will work.</span></span> 
    
5. <span data-ttu-id="f8d6c-275">编辑将**RequestHeader**参数绑定到字典 web 服务呼叫您创建的属性。</span><span class="sxs-lookup"><span data-stu-id="f8d6c-275">Edit the properties of the web service call to bind the **RequestHeader** parameter to the dictionary you created.</span></span> 
    
    <span data-ttu-id="f8d6c-276">![绑定到请求的词典](media/61a5a0a8-405f-44eb-b5e7-80b11f7caec3.png "绑定到请求的词典")</span><span class="sxs-lookup"><span data-stu-id="f8d6c-276">![Binding the dictionary to the request](media/61a5a0a8-405f-44eb-b5e7-80b11f7caec3.png "Binding the dictionary to the request")</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f8d6c-277">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f8d6c-277">See also</span></span>

- [<span data-ttu-id="f8d6c-278">Project 编程任务</span><span class="sxs-lookup"><span data-stu-id="f8d6c-278">Project programming tasks</span></span>](project-programming-tasks.md)
- [<span data-ttu-id="f8d6c-279">Project 2013 的客户端对象模型 (CSOM)</span><span class="sxs-lookup"><span data-stu-id="f8d6c-279">Client-side object model (CSOM) for Project 2013</span></span>](client-side-object-model-csom-for-project-2013.md)
- [<span data-ttu-id="f8d6c-280">SharePoint 2013 中的工作流</span><span class="sxs-lookup"><span data-stu-id="f8d6c-280">Workflows in SharePoint 2013</span></span>](https://msdn.microsoft.com/library/e0602371-ae22-44be-8a7e-9e47e9f046d6%28Office.15%29.aspx)
    

