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
# <a name="bulk-update-custom-fields-and-create-project-sites-from-a-workflow-in-project-online"></a>批量更新自定义字段并从 Project Online 中的工作流创建项目网站

为帮助客户充分利用 Project Online 和改进我们的服务扩展性和灵活性，我们为添加了两种方法可以在 Project Online 的应用程序和工作流中使用的客户端对象模型。
  
|||
|:-----|:-----|
|**UpdateCustomFields** <br/> |批量更新项目自定义域。 对于仅 Project Online。 仅在 REST API 中可用。  <br/> |
|**CreateProjectSite** <br/> | 创建项目网站。 对于仅 Project Online。 在 REST API、 托管客户端对象模型和 JavaScript 客户端对象模型中可用。  <br/> |
   
除了提供更大的灵活性，这些方法还提供了显著的性能改进保存和发布工作流中的项目时。 本文介绍如何使用 REST API 中的方法，并提供用于创建工作流的批量更新自定义字段和创建项目网站的工作流的说明。
  
> [!NOTE]
> 若要了解更多 REST Api 调用从 SharePoint 2013 工作流，请参阅[从 POST 方法与工作流的使用 SharePoint REST 服务](https://mysharepointinsight.blogspot.com/2013/05/using-sharepoint-rest-services-from.mdl)和[调用从 SharePoint Designer 工作流的 SharePoint 2013 Rest API](https://sergeluca.wordpress.com/2013/04/09/calling-the-sharepoint-2013-rest-api-from-a-sharepoint-designer-workflow/)。 
  
## <a name="bulk-update-project-custom-fields-from-a-workflow"></a>批量更新项目从工作流的自定义字段
<a name="BulkUpdateCustomFields"> </a>

以前，工作流仅一次更新一个自定义字段。 一次更新项目自定义域一个会导致时用户转换项目详细信息页面之间的差的最终用户体验。 每个更新所需使用**设置项目域**操作，一个单独的服务器请求和更新多个自定义字段在高延迟低带宽网络导致不常用的开销。 若要解决此问题，我们**UpdateCustomFields**方法添加到允许您批量更新自定义字段 REST API。 若要使用**UpdateCustomFields**，您将传递包含的名称和您要更新的所有自定义字段值词典中。
  
下面的终结点上可以找到 REST 方法：
  
`https://<site-url>/_api/ProjectServer/Projects('<guid>')/Draft/UpdateCustomFields()`
  
> [!NOTE]
> 替换`<site-url>`的 Project Web App (PWA) 网站的 url 示例中的占位符和`<guid>`与您的项目 UID 的占位符。 
  
本节介绍如何创建工作流的批量更新项目的自定义域。 工作流包括以下高级步骤：
  
- 等待要更新，以获取签入项目
    
- 构建一个定义项目的所有自定义字段更新的数据集
    
- 签出项目
    
- 调用**UpdateCustomFields**自定义字段更新应用到项目 
    
- 登录相关信息的工作流历史记录列表 （如果需要）
    
- 发布项目
    
- 签入项目
    
最终的端到端工作流如下所示：
  
![端到端工作流](media/8c0741f9-7f76-409d-8c00-e7a8c3ddb89f.png "端到端工作流")
  
### <a name="to-create-a-workflow-that-bulk-updates-custom-fields"></a>创建工作流的批量更新自定义字段

1. 可选。 您可以使用整个工作流变量中存储项目的完整的 URL。
    
    ![存储在变量中的项目的 URL](media/a880c5c6-8e7a-44dd-87e9-7e532169d489.png "存储在变量中的项目的 URL")
  
2. 将**等待项目事件**操作添加到工作流，并选择**一个项目签入时**事件。 
    
    ![等待要签入的项目](media/699aa9c7-b3c9-426e-a775-96993a13559c.png "等待要签入的项目")
  
3. 创建使用**生成字典**操作**requestHeader**词典。 所有 web 服务调用该工作流中，您可以使用相同的请求标头。 
    
    ![生成字典 requestHeader](media/83b0aa10-9ab7-43dd-800d-a738bb815876.png "生成字典 requestHeader")
  
4. 将以下两项添加到词典。
    
    |名称|类型|值|
    |:-----|:-----|:-----|
    |Accept  <br/> |String  <br/> |应用程序/json;odata = verbose  <br/> |
    |Content-Type  <br/> |String  <br/> |应用程序/json;odata = verbose  <br/> |
   
    ![添加 Accept 标头](media/2f2e2016-3c49-4cac-b1e7-f2b8118b840c.png "添加 Accept 标头")
  
5. 创建使用**生成字典**操作**requestBody**词典。 该词典存储要应用的所有字段更新。 
    
    每个自定义字段更新需要四行： 该字段的 （1） 元数据类型、 （2） 密钥、 （3） 值和 （4） 值类型。
    
    - **__metadata/类型**该字段的元数据类型。 此记录始终是相同，并使用以下值： 
    
       - 名称： customFieldDictionary （i）/__metadata/类型 （其中**i**是中每个自定义字段的词典，从 0 开始进行索引） 
            
       - 类型：字符串
            
       - 值： sp。KeyValue
    
       ![定义自定义字段更新](media/a4423493-6603-42ee-ae50-1ef74c5c59bd.png "定义自定义字段更新")
  
    - **键**格式中的自定义字段的内部名称： *Custom_ce23fbf43fa0e411941000155d3c8201* 
    
       您可以通过导航到它的**InternalName**终结点中找到的自定义字段的内部名称：`https://<site-url>/_api/ProjectServer/CustomFields('<guid>')/InternalName`
    
       如果手动创建自定义域，值将不同站点到站点。 如果您打算在多个网站重用工作流，请确保自定义字段 Id 正确。
    
    - **值**要分配自定义域的值。 链接到查阅表格的自定义域，您需要使用而不是实际的查阅表格值的查找表条目的内部名称。 
    
       您可以找到以下端点处的查阅表格项的内部名称：`https://<site-url>/_api/ProjectServer/CustomFields('<guid>')/LookupEntries('<guid>')/InternalName`
    
       如果您具有查找表自定义字段设置为接受多个值，请使用`;#`来连接值 （如下面的示例词典中所示）。 
    
    - **ValueType**要更新的自定义字段类型。 
    
       - 对于文本、 工期、 标志和 LookupTable 字段，使用 Edm.String
    
       - 对于数字字段，使用 Edm.Int32、 Edm.Double 或任何其他 OData 接受数字类型
    
       - 对于日期字段中，使用 Edm.DateTime
    
       下面的示例词典定义三个自定义域的更新。 第一个是多值查找表自定义字段、 第二个是数字字段，和第三个是日期字段。 注意如何**customFieldDictionary**索引增量。 
    
       > [!NOTE]
       > 这些值是仅用于图。 您可以使用的键 / 值对取决于您的 PWA 数据。 
  
       |名称|类型|值|
       |:-----|:-----|:-----|
       |customFieldDictionary (0) / __metadata/类型  <br/> |String  <br/> |SP。KeyValue  <br/> |
       |customFieldDictionary (0) / 键  <br/> |String  <br/> |自定义\_ce23fbf43fa0e411941000155d3c8201  <br/> |
       |customFieldDictionary (0) / 值  <br/> |String  <br/> |条目\_b9a2fd69279de411940f00155d3c8201; #Entry\_baa2fd69279de411940f00155d3c8201  <br/> |
       |customFieldDictionary (0) / ValueType  <br/> |String  <br/> |Edm.String  <br/> |
       |customFieldDictionary （1）/__metadata/类型  <br/> |String  <br/> |SP。KeyValue  <br/> |
       |customFieldDictionary （1）/键  <br/> |String  <br/> |Custom_c7f114c97098e411940f00155d3c8201  <br/> |
       |customFieldDictionary （1）/值  <br/> |String  <br/> |90.5  <br/> |
       |customFieldDictionary （1) / ValueType  <br/> |String  <br/> |Edm.Double  <br/> |
       |customFieldDictionary （2）/__metadata/类型  <br/> |String  <br/> |SP。KeyValue  <br/> |
       |customFieldDictionary （2）/键  <br/> |String  <br/> |Custom_c6fb67e0b9a1e411941000155d3c8201  <br/> |
       |customFieldDictionary （2）/值  <br/> |String  <br/> |2015-04-01T00:00:00.0000000  <br/> |
       |customFieldDictionary （2) / ValueType  <br/> |String  <br/> |Edm.DateTime  <br/> |
   
       ![定义自定义字段更新的字典](media/41a1f18f-a6b2-40ff-904b-437baf962621.png "定义自定义字段更新的字典")
  
