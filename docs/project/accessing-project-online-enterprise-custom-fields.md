---
title: 访问 Project Online 企业自定义字段
manager: soliver
ms.date: 11/08/2016
ms.audience: Developer
localization_priority: Normal
ms.assetid: 25509631-fa14-49d8-b594-cfacf5355c38
description: Project Online 是 Office 365 服务，公司可以扩展以满足业务需求。 一个扩展区域是企业自定义域 (ECFs)。 ECFs 不可以添加到项目、 资源和任务的类型的值字段。 下表列出了将与项目、 资源和任务相关联的 ECFs，并为该 ECF 实例提供值的示例：
ms.openlocfilehash: d6c8f97ffc887b33e5d81af8e463cf10502845dd
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779421"
---
# <a name="accessing-project-online-enterprise-custom-fields"></a>访问 Project Online 企业自定义字段

Project Online 是 Office 365 服务，公司可以扩展以满足业务需求。 一个扩展区域是企业自定义域 (ECFs)。 ECFs 不可以添加到项目、 资源和任务的类型的值字段。 下表列出了将与项目、 资源和任务相关联的 ECFs，并为该 ECF 实例提供值的示例：
  
|ECF 名称|ECF 类型|Association|示例值|
|:-----|:-----|:-----|:-----|
|字距调整  <br/> |TEXT  <br/> |Project  <br/> |最终用户可以记录重要统计信息和运行状况数据，包括运行状况评估和个性化的操作的结果达到更好的运行状况的计划。  <br/> |
|风险评估  <br/> |TEXT  <br/> |Project  <br/> |Low  <br/> |
|投资回报  <br/> |号码  <br/> |Project  <br/> |2.10  <br/> |
|总成本  <br/> |成本  <br/> |Project  <br/> |$ 1,031,514  <br/> |
|启动团队  <br/> |TEXT  <br/> |Resources  <br/> |是  <br/> |
|位置角色  <br/> |TEXT  <br/> |Resources  <br/> |测试人员  <br/> |
|标记状态  <br/> |标志  <br/> |Task  <br/> |否  <br/> |
|运行状况  <br/> |TEXT  <br/> |Task  <br/> |未指定  <br/> |
   
ECFs 中定义的任何项目、 资源或任务从外部的 Project Web 应用程序 (PWA) 实例。 尚未，他们可以成为与项目、 资源或任务关联。 本文提供介绍性检查使用示例应用程序的自定义字段，并重点介绍检索 ECF 值。 
  
您可以下载完整的示例在https://github.com/OfficeDev/Project-CSOM-Read-Enterprise-CustomFields。
  
此外，Project Online 支持本地自定义域作为只读实体特定于特定项目、 资源或任务。 本地自定义域的详细信息，请参阅 sample https://github.com/OfficeDev/Project-CSOM-Read-Local-CustomFields\。
  
## <a name="background-materials"></a>背景材料

[开发 Project Online 应用程序使用的客户端对象模型](developing-a-project-online-application-using-the-client-side-object-model.md)，上一篇文章提供了背景和开发应用程序使用 CSOM 的初始方向。 请参阅本文的以下各项：
  
- 有关项目，独立和基于云的版本的背景信息 
    
- 开发环境 （Visual Studio 版本和软件库）
    
- Visual Studio 项目安装.NET 应用程序使用 CSOM 库
    
- 连接到 Project Online 服务
    
## <a name="preliminaries-class-level-declarations"></a>准备事项 （类级别声明）

此应用程序的类定义两个数据项： 项目上下文和 pwaECF 词典。
  
项目上下文对象属于 Project CSOM，并将连接的应用程序和 PWA 实例。 所有服务请求使用项目上下文。
  
```cs
private static ProjectContext projContext = 
     new ProjectContext("https://Contoso216.sharepoint.com/sites/pwa");

```

上下文需要应用程序中创建实例的连接终结点。 连接终结点是 PWA 实例的 URL。 
  
PwaECF 词典存储 ECFs PWA 级别定义的项目。 该词典使用 ECF。InternalName 作为键和值的 CustomField 对象。 字典是在 ListPWACustomFields 方法中，填充，然后用作在 Main 方法中的引用。 
  
```cs
    //Dictionary of ECFs
        static Dictionary<String, CustomField> pwaECF = new Dictionary<string, CustomField>();

```

## <a name="main-method"></a>Main 方法

