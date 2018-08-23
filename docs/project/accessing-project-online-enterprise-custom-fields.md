---
title: 访问 Project Online 企业自定义字段
manager: soliver
ms.date: 11/08/2016
ms.audience: Developer
localization_priority: Normal
ms.assetid: 25509631-fa14-49d8-b594-cfacf5355c38
description: Project Online 是 Office 365 服务，公司可以扩展以满足业务需求。 一个扩展区域是企业自定义域 (ECFs)。 ECFs 不可以添加到项目、 资源和任务的类型的值字段。 下表列出了将与项目、 资源和任务相关联的 ECFs，并为该 ECF 实例提供值的示例：
ms.openlocfilehash: d560b258f2c9873844009cb6bc6e698abec029a6
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584602"
---
# <a name="accessing-project-online-enterprise-custom-fields"></a><span data-ttu-id="8ccf1-106">访问 Project Online 企业自定义字段</span><span class="sxs-lookup"><span data-stu-id="8ccf1-106">Accessing Project Online enterprise custom fields</span></span>

<span data-ttu-id="8ccf1-107">Project Online 是 Office 365 服务，公司可以扩展以满足业务需求。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-107">Project Online is an Office 365 service that companies can extend to meet business needs.</span></span> <span data-ttu-id="8ccf1-108">一个扩展区域是企业自定义域 (ECFs)。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-108">One extension area is Enterprise Custom Fields (ECFs).</span></span> <span data-ttu-id="8ccf1-109">ECFs 不可以添加到项目、 资源和任务的类型的值字段。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-109">ECFs are typed value fields that can be added to projects, resources, and tasks.</span></span> <span data-ttu-id="8ccf1-110">下表列出了将与项目、 资源和任务相关联的 ECFs，并为该 ECF 实例提供值的示例：</span><span class="sxs-lookup"><span data-stu-id="8ccf1-110">The following table lists ECFs that associate with projects, resources, and tasks, and provides an example of a value for an instance of that ECF:</span></span>
  