6. 添加**调用 HTTP Web 服务**操作签出的项目。 
    
    ![调用 Checkout 方法](media/8ce56014-0317-419b-afa7-229d05c86885.png "调用 Checkout 方法")
  
7. 编辑 web 服务调用指定请求标头的属性。 要打开**属性**对话框，请右键单击操作，然后选择**属性**。
    
    ![指定在 web 服务请求标头调用属性](media/d81e92b1-43df-42ad-9cd0-a693f93b164e.png "指定在 web 服务请求标头调用属性")
  
8. 添加**调用 HTTP Web 服务**操作调用**UpdateCustomFields**方法。 
    
    ![创建一个调用 HTTP Web 服务操作](media/9a73a201-c035-41b4-8798-506ac48b90f8.png "创建一个调用 HTTP Web 服务操作")
  
    注意`/Draft/`段中的 web 服务 URL。 完整的 URL 应如下所示：`https://<site-url>/_api/ProjectServer/Projects('<guid>')/Draft/UpdateCustomFields()`
    
    ![调用 UpdateCustomFields 方法](media/03b323f1-8e99-4b18-be18-be505d7cec7e.png "调用 UpdateCustomFields 方法")
  
9. 编辑 web 服务调用将**RequestHeader**和**RequestContent**参数绑定词典您创建的属性。 您还可以创建的新变量来存储**ResponseContent**。
    
    ![绑定到的请求标头和内容的词典](media/f96bec92-138e-4eab-b1e7-1ab83d0428a5.png "绑定到的请求标头和内容的词典")
  
