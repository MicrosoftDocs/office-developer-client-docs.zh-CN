---
title: 批量更新自定义域，并创建项目Project Online
manager: soliver
ms.date: 08/10/2016
ms.audience: Developer
localization_priority: Normal
ms.assetid: 815131c6-190c-4f29-83bf-c853eee72821
description: 为了帮助客户充分利用 Project Online并提高服务的可扩展性和灵活性，我们向客户端对象模型添加了两种方法，可用于 Project Online 应用和工作流。
ms.openlocfilehash: 4de42471cd8c2f12a982447ccffc27ec8104fa31
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355338"
---
# <a name="bulk-update-custom-fields-and-create-project-sites-from-a-workflow-in-project-online"></a>批量更新自定义字段并通过 Project Online 中的工作流创建项目网站

为了帮助客户充分利用 Project Online并提高服务的可扩展性和灵活性，我们向客户端对象模型添加了两种方法，可用于 Project Online 应用和工作流。
  
|||
|:-----|:-----|
|**UpdateCustomFields** <br/> |批量更新项目自定义域。 仅Project Online。 仅在 REST API 中可用。  <br/> |
|**CreateProjectSite** <br/> | 创建Project网站。 仅Project Online。 在 REST API、托管客户端对象模型和 JavaScript 客户端对象模型中可用。  <br/> |
   
除了提供更大的灵活性之外，这些方法还在工作流中保存和发布项目时提供了显著的性能改进。 本文介绍如何使用 REST API 中的方法，并提供有关创建可批量更新自定义域的工作流和创建网站集的Project说明。
  