|<span data-ttu-id="8ccf1-111">ECF 名称</span><span class="sxs-lookup"><span data-stu-id="8ccf1-111">ECF Name</span></span>|<span data-ttu-id="8ccf1-112">ECF 类型</span><span class="sxs-lookup"><span data-stu-id="8ccf1-112">ECF Type</span></span>|<span data-ttu-id="8ccf1-113">Association</span><span class="sxs-lookup"><span data-stu-id="8ccf1-113">Association</span></span>|<span data-ttu-id="8ccf1-114">示例值</span><span class="sxs-lookup"><span data-stu-id="8ccf1-114">Example Value</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8ccf1-115">字距调整</span><span class="sxs-lookup"><span data-stu-id="8ccf1-115">Justification</span></span>  <br/> |<span data-ttu-id="8ccf1-116">TEXT</span><span class="sxs-lookup"><span data-stu-id="8ccf1-116">TEXT</span></span>  <br/> |<span data-ttu-id="8ccf1-117">Project</span><span class="sxs-lookup"><span data-stu-id="8ccf1-117">Project</span></span>  <br/> |<span data-ttu-id="8ccf1-118">最终用户可以记录重要统计信息和运行状况数据，包括运行状况评估和个性化的操作的结果达到更好的运行状况的计划。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-118">An end user can record vital statistics and health data, with results that include a health evaluation and an individualized action plan towards better health.</span></span>  <br/> |
|<span data-ttu-id="8ccf1-119">风险评估</span><span class="sxs-lookup"><span data-stu-id="8ccf1-119">Risk Rating</span></span>  <br/> |<span data-ttu-id="8ccf1-120">TEXT</span><span class="sxs-lookup"><span data-stu-id="8ccf1-120">TEXT</span></span>  <br/> |<span data-ttu-id="8ccf1-121">Project</span><span class="sxs-lookup"><span data-stu-id="8ccf1-121">Project</span></span>  <br/> |<span data-ttu-id="8ccf1-122">Low</span><span class="sxs-lookup"><span data-stu-id="8ccf1-122">Low</span></span>  <br/> |
|<span data-ttu-id="8ccf1-123">投资回报</span><span class="sxs-lookup"><span data-stu-id="8ccf1-123">ROI</span></span>  <br/> |<span data-ttu-id="8ccf1-124">号码</span><span class="sxs-lookup"><span data-stu-id="8ccf1-124">NUMBER</span></span>  <br/> |<span data-ttu-id="8ccf1-125">Project</span><span class="sxs-lookup"><span data-stu-id="8ccf1-125">Project</span></span>  <br/> |<span data-ttu-id="8ccf1-126">2.10</span><span class="sxs-lookup"><span data-stu-id="8ccf1-126">2.10</span></span>  <br/> |
|<span data-ttu-id="8ccf1-127">总成本</span><span class="sxs-lookup"><span data-stu-id="8ccf1-127">Total Cost</span></span>  <br/> |<span data-ttu-id="8ccf1-128">成本</span><span class="sxs-lookup"><span data-stu-id="8ccf1-128">COST</span></span>  <br/> |<span data-ttu-id="8ccf1-129">Project</span><span class="sxs-lookup"><span data-stu-id="8ccf1-129">Project</span></span>  <br/> |<span data-ttu-id="8ccf1-130">$ 1,031,514</span><span class="sxs-lookup"><span data-stu-id="8ccf1-130">$1,031,514</span></span>  <br/> |
|<span data-ttu-id="8ccf1-131">启动团队</span><span class="sxs-lookup"><span data-stu-id="8ccf1-131">Launch Team</span></span>  <br/> |<span data-ttu-id="8ccf1-132">TEXT</span><span class="sxs-lookup"><span data-stu-id="8ccf1-132">TEXT</span></span>  <br/> |<span data-ttu-id="8ccf1-133">Resources</span><span class="sxs-lookup"><span data-stu-id="8ccf1-133">Resources</span></span>  <br/> |<span data-ttu-id="8ccf1-134">是</span><span class="sxs-lookup"><span data-stu-id="8ccf1-134">Yes</span></span>  <br/> |
|<span data-ttu-id="8ccf1-135">位置角色</span><span class="sxs-lookup"><span data-stu-id="8ccf1-135">Position Role</span></span>  <br/> |<span data-ttu-id="8ccf1-136">TEXT</span><span class="sxs-lookup"><span data-stu-id="8ccf1-136">TEXT</span></span>  <br/> |<span data-ttu-id="8ccf1-137">Resources</span><span class="sxs-lookup"><span data-stu-id="8ccf1-137">Resources</span></span>  <br/> |<span data-ttu-id="8ccf1-138">测试人员</span><span class="sxs-lookup"><span data-stu-id="8ccf1-138">Tester</span></span>  <br/> |
|<span data-ttu-id="8ccf1-139">标记状态</span><span class="sxs-lookup"><span data-stu-id="8ccf1-139">Flag Status</span></span>  <br/> |<span data-ttu-id="8ccf1-140">标志</span><span class="sxs-lookup"><span data-stu-id="8ccf1-140">FLAG</span></span>  <br/> |<span data-ttu-id="8ccf1-141">Task</span><span class="sxs-lookup"><span data-stu-id="8ccf1-141">Task</span></span>  <br/> |<span data-ttu-id="8ccf1-142">否</span><span class="sxs-lookup"><span data-stu-id="8ccf1-142">No</span></span>  <br/> |
|<span data-ttu-id="8ccf1-143">运行状况</span><span class="sxs-lookup"><span data-stu-id="8ccf1-143">Health</span></span>  <br/> |<span data-ttu-id="8ccf1-144">TEXT</span><span class="sxs-lookup"><span data-stu-id="8ccf1-144">TEXT</span></span>  <br/> |<span data-ttu-id="8ccf1-145">Task</span><span class="sxs-lookup"><span data-stu-id="8ccf1-145">Task</span></span>  <br/> |<span data-ttu-id="8ccf1-146">未指定</span><span class="sxs-lookup"><span data-stu-id="8ccf1-146">Not specified</span></span>  <br/> |
   
