---
title: 访问 Project Online 企业自定义域
manager: soliver
ms.date: 11/08/2016
ms.audience: Developer
ms.assetid: 25509631-fa14-49d8-b594-cfacf5355c38
description: Project Online 是 Office 365 服务，公司可以通过扩展此服务来满足业务需求。 其中一个扩展区域是企业自定义域 (ECF)。 ECF 是可添加到项目、资源和任务的类型化值域。 下表列出了与项目、资源和任务相关联的 ECF，并提供了相应 ECF 实例的值示例：
localization_priority: Priority
ms.openlocfilehash: 9f754f1446890ae021bf6f7000ffba11e2a2df33
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355081"
---
# <a name="accessing-project-online-enterprise-custom-fields"></a>访问 Project Online 企业自定义域

Project Online 是 Office 365 服务，公司可以通过扩展此服务来满足业务需求。 其中一个扩展区域是企业自定义域 (ECF)。 ECF 是可添加到项目、资源和任务的类型化值域。 下表列出了与项目、资源和任务相关联的 ECF，并提供了相应 ECF 实例的值示例：
  
|ECF 名称|ECF 类型|关联项|示例值|
|:-----|:-----|:-----|:-----|
|理由  <br/> |文本  <br/> |项目  <br/> |最终用户可以记录重要的统计信息及运行状况数据，其中包含运行状况评估和旨在改善运行状况的个性化操作计划等结果。  <br/> |
|风险评级  <br/> |文本  <br/> |项目  <br/> |低  <br/> |
|ROI  <br/> |数字  <br/> |项目  <br/> |2.10  <br/> |
|总成本  <br/> |成本  <br/> |项目  <br/> |$1,031,514  <br/> |
|启动团队  <br/> |文本  <br/> |资源  <br/> |是  <br/> |
|职位  <br/> |文本  <br/> |资源  <br/> |测试人员  <br/> |
|标记状态  <br/> |标记  <br/> |任务  <br/> |否  <br/> |
|运行状况  <br/> |文本  <br/> |任务  <br/> |未指定  <br/> |
   
ECF 在 Project Web Application (PWA) 实例中定义，位于任何项目、资源或任务的外部。 但它们可与项目、资源或任务关联。 本文通过示例应用程序介绍了自定义域，重点介绍了检索 ECF 值。 
  
可以从 https://github.com/OfficeDev/Project-CSOM-Read-Enterprise-CustomFields 下载完整的示例。
  
此外，Project Online 支持本地自定义域作为特定于特定项目、资源或任务的只读实体。 有关本地自定义域的详细信息，请参阅示例 https://github.com/OfficeDev/Project-CSOM-Read-Local-CustomFields\。
  
## <a name="background-materials"></a>背景材料

之前的文章[使用客户端对象模型开发 Project Online 应用程序](developing-a-project-online-application-using-the-client-side-object-model.md)提供了使用 CSOM 开发应用程序的背景和初始方向。 请参阅此文，以了解下列项目：
  
- Project 独立版本和基于云的版本的相关背景信息。 
    
- 开发环境（Visual Studio 版本和软件库）
    
- 针对使用 CSOM 库的 .NET 应用程序的 Visual Studio 项目安装
    
- 连接到 Project Online 服务
    
## <a name="preliminaries-class-level-declarations"></a>先决条件（类别级别声明）

此应用程序的类别定义两个数据项：项目上下文和 pwaECF 字典。
  
项目上下文对象是 Project CSOM 的一部分，并且连接了应用程序和 PWA 实例。 对此服务的所有请求均使用项目上下文。
  
```cs
private static ProjectContext projContext = 
     new ProjectContext("https://Contoso216.sharepoint.com/sites/pwa");

```

上下文需要使用连接终结点，来在应用程序中创建实例。 连接终结点是 PWA 实例的 URL。 
  
pwaECF 字典存储 PWA 级别定义的项目 ECF。 此字典将 ECF.InternalName 用作键，并将 CustomField 对象用作值。 此字典使用 ListPWACustomFields 方法填充，然后用作 Main 方法中的引用。 
  
```cs
    //Dictionary of ECFs
        static Dictionary<String, CustomField> pwaECF = new Dictionary<string, CustomField>();

```

## <a name="main-method"></a>Main 方法

Main 方法管理应用程序流。 与其他使用 Project Online CSOM 的应用程序相同，Main 初始化项目上下文。 
  