> [!NOTE]
> 若要了解有关从 SharePoint 2013 工作流调用 REST API 的信息，请参阅 Using [SharePoint REST services from workflow with POST method](https://mysharepointinsight.blogspot.com/2013/05/using-sharepoint-rest-services-from.mdl)和 Calling the SharePoint [2013 Rest API from a SharePoint Designer Workflow。](https://sergeluca.wordpress.com/2013/04/09/calling-the-sharepoint-2013-rest-api-from-a-sharepoint-designer-workflow/) 
  
## <a name="bulk-update-project-custom-fields-from-a-workflow"></a>从工作流批量更新项目自定义域
<a name="BulkUpdateCustomFields"> </a>

以前，工作流一次只能更新一个自定义域。 当用户在详细信息页面之间转换时，一次更新一个项目自定义域Project较差的最终用户体验。 每个更新都需要使用 Set Project **Field** 操作创建单独的服务器请求，在高延迟、低带宽网络上更新多个自定义字段会导致非比的开销。 为了解决此问题，我们向 REST API 添加了 **UpdateCustomFields** 方法，允许您批量更新自定义字段。 若要使用 **UpdateCustomFields，** 请传递包含要更新的所有自定义域的名称和值的字典。
  
REST 方法位于以下终结点：
  
`https://<site-url>/_api/ProjectServer/Projects('<guid>')/Draft/UpdateCustomFields()`
  
> [!NOTE]
> 将示例中的占位符替换为网站 URL，Project Web App (PWA) `<site-url>` `<guid>` UID 替换占位符。 
  
本节介绍如何创建可批量更新项目的自定义域的工作流。 工作流遵循以下高级步骤：
  
- 等待要更新的项目签入
    
- 生成一个定义项目的所有自定义域更新的数据集
    
- 签出项目
    
- 调用 **UpdateCustomFields** 以将自定义域更新应用于项目 
    
- 将相关信息记录到工作流历史记录列表 (如果需要) 
    
- 发布项目
    
- 签入项目
    
最终的端到端工作流如下所示：
  
![端到端工作流](media/8c0741f9-7f76-409d-8c00-e7a8c3ddb89f.png "端到端工作流")
  
### <a name="to-create-a-workflow-that-bulk-updates-custom-fields"></a>创建批量更新自定义域的工作流

1. 可选。 将项目的完整 URL 存储在变量中，您可以在整个工作流中使用该变量。
    
    ![将项目的 URL 存储在变量中](media/a880c5c6-8e7a-44dd-87e9-7e532169d489.png "将项目的 URL 存储在变量中")
  
2. 将"**等待Project事件**"操作添加到工作流，然后选择"**签入项目时"** 事件。 
    
    ![等待项目签入 等待](media/699aa9c7-b3c9-426e-a775-96993a13559c.png "项目签入")
  
3. 使用" **生成字典"** 操作创建 **requestHeader** 字典。 您将对此工作流中所有 Web 服务调用使用相同的请求标头。 
    
    ![生成 requestHeader 字典](media/83b0aa10-9ab7-43dd-800d-a738bb815876.png "生成 requestHeader 字典")
  
4. 将以下两项添加到字典。
    
    |名称|类型|值|
    |:-----|:-----|:-----|
    |Accept  <br/> |String  <br/> |application/json;odata=verbose  <br/> |
    |Content-Type  <br/> |String  <br/> |application/json;odata=verbose  <br/> |
   
    ![添加 Accept 标头](media/2f2e2016-3c49-4cac-b1e7-f2b8118b840c.png "添加 Accept 标头")
  
5. 使用" **生成字典** "操作创建 **requestBody** 字典。 此字典存储要应用的所有字段更新。 
    
    每个自定义字段更新都需要四行：字段的 (1) 元数据类型、 (2) 键、 (3) 值和 (4) 值类型。
    
    - **__metadata/type** 字段的元数据类型。 此记录始终相同，并具有以下值： 
    
       - 名称：customFieldDictionary (i) /__metadata/type (其中 **i** 是字典中每个自定义域的索引，从 0 开始)  
            
       - 类型：字符串
            
       - 值：SP。KeyValue
    
       ![定义自定义字段更新](media/a4423493-6603-42ee-ae50-1ef74c5c59bd.png "定义自定义字段更新")
  
    - **键** 自定义域的内部名称，格式为 *：Custom_ce23fbf43fa0e411941000155d3c8201* 
    
       您可以通过导航到自定义字段的 InternalName 终结点来查找 **该字段的内部** 名称： `https://<site-url>/_api/ProjectServer/CustomFields('<guid>')/InternalName`
    
       如果手动创建自定义域，值将因网站不同而不同。 如果您计划跨多个网站重用工作流，请确保自定义域的 ID 正确。
    
    - **值** 要分配给自定义域的值。 对于链接到查找表的自定义域，您需要使用查找表条目的内部名称，而不是实际的查找表值。 
    
       您可以在以下终结点找到查找表条目的内部名称： `https://<site-url>/_api/ProjectServer/CustomFields('<guid>')/LookupEntries('<guid>')/InternalName`
    
       如果将查找表自定义域设置为接受多个值，请使用 连接 (如下面的示例字典  `;#` 中所示) 。 
    
    - **ValueType** 要更新的自定义域的类型。 
    
       - 对于"文本"、"持续时间"、"标志"和"LookupTable"字段，请使用 Edm.String
    
       - 对于"数字"字段，请使用 Edm.Int32、Edm.Double 或其他任何 OData 接受的号码类型
    
       - 对于 Date 字段，请使用 Edm.DateTime
    
       下面的示例字典定义三个自定义域的更新。 第一个针对多值查找表自定义域，第二个针对数字字段，第三个用于日期字段。 请注意 **customFieldDictionary** 索引的增量方式。 
    
       > [!NOTE]
       > 这些值仅用于说明目的。 将使用的键值对取决于您PWA数据。 
  
       |名称|类型|值|
       |:-----|:-----|:-----|
       |customFieldDictionary (0) /__metadata/type  <br/> |String  <br/> |SP。KeyValue  <br/> |
       |customFieldDictionary (0) /Key  <br/> |String  <br/> |自定义 \_ ce23fbf43fa0e411941000155d3c8201  <br/> |
       |customFieldDictionary (0) /Value  <br/> |String  <br/> |条目 \_ b9a2fd69279de411940f00155d3c8201;#Entry \_ baa2fd69279de411940f00155d3c8201  <br/> |
       |customFieldDictionary (0) /ValueType  <br/> |String  <br/> |Edm.String  <br/> |
       |customFieldDictionary (1) /__metadata/type  <br/> |String  <br/> |SP。KeyValue  <br/> |
       |customFieldDictionary (1) /Key  <br/> |String  <br/> |Custom_c7f114c97098e411940f00155d3c8201  <br/> |
       |customFieldDictionary (1) /Value  <br/> |String  <br/> |90.5  <br/> |
       |customFieldDictionary (1) /ValueType  <br/> |String  <br/> |Edm.Double  <br/> |
       |customFieldDictionary (2) /__metadata/type  <br/> |String  <br/> |SP。KeyValue  <br/> |
       |customFieldDictionary (2) /Key  <br/> |String  <br/> |Custom_c6fb67e0b9a1e411941000155d3c8201  <br/> |
       |customFieldDictionary (2) /Value  <br/> |String  <br/> |2015-04-01T00：00：00.00000000  <br/> |
       |customFieldDictionary (2) /ValueType  <br/> |String  <br/> |Edm.DateTime  <br/> |
   
       ![定义自定义字段更新的](media/41a1f18f-a6b2-40ff-904b-437baf962621.png "字典 定义自定义字段更新")
  
6. 添加 **Call HTTP Web Service** 操作以签出项目。 
    
    ![调用 Checkout 方法](media/8ce56014-0317-419b-afa7-229d05c86885.png "调用 Checkout 方法")
  
7. 编辑 Web 服务调用的属性以指定请求标头。 若要打开 **"属性**"对话框，请右键单击该操作并选择"属性 **"。**
    
    ![在 Web 服务调用属性中]指定请求标头(media/d81e92b1-43df-42ad-9cd0-a693f93b164e.png "在 Web 服务调用属性中指定请求标头")
  
8. 添加 Call **HTTP Web Service** 操作以调用 **UpdateCustomFields** 方法。 
    
    ![Create a Call HTTP Web Service action]Create a Call HTTP Web Service(media/9a73a201-c035-41b4-8798-506ac48b90f8.png "action")
  
    记下  `/Draft/` Web 服务 URL 中的段。 完整 URL 应如下所示： `https://<site-url>/_api/ProjectServer/Projects('<guid>')/Draft/UpdateCustomFields()`
    
    ![调用 UpdateCustomFields 方法](media/03b323f1-8e99-4b18-be18-be505d7cec7e.png "调用 UpdateCustomFields 方法")
  
9. 编辑 Web 服务调用的属性以将 **RequestHeader** 和 **RequestContent** 参数绑定到您创建的词典。 您还可以创建一个新变量来存储 **ResponseContent**。
    
    ![将字典绑定到请求标头和内容](media/f96bec92-138e-4eab-b1e7-1ab83d0428a5.png "将字典绑定到请求标头和内容")
  
10. 可选。 从响应字典中读取，以检查队列作业的状态，并记录工作流历史记录列表中的信息。
    
    ![设置日志记录](media/7d2f4936-61d7-4906-83e8-7478a5935af5.png "设置日志记录")
  
11. 将 Web 服务调用添加到 **发布终结点** 以发布项目。 始终使用相同的请求标头。 
    
    ![调用 Publish 方法](media/3b661091-ffae-4d7e-a0bb-5b96a6292731.png "调用 Publish 方法")
  
    ![发布 Web 服务调用的属性](media/6a80a5d3-7e29-4398-993c-f78b3faca8b1.png "发布 Web 服务调用的属性")
  
12. 将最终 Web 服务调用添加到 **Checkin** 终结点以签入项目。 
    
    ![调用 Checkin 方法](media/430510cb-0774-4911-af7f-b565b83eba0e.png "调用 Checkin 方法")
  
    ![Checkin Web 服务调用](media/485f48d6-bbb8-4568-9dc3-aae3218f6bd1.png "的属性 Checkin Web")服务调用的属性

<a name="CreateProjectSite"> </a>

## <a name="create-a-project-site-from-a-workflow"></a>从Project创建网站

每个项目都可以有其自己的专用SharePoint工作组成员可在其中进行协作、共享文档、提出问题等。 以前，网站只能在首次发布时自动创建，或由 Project Professional 中的项目经理或管理员在 PWA 设置中自动创建，或者可以将其禁用。
  
我们添加了 **CreateProjectSite** 方法，因此您可以选择何时创建项目网站。 对于想要在项目建议达到预定义工作流中的特定阶段（而不是首次发布时）自动创建网站的组织来说，这尤其有用。 推迟项目网站创建可显著提高项目的创建性能。 
  
**先决条件：** 在可以使用 **CreateProjectSite** 之前，必须为 PWA 设置 > ** Connected SharePoint Sites ** **>** 设置 中的项目网站创建 **设置。**
  
![在"设置"中设置"允许用户PWA"](media/6c6c8175-eb10-431d-8056-cea55718fdb4.png "设置\"允许用户在PWA选择\"")
  
### <a name="to-create-a-workflow-that-creates-a-project-site"></a>创建创建网站集Project工作流

1. 创建或编辑现有工作流，然后选择要创建现有工作流Project步骤。
    
2. 使用" **生成字典"** 操作创建 **requestHeader** 字典。 
    
    ![生成 requestHeader 字典](media/83b0aa10-9ab7-43dd-800d-a738bb815876.png "生成 requestHeader 字典")
  
3. 将以下两项添加到字典。
    
    |名称|类型|值|
    |:-----|:-----|:-----|
    |Accept  <br/> |String  <br/> |application/json;odata=verbose  <br/> |
    |Content-Type  <br/> |String  <br/> |application/json;odata=verbose  <br/> |
   
    ![添加 Accept 标头](media/2f2e2016-3c49-4cac-b1e7-f2b8118b840c.png "添加 Accept 标头")
  
4. 添加" **调用 HTTP Web 服务"** 操作。 将请求类型更改为使用 **POST**，并使用以下格式设置 URL：
    
    `https://<site-url>/_api/ProjectServer/Projects('<guid>')/CreateProjectSite('New web name')`
    
    ![生成 CreateProjectSite 终结点 URI](media/42a90a5e-8d1b-4667-a933-785175212847.png "生成 CreateProjectSite 终结点 URI")
  
    将网站名称作为Project **传递给 CreateProjectSite** 方法。 若要使用项目名称作为网站名称，请传递一个空字符串。 请务必使用唯一的名称，以便你创建的下一个项目网站能够正常工作。 
    
5. 编辑 Web 服务调用的属性以将 **RequestHeader** 参数绑定到您创建的词典。 
    
    ![将字典绑定到请求](media/61a5a0a8-405f-44eb-b5e7-80b11f7caec3.png "将字典绑定到请求")
  
## <a name="see-also"></a>另请参阅

- [Project 编程任务](project-programming-tasks.md)
- [Project 2013 的客户端对象模型 (CSOM)](client-side-object-model-csom-for-project-2013.md)
- [SharePoint 2013 中的工作流](https://msdn.microsoft.com/library/e0602371-ae22-44be-8a7e-9e47e9f046d6%28Office.15%29.aspx)
    