<span data-ttu-id="8ccf1-147">ECFs 中定义的任何项目、 资源或任务从外部的 Project Web 应用程序 (PWA) 实例。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-147">ECFs are defined at the Project Web Application (PWA) instance, external from any project, resource, or task.</span></span> <span data-ttu-id="8ccf1-148">尚未，他们可以成为与项目、 资源或任务关联。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-148">Yet, they can become associated with a project, resource, or task.</span></span> <span data-ttu-id="8ccf1-149">本文提供介绍性检查使用示例应用程序的自定义字段，并重点介绍检索 ECF 值。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-149">This article provides an introductory look at custom fields using a sample application and focuses on retrieving ECF values.</span></span> 
  
<span data-ttu-id="8ccf1-150">您可以下载完整的示例在https://github.com/OfficeDev/Project-CSOM-Read-Enterprise-CustomFields。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-150">You can download the complete sample at https://github.com/OfficeDev/Project-CSOM-Read-Enterprise-CustomFields.</span></span>
  
<span data-ttu-id="8ccf1-151">此外，Project Online 支持本地自定义域作为只读实体特定于特定项目、 资源或任务。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-151">Additionally, Project Online supports local custom fields as read-only entities specific to the specific project, resource, or task.</span></span> <span data-ttu-id="8ccf1-152">本地自定义域的详细信息，请参阅 sample https://github.com/OfficeDev/Project-CSOM-Read-Local-CustomFields\。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-152">For more information on local custom fields, see the sample https://github.com/OfficeDev/Project-CSOM-Read-Local-CustomFields\.</span></span>
  
## <a name="background-materials"></a><span data-ttu-id="8ccf1-153">背景材料</span><span class="sxs-lookup"><span data-stu-id="8ccf1-153">Background materials</span></span>

<span data-ttu-id="8ccf1-154">[开发 Project Online 应用程序使用的客户端对象模型](developing-a-project-online-application-using-the-client-side-object-model.md)，上一篇文章提供了背景和开发应用程序使用 CSOM 的初始方向。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-154">A previous article, [Developing a Project Online application using the client-side object model](developing-a-project-online-application-using-the-client-side-object-model.md), provides background and the initial orientation for developing applications using CSOM.</span></span> <span data-ttu-id="8ccf1-155">请参阅本文的以下各项：</span><span class="sxs-lookup"><span data-stu-id="8ccf1-155">Refer to this article for the following items:</span></span>
  
- <span data-ttu-id="8ccf1-156">有关项目，独立和基于云的版本的背景信息</span><span class="sxs-lookup"><span data-stu-id="8ccf1-156">Background information about Project, stand-alone and cloud-based editions</span></span> 
    
- <span data-ttu-id="8ccf1-157">开发环境 （Visual Studio 版本和软件库）</span><span class="sxs-lookup"><span data-stu-id="8ccf1-157">Development environment (Visual Studio editions and software libraries)</span></span>
    
- <span data-ttu-id="8ccf1-158">Visual Studio 项目安装.NET 应用程序使用 CSOM 库</span><span class="sxs-lookup"><span data-stu-id="8ccf1-158">Visual Studio project setup for a .NET application using the CSOM library</span></span>
    
- <span data-ttu-id="8ccf1-159">连接到 Project Online 服务</span><span class="sxs-lookup"><span data-stu-id="8ccf1-159">Connecting to the Project Online service</span></span>
    
## <a name="preliminaries-class-level-declarations"></a><span data-ttu-id="8ccf1-160">准备事项 （类级别声明）</span><span class="sxs-lookup"><span data-stu-id="8ccf1-160">Preliminaries (class-level declarations)</span></span>