1. 检索并列出 Project Online PWA 中的 ECF。
    
   此功能使用 ListPWACustomFields 方法实现。
    
2. 检索包含自定义域和非自定义域的项目。
    
   检索包含 ECF 的项目时，对 Project Online 服务的查询请求需要包括下列项目： 
    
   - **IncludeCustomFields** &ndash; 此项目请求服务返回 PublishedProjects 集合，其中的每个已发布项目均包含支持自定义域的扩展。 若未指定此项目，Project Online 将返回不包含自定义域数据的 PublishedProject 对象。
    
   - **IncludeCustomFields.CustomFields** &ndash; 此项目请求服务使用 CustomFields 数据填充 PublishedProject 对象。
    
   下列请求指定项目 ID 和名称，以及自定义域的对象扩展和自定义域值。
    
   ```cs
        var projBlk = projContext.LoadQuery(
        projContext.Projects.Include(
            p => p.Id, 
            p => p.Name,
            p => p.IncludeCustomFields,
            p => p.IncludeCustomFields.CustomFields
        ));
    
   ```

3. 查看各个项目。
    
   此应用程序使用的项目对象为 PublishedProject 类型，因为将检索和显示值。 
    
   如需更新一个或多个项目的数据值，将签出正在进行更新的项目，应用程序将使用 DraftProject 对象检索值并更新项目。
    
4. 访问项目的 ECF 条目
    
   每个 ECF 实例均会将域值与其他 ECF 信息分隔开。 域值存储为键值对的一部分。 其他信息存储在 CustomField 中。
    
   访问项目的 ECF 值包含两个部分：
    
   - 循环 CustomField 集合
    
   - 使用两个构造访问相应的条目。
    
   每个项目均会将相关联的 ECF 条目存储在两个位置：可枚举的 CustomFields 集合和属于键值对组成部分的域值。 在键值对中，internalName 是键，域值为值。 使用字典保管和访问域值。 
    
   除域值以外的 ECF 属性存储在 CustomField 对象中，一个对象对应一个项目。 使用 CustomFields 集合访问单个项目关联的 ECF。 
    
5. 每个项目均将相关联的 ECF 存储在一个集合中，其中的每个 ECF 条目由键（ECF 的内部名称）和对象（保管 ECF 值的对象）组成。 将此集合迁移到字典，以访问各个条目。 声明随附在后面。
    
   ```cs
    Dictionary<string, object> projDict = pubProj.IncludeCustomFields.FieldValues;
    
   ```

   字典条目中的值与 ECF 的数据类型相对应。 每个 ECF 的对象映射到各种类型之一。 大多数 ECF 使用适用于标准变量的简单类型。 下面的片段说明了有几种类型只涉及最少的处理：
    
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

   但文本值的查找表需要其他处理。 应用程序从服务检索相应的查找表，然后通过遍历查找表来输出 ECF 实例（包含单个或多个值）。 下面的代码段说明了对文本 ECF 的处理，其中包括使用简单值的 ECF 和使用查找表的 ECF： 
    
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

   此应用程序仅输出值；但也可以从数据值获取更多有意义的内容。
    
## <a name="listpwacustomfields"></a>ListPWACustomFields

ListPWACustomFields 方法检索并列出项目关联的 ECF。 此方法列出可与各个项目关联并已在 PWA 实例上注册的 ECF。 访问 ECF 的入口点使用项目上下文的 CustomFields 元素，如下面的查询请求所示：
  
```cs
// Project ECFs
    var allECFields = 
            projContext.LoadQuery(projContext.CustomFields.Include(
            qp => qp.InternalName,
            qp => qp.Name
        ));
    projContext.ExecuteQuery();

```

此方法不会查看项目是否使用特定 ECF。
  
## <a name="see-also"></a>另请参阅

- [Project 开发门户](https://developer.microsoft.com/zh-CN/project)
- [概述：企业自定义域和查找表](https://support.office.com/en-us/article/overview-enterprise-custom-fields-and-lookup-tables-f99db553-0b33-4648-93c0-f6a74637d790?ui=en-us&rs=en-us&ad=us)
- [本地和企业自定义域](https://msdn.microsoft.com/library/office/ms447495(v=office.14).aspx)
- [在 Project Server 2013 中添加或编辑企业自定义域](https://docs.microsoft.com/project/add-or-edit-enterprise-custom-fields-in-project-server)
    