Main 方法中管理应用程序流。 为与其他应用程序使用 Project Online CSOM，Main 初始化项目上下文。 
  
1. 检索和列表中 Project Online PWA ECFs。
    
   在 ListPWACustomFields 方法实现此功能。
    
2. 检索与自定义域和非自定义域的项目。
    
   当检索具有 ECFs 项目，对 Project Online 服务的查询请求需要包括以下各项： 
    
   - **IncludeCustomFields**&ndash;此项目请求返回的每个已发布的项目，包括支持自定义域的扩展的 PublishedProjects 集合的服务。 指定此项，则除非 Project Online 返回不包括自定义字段数据的 PublishedProject 对象。
    
   - **IncludeCustomFields.CustomFields** &ndash;此项请求服务来填充 CustomFields 数据 PublishedProject 对象。
    
   以下请求指定项目 Id 和名称，以及自定义字段的对象扩展和自定义字段值。
    
   ```cs
        var projBlk = projContext.LoadQuery(
        projContext.Projects.Include(
            p => p.Id, 
            p => p.Name,
            p => p.IncludeCustomFields,
            p => p.IncludeCustomFields.CustomFields
        ));
    
   ```

3. 检查每个项目。
    
   使用此应用程序中的项目对象是 PublishedProject 类型，因为检索并显示值。 
    
   如果您需要更新一个或多个项目中的数据值，正在更新项目将签出和应用程序将使用 DraftProject 对象来检索的值并更新项目。
    
4. 访问 project ECF 条目
    
   每个 ECF 实例分离开来的其余 ECF 信息的字段值。 字段值的键/值对的一部分存储。 其余的信息存储在 CustomField 对象。
    
   访问项目中的 ECF 值由两部分组成：
    
   - 循环 CustomFields 集合
    
   - 访问使用两个构造的相应项。
    
   每个项目存储在两个位置，可枚举的 CustomFields 集关联的 ECF 条目和键/值对的一部分的字段值。 在键/值对，internalName 是密钥和字段值为值。 使用字典保留和访问的字段值。 
    
   ECF 属性，之外的字段值，存储在 CustomField 对象，每个项目的一个对象。 使用 CustomFields 集合可访问 ECFs 单个项目相关联。 
    
5. 每个项目存储相关联的 ECFs 其中每个 ECF 项包含的密钥-ECF-和保存的 ECF 值的对象的内部名称集合中。 传输到字典访问各项的集合。 声明如下。
    
   ```cs
    Dictionary<string, object> projDict = pubProj.IncludeCustomFields.FieldValues;
    
   ```

   词典条目中的值对应于 ECF 的数据类型。 每个 ECF 的对象映射到各种类型之一。 大多数 ECFs 使用纳入标准变量的简单类型。 以下片段显示了最少的处理所涉及的几种类型：
    
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

   查阅表格的文本值，但是，需要进行其他处理。 应用程序从该服务，检索适当的查阅表格，并通过遍历查阅表格输出 ECF 实例 （与单个或多个值）。 下面的代码段显示的文本 ECFs，其中包括与简单值以及那些使用查阅表格的处理： 
    
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

   此应用程序只需输出值;但是，就可以获得的数据值的更多的含义。
    
## <a name="listpwacustomfields"></a>ListPWACustomFields

ListPWACustomFields 方法检索并列出 ECFs 与项目关联。 此方法列出了可与各个项目相关联的 PWA 实例上注册 ECFs。 用于访问 ECFs 的入口点使用 CustomFields 元素的项目上下文，如下面的查询请求中所示：
  
```cs
// Project ECFs
    var allECFields = 
            projContext.LoadQuery(projContext.CustomFields.Include(
            qp => qp.InternalName,
            qp => qp.Name
        ));
    projContext.ExecuteQuery();

```

该方法不会检查项目是否使用特定 ECF。
  
## <a name="see-also"></a>另请参阅

- [项目开发门户](http://dev.office.com/project.aspx)
- [概述： 企业自定义域和查阅表格](https://support.office.com/en-us/article/overview-enterprise-custom-fields-and-lookup-tables-f99db553-0b33-4648-93c0-f6a74637d790?ui=en-us&rs=en-us&ad=us)
- [本地和企业自定义域](https://msdn.microsoft.com/en-us/library/office/ms447495(v=office.14).aspx)
- [添加或编辑 Project Server 2013 中的企业自定义域](https://docs.microsoft.com/en-us/project/add-or-edit-enterprise-custom-fields-in-project-server)
    