<span data-ttu-id="8ccf1-161">此应用程序的类定义两个数据项： 项目上下文和 pwaECF 词典。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-161">The class for this application defines two data items: the project context and the pwaECF dictionary.</span></span>
  
<span data-ttu-id="8ccf1-162">项目上下文对象属于 Project CSOM，并将连接的应用程序和 PWA 实例。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-162">The project context object is part of the Project CSOM, and connects the application and the PWA instance.</span></span> <span data-ttu-id="8ccf1-163">所有服务请求使用项目上下文。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-163">All requests to the service use the project context.</span></span>
  
```cs
private static ProjectContext projContext = 
     new ProjectContext("https://Contoso216.sharepoint.com/sites/pwa");

```

<span data-ttu-id="8ccf1-164">上下文需要应用程序中创建实例的连接终结点。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-164">The context needs the connection endpoint to create an instance in an application.</span></span> <span data-ttu-id="8ccf1-165">连接终结点是 PWA 实例的 URL。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-165">The connection endpoint is the URL of your PWA instance.</span></span> 
  
<span data-ttu-id="8ccf1-166">PwaECF 词典存储 ECFs PWA 级别定义的项目。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-166">The pwaECF dictionary stores the project ECFs defined at the PWA level.</span></span> <span data-ttu-id="8ccf1-167">该词典使用 ECF。InternalName 作为键和值的 CustomField 对象。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-167">The dictionary uses the ECF.InternalName as the key, and the CustomField object as the value.</span></span> <span data-ttu-id="8ccf1-168">字典是在 ListPWACustomFields 方法中，填充，然后用作在 Main 方法中的引用。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-168">The dictionary is populated in the ListPWACustomFields method, and then used as a reference in the Main method.</span></span> 
  
```cs
    //Dictionary of ECFs
        static Dictionary<String, CustomField> pwaECF = new Dictionary<string, CustomField>();

```

## <a name="main-method"></a><span data-ttu-id="8ccf1-169">Main 方法</span><span class="sxs-lookup"><span data-stu-id="8ccf1-169">Main method</span></span>

<span data-ttu-id="8ccf1-170">Main 方法中管理应用程序流。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-170">The Main method manages the application flow.</span></span> <span data-ttu-id="8ccf1-171">为与其他应用程序使用 Project Online CSOM，Main 初始化项目上下文。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-171">As with other applications that use the Project Online CSOM, Main initializes the project context.</span></span> 
  
1. <span data-ttu-id="8ccf1-172">检索和列表中 Project Online PWA ECFs。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-172">Retrieve and list the ECFs in the Project Online PWA.</span></span>
    
   <span data-ttu-id="8ccf1-173">在 ListPWACustomFields 方法实现此功能。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-173">This functionality is implemented in the ListPWACustomFields method.</span></span>
    
2. <span data-ttu-id="8ccf1-174">检索与自定义域和非自定义域的项目。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-174">Retrieve projects with custom fields and non-custom fields.</span></span>
    
   <span data-ttu-id="8ccf1-175">当检索具有 ECFs 项目，对 Project Online 服务的查询请求需要包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="8ccf1-175">When retrieving projects with ECFs, the query request to the Project Online service needs to include the following items:</span></span> 
    
   - <span data-ttu-id="8ccf1-176">**IncludeCustomFields**&ndash;此项目请求返回的每个已发布的项目，包括支持自定义域的扩展的 PublishedProjects 集合的服务。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-176">**IncludeCustomFields** &ndash; This item requests the service to return a collection of PublishedProjects where each published project includes an extension that supports custom fields.</span></span> <span data-ttu-id="8ccf1-177">指定此项，则除非 Project Online 返回不包括自定义字段数据的 PublishedProject 对象。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-177">Unless this item is specified, Project Online returns PublishedProject objects that do not include Custom Field data.</span></span>
    
   - <span data-ttu-id="8ccf1-178">**IncludeCustomFields.CustomFields** &ndash;此项请求服务来填充 CustomFields 数据 PublishedProject 对象。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-178">**IncludeCustomFields.CustomFields** &ndash; This item requests the service to populate the PublishedProject objects with CustomFields data.</span></span>
    
   <span data-ttu-id="8ccf1-179">以下请求指定项目 Id 和名称，以及自定义字段的对象扩展和自定义字段值。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-179">The following request specifies the project Id and Name, as well as the object extension for custom fields and the custom field values.</span></span>
    
   ```cs
        var projBlk = projContext.LoadQuery(
        projContext.Projects.Include(
            p => p.Id, 
            p => p.Name,
            p => p.IncludeCustomFields,
            p => p.IncludeCustomFields.CustomFields
        ));
    
   ```