10. 可选。 读取响应字典来检查队列作业的状态和日志中的工作流历史记录列表的信息。
    
    ![设置日志记录](media/7d2f4936-61d7-4906-83e8-7478a5935af5.png "设置日志记录")
  
11. 添加到**发布**的终结点的 web 服务调用，以发布项目。 始终使用相同的请求标头。 
    
    ![调用发布方法](media/3b661091-ffae-4d7e-a0bb-5b96a6292731.png "调用发布方法")
  
    ![发布 web 服务的属性呼叫](media/6a80a5d3-7e29-4398-993c-f78b3faca8b1.png "发布 web 服务的属性呼叫")
  
12. 添加对**Checkin**终结点的最后一个 web 服务调用，签入项目。 
    
    ![调用 Checkin 方法](media/430510cb-0774-4911-af7f-b565b83eba0e.png "调用 Checkin 方法")
  
    ![签入 web 服务的属性呼叫](media/485f48d6-bbb8-4568-9dc3-aae3218f6bd1.png "签入 web 服务的属性呼叫")

<a name="CreateProjectSite"> </a>

## <a name="create-a-project-site-from-a-workflow"></a>从工作流创建项目网站

每个项目都可以具有自己专用的 SharePoint 网站，其中工作组成员可以协作、 共享文档、 提出问题，等等。 以前，无法仅创建网站上自动首先发布或手动按项目经理在 Project Professional 或 PWA 中的管理员设置，也无法被禁用。
  
我们已添加**CreateProjectSite**方法，以便您可以选择何时创建项目网站。 这是对要项目建议达到预定义工作流中的特定容器时自动创建其网站，而不是第一个发布的组织特别有用。 推迟项目网站创建会显著提高了创建项目的性能。 
  
**必备：** 您可以使用**CreateProjectSite**之前，必须**设置 PWA**中创建的项目网站设置**允许用户选择**设置 > * * 连接的 SharePoint 网站 * * >**设置**。
  
![设置 PWA 设置中的"允许用户选择"](media/6c6c8175-eb10-431d-8056-cea55718fdb4.png "设置允许用户选择在 PWA 的设置")
  
### <a name="to-create-a-workflow-that-creates-a-project-site"></a>创建工作流创建项目网站

1. 创建或编辑现有工作流和选择想要创建项目网站的步骤。
    
2. 创建使用**生成字典**操作**requestHeader**词典。 
    
    ![生成字典 requestHeader](media/83b0aa10-9ab7-43dd-800d-a738bb815876.png "生成字典 requestHeader")
  
3. 将以下两项添加到词典。
    
    |名称|类型|值|
    |:-----|:-----|:-----|
    |Accept  <br/> |String  <br/> |应用程序/json;odata = verbose  <br/> |
    |Content-Type  <br/> |String  <br/> |应用程序/json;odata = verbose  <br/> |
   
    ![添加 Accept 标头](media/2f2e2016-3c49-4cac-b1e7-f2b8118b840c.png "添加 Accept 标头")
  
4. 添加**调用 HTTP Web 服务**操作。 更改要使用**POST**请求类型，并设置使用以下格式的 URL:
    
    `https://<site-url>/_api/ProjectServer/Projects('<guid>')/CreateProjectSite('New web name')`
    
    ![构建 CreateProjectSite 终结点 URI](media/42a90a5e-8d1b-4667-a933-785175212847.png "构建 CreateProjectSite 终结点 URI")
  
    作为字符串传递给**CreateProjectSite**方法的项目网站的名称。 若要作为网站名称中使用的项目名称，传递一个空字符串。 请务必使用唯一的名称，因此您创建的下一个项目网站将起作用。 
    
5. 编辑将**RequestHeader**参数绑定到字典 web 服务呼叫您创建的属性。 
    
    ![绑定到请求的词典](media/61a5a0a8-405f-44eb-b5e7-80b11f7caec3.png "绑定到请求的词典")
  
## <a name="see-also"></a>另请参阅

- [Project 编程任务](project-programming-tasks.md)
- [Project 2013 的客户端对象模型 (CSOM)](client-side-object-model-csom-for-project-2013.md)
- [SharePoint 2013 中的工作流](https://msdn.microsoft.com/library/e0602371-ae22-44be-8a7e-9e47e9f046d6%28Office.15%29.aspx)
    