3. <span data-ttu-id="8ccf1-180">检查每个项目。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-180">Examine each project.</span></span>
    
   <span data-ttu-id="8ccf1-181">使用此应用程序中的项目对象是 PublishedProject 类型，因为检索并显示值。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-181">The project objects used in this application are the PublishedProject type because the values are retrieved and displayed.</span></span> 
    
   <span data-ttu-id="8ccf1-182">如果您需要更新一个或多个项目中的数据值，正在更新项目将签出和应用程序将使用 DraftProject 对象来检索的值并更新项目。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-182">If you need to update data values in one or more projects, the project undergoing the update would be checked out and the application would use a DraftProject object to retrieve the values and update the project.</span></span>
    
4. <span data-ttu-id="8ccf1-183">访问 project ECF 条目</span><span class="sxs-lookup"><span data-stu-id="8ccf1-183">Accessing the ECF entries for a project</span></span>
    
   <span data-ttu-id="8ccf1-184">每个 ECF 实例分离开来的其余 ECF 信息的字段值。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-184">Each ECF instance separates the field value from the rest of the ECF information.</span></span> <span data-ttu-id="8ccf1-185">字段值的键/值对的一部分存储。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-185">The field value is stored as part of a key/value pair.</span></span> <span data-ttu-id="8ccf1-186">其余的信息存储在 CustomField 对象。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-186">The rest of the information is stored in a CustomField object.</span></span>
    
   <span data-ttu-id="8ccf1-187">访问项目中的 ECF 值由两部分组成：</span><span class="sxs-lookup"><span data-stu-id="8ccf1-187">Accessing ECF values in a project consists of two parts:</span></span>
    
   - <span data-ttu-id="8ccf1-188">循环 CustomFields 集合</span><span class="sxs-lookup"><span data-stu-id="8ccf1-188">Cycling through the CustomFields collection</span></span>
    
   - <span data-ttu-id="8ccf1-189">访问使用两个构造的相应项。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-189">Accessing the proper entry using two constructs.</span></span>
    
   <span data-ttu-id="8ccf1-190">每个项目存储在两个位置，可枚举的 CustomFields 集关联的 ECF 条目和键/值对的一部分的字段值。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-190">Each project stores associated ECF entries in two places, a CustomFields collection that is enumerable and and the field values as part of key/value pairs.</span></span> <span data-ttu-id="8ccf1-191">在键/值对，internalName 是密钥和字段值为值。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-191">In the key/value pairs, the internalName is the key and the field value is the value.</span></span> <span data-ttu-id="8ccf1-192">使用字典保留和访问的字段值。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-192">Use a dictionary to hold and access the field values.</span></span> 
    
   <span data-ttu-id="8ccf1-193">ECF 属性，之外的字段值，存储在 CustomField 对象，每个项目的一个对象。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-193">The ECF properties, other than the field values, are stored in CustomField objects, one object per project.</span></span> <span data-ttu-id="8ccf1-194">使用 CustomFields 集合可访问 ECFs 单个项目相关联。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-194">Use a CustomFields collection to access the ECFs associated with an individual project.</span></span> 
    
5. <span data-ttu-id="8ccf1-195">每个项目存储相关联的 ECFs 其中每个 ECF 项包含的密钥-ECF-和保存的 ECF 值的对象的内部名称集合中。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-195">Each project stores the associated ECFs in a collection where each ECF entry consists of a key--the internal name of the ECF--and an object that holds the value of the ECF.</span></span> <span data-ttu-id="8ccf1-196">传输到字典访问各项的集合。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-196">Transfer the collection to a dictionary to access individual entries.</span></span> <span data-ttu-id="8ccf1-197">声明如下。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-197">The declaration follows.</span></span>
    
   ```cs
    Dictionary<string, object> projDict = pubProj.IncludeCustomFields.FieldValues;
    
   ```

   <span data-ttu-id="8ccf1-198">词典条目中的值对应于 ECF 的数据类型。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-198">The value in a dictionary entry corresponds to the data type of the ECF.</span></span> <span data-ttu-id="8ccf1-199">每个 ECF 的对象映射到各种类型之一。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-199">The object for each ECF maps to one of a variety of types.</span></span> <span data-ttu-id="8ccf1-200">大多数 ECFs 使用纳入标准变量的简单类型。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-200">Most ECFs use simple types that fit into standard variables.</span></span> <span data-ttu-id="8ccf1-201">以下片段显示了最少的处理所涉及的几种类型：</span><span class="sxs-lookup"><span data-stu-id="8ccf1-201">The following fragment shows that minimal processing is involved for several types:</span></span>
    
   ```cs
    switch (cf.FieldType)
    {
        case CustomFieldType.COST:
            decimal costValue = (decimal)oVal;
            Console.WriteLine("\tFieldType:\t{0}\n\tValue:\t{1}", cf.FieldType, 
                costValue.ToString("C"));
            break;
        case CustomFieldType.DATE:
            Console.WriteLine("\tFieldType:\t{0}\n\tValue:\t{1}", cf.FieldType, 
                oVal.ToString());
            break;
        case CustomFieldType.FINISHDATE:
            Console.WriteLine("\tFieldType:\t{0}\n\tValue:\t{1}", cf.FieldType, 
                oVal.ToString());
            break;
        case CustomFieldType.DURATION:
            Console.WriteLine("\tFieldType:\t{0}\n\tValue:\t{1}", cf.FieldType, 
                oVal.ToString());
            break;
        case CustomFieldType.FLAG:
            Console.WriteLine("\tFieldType:\t{0}\n\tValue:\t{1}", cf.FieldType, 
                oVal.ToString());
            break;
        case CustomFieldType.NUMBER:
            Console.WriteLine("\tFieldType:\t{0}\n\tValue:\t{1}", cf.FieldType, 
                oVal.ToString());
            break;
    
   ```

   <span data-ttu-id="8ccf1-202">查阅表格的文本值，但是，需要进行其他处理。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-202">The lookup table of TEXT values, however, requires additional processing.</span></span> <span data-ttu-id="8ccf1-203">应用程序从该服务，检索适当的查阅表格，并通过遍历查阅表格输出 ECF 实例 （与单个或多个值）。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-203">The application retrieves the appropriate lookup table from the service, and outputs the ECF instance (with single or multiple values) by traversing the lookup table.</span></span> <span data-ttu-id="8ccf1-204">下面的代码段显示的文本 ECFs，其中包括与简单值以及那些使用查阅表格的处理：</span><span class="sxs-lookup"><span data-stu-id="8ccf1-204">The following code fragment shows processing of TEXT ECFs, including those with simple values and those using lookup tables:</span></span> 
    
   ```cs
    case CustomFieldType.TEXT:
        if (!cf.LookupTable.ServerObjectIsNull.HasValue ||
            (cf.LookupTable.ServerObjectIsNull.HasValue && 
            cf.LookupTable.ServerObjectIsNull.Value))
        { //No lookup table
            Console.WriteLine("\tFieldType:\t{0}\n\tText:\t{1}", cf.FieldType, 
                oVal.ToString());
        }
        else
        { //Lookup table
            Console.WriteLine("\tFieldType:\t{0} - using Lookup Table", cf.FieldType);
            String[] entries = (String[])oVal;
            foreach (String entry in entries)
            {
                var luEntry = projContext.LoadQuery(cf.LookupTable.Entries
                    .Where(e => e.InternalName == entry));
                projContext.ExecuteQuery();
                Console.WriteLine("\tLookup Value:\t{0}", luEntry.First().FullValue);  
            }
        }
        break;
    
   ```

   <span data-ttu-id="8ccf1-205">此应用程序只需输出值;但是，就可以获得的数据值的更多的含义。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-205">This application simply outputs the value(s); however, it is possible to get more meaning from the data value(s).</span></span>
    
## <a name="listpwacustomfields"></a><span data-ttu-id="8ccf1-206">ListPWACustomFields</span><span class="sxs-lookup"><span data-stu-id="8ccf1-206">ListPWACustomFields</span></span>

<span data-ttu-id="8ccf1-207">ListPWACustomFields 方法检索并列出 ECFs 与项目关联。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-207">The ListPWACustomFields method retrieves and lists the ECFs associated with projects.</span></span> <span data-ttu-id="8ccf1-208">此方法列出了可与各个项目相关联的 PWA 实例上注册 ECFs。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-208">This method lists the ECFs registered on the PWA instance that can be associated with individual projects.</span></span> <span data-ttu-id="8ccf1-209">用于访问 ECFs 的入口点使用 CustomFields 元素的项目上下文，如下面的查询请求中所示：</span><span class="sxs-lookup"><span data-stu-id="8ccf1-209">The entry point for accessing the ECFs uses the CustomFields element of the project context, as in the following query request:</span></span>
  
```cs
// Project ECFs
    var allECFields = 
            projContext.LoadQuery(projContext.CustomFields.Include(
            qp => qp.InternalName,
            qp => qp.Name
        ));
    projContext.ExecuteQuery();

```

<span data-ttu-id="8ccf1-210">该方法不会检查项目是否使用特定 ECF。</span><span class="sxs-lookup"><span data-stu-id="8ccf1-210">The method does not check to see whether a project uses a specific ECF.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8ccf1-211">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8ccf1-211">See also</span></span>

- [<span data-ttu-id="8ccf1-212">项目开发门户</span><span class="sxs-lookup"><span data-stu-id="8ccf1-212">Project Development Portal</span></span>](https://developer.microsoft.com/en-us/project)
- [<span data-ttu-id="8ccf1-213">概述： 企业自定义域和查阅表格</span><span class="sxs-lookup"><span data-stu-id="8ccf1-213">Overview: Enterprise custom fields and lookup tables</span></span>](https://support.office.com/en-us/article/overview-enterprise-custom-fields-and-lookup-tables-f99db553-0b33-4648-93c0-f6a74637d790?ui=en-us&rs=en-us&ad=us)
- <span data-ttu-id="8ccf1-214">[本地和企业自定义域](https://msdn.microsoft.com/en-us/library/office/ms447495(v=office.14).aspx)</span><span class="sxs-lookup"><span data-stu-id="8ccf1-214">[Local and Enterprise Custom Fields](https://msdn.microsoft.com/en-us/library/office/ms447495(v=office.14).aspx)</span></span>
- [<span data-ttu-id="8ccf1-215">添加或编辑 Project Server 2013 中的企业自定义域</span><span class="sxs-lookup"><span data-stu-id="8ccf1-215">Add or edit enterprise custom fields in Project Server 2013</span></span>](https://docs.microsoft.com/en-us/project/add-or-edit-enterprise-custom-fields-in-project-server)
    

