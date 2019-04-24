---
title: Project Online 从入门到精通
manager: soliver
ms.date: 11/08/2016
ms.audience: Developer
localization_priority: Normal
ms.assetid: 5b48958e-6dab-4121-871f-fb15f58f1b24
description: '应用程序开发人员可以使用独立应用程序和/或项目加载项自定义 Project Online 网站 (SharePoint 托管)。可以使用大量的应用程序, 包括项目中涉及到 PMO 支持功能的需求, 如以下任何一项:'
ms.openlocfilehash: 00f79b05b886bfd2c54c118245e22f10bb5451bf
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32344406"
---
# <a name="from-0-to-60-with-project-online"></a>Project Online 从入门到精通

应用程序开发人员可以使用独立应用程序和/或项目加载项自定义 Project Online 网站 (SharePoint 托管)。可以使用大量的应用程序, 包括项目中涉及到 PMO 支持功能的需求, 如以下任何一项:
  
- 工作人员的简化工时记录卡数据输入
- 有效工时记录卡审批主管
- 项目所需的允许 (采购和状态) 监督
- 活动项目的状态/运行状况检查
- 问题报告
- 更改管理状态报告
    
Project Online 包括 API 支持, 以适应以下方案:
  
- 对于项目 (SharePoint) 托管外接程序:
    
  - SharePoint Online 中托管的代码 (JavaScript、HTML、CSS)
  - 下载到浏览器中并对 SharePoint Online 执行的资产。  
  - JavaScript 中的业务逻辑   
  - 在 Project Online 或 SharePoint 中访问/存储的数据, 例如 (但不限于):  
  - Custom fields  
  - 列表
    
- 对于项目 (SharePoint) 提供程序托管的外接程序:
    
  - 在 Project Online 网站外部的网站上存在的代码 
  - 外部网站, 可以 (但不限于):  
  - 另一个 SharePoint 网站  
  - 在任何平台上构建的 Web 应用/服务  
  - 外部网站包含业务逻辑  
  - 浏览器从 project online 重定向到外部网站, 并具有对 Project online 的访问令牌  
  - 外部网站可以对 SharePoint 和 Project Online 进行调用
    
- 对于外部/独立外接程序:
    
  - 用户在其设备上执行应用程序
  - 应用程序直接对 Project Online api 进行身份验证和调用
    

|应用程序类型|API 实现|目标环境|应用程序示例|
|:-----|:-----|:-----|:-----|
|托管项目  <br/> |JSOM (Java 脚本对象模型)  <br/> REST  <br/> |Browser  <br/> |工时记录卡条目  <br/> 工时记录卡审核  <br/> 项目状态  <br/> 问题报告  <br/> |
|项目提供程序托管  <br/> |CSOM 客户端库  <br/> |Azure 网站/应用  <br/> 非 Windows 环境 (灯等)  <br/> |外部时间表验证程序  <br/> 项目导入程序  <br/> |
|外部/独立  <br/> |REST  <br/> CSOM  <br/> |REST-任意平台  <br/> CSOM-任何 .net 支持的平台  <br/> |工时记录卡条目  <br/> 将项目迁移到新网站  <br/> 更改管理状态。  <br/> |
   
## <a name="what-does-it-take-to-start-developing-applications-for-project-online"></a>开始开发 Project Online 应用程序需要执行哪些操作？

开发 project online 应用程序所需的常见项目是 project online 帐户和测试数据, 包括工作分配、任务、资源和自定义字段的项目和项目相关信息。 开发环境也是必需的, 但开发环境的具体情况取决于应用程序所需的应用程序和 API 接口的类型。 接下来的几节介绍了三个 API 接口的开发需求。
  
参考文档介绍了所有三个接口通用的对象模型, 以及显示对象模型组件之间关系的实体映射。
  
## <a name="project-hosted-add-in-development-environment"></a>项目托管的加载项开发环境

托管加载项是驻留在服务器上并下载到浏览器以进行运行时执行的外接程序。 托管的外接程序可以使用 JSOM 或 REST 接口, 并在 JavaScript 中编写。 Project Online 为运行时执行提供对 JSOM 库的引用。 假定开发在 Windows 平台上, 则需要执行以下资源:
  
- visual studio 2015 (首选) 或 visual studio 2013
    
- 适用于 Visual Studio 的 Office 开发工具
    
- JavaScript 语言
    
请https://github.com/OfficeDev/Project-JSOM-Copy-Work-Packages访问示例应用程序。 
  
您可以通过几个简单的步骤下载并运行示例:
  
1. 下载并打开示例应用程序
    
2. 在 "属性" 窗口中更新 SiteURL
    
   project online 将检查外接程序的应用程序范围和用户权限以管理对 Project Online 主机上的信息的访问权限。 如果在一个或两个设置中明确拒绝访问, Project Online 将拒绝对信息的访问。 否则, 将授予访问权限。
    
3. 在您的网站上启用[旁加载](https://docs.microsoft.com/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)。  
    
4. 生成项目。
    
5. 运行项目。
    
## <a name="project-provider-hosted-add-in-development-environment"></a>项目提供程序托管的外接程序开发环境

提供程序托管的外接程序是编写并驻留在任何 web 平台上的应用程序。 他们可以使用 REST (或 CSOM for Microsoft 平台) API 连接和执行数据操作。 支持 REST 接口的任何语言和环境都可用于开发。 
  
此类应用程序的 Windows 开发环境示例包括以下各项:
  
-  visual studio 2015 (首选) 或 visual studio 2013 
    
- 适用于 visual studio 的 Microsoft Office 开发工具 (由 visual studio 2015 Professional 和 Enterprise edition 提供)
    
- .net Framework 4.0 或更高版本
    
- [SharePointOnline CSOM 程序包](https://www.nuget.org/packages/Microsoft.SharePointOnline.CSOM)(对于 CSOM 呼叫) 
    
- 一种编程语言, 例如 c # 
    
访问https://github.com/OfficeDev/Project-Add-in-REST-BasicDataOperations以获取工作示例脚本。 
  
您可以通过以下几个步骤来运行该示例:
  
1. 下载并打开示例应用程序
    
2. 在 "属性" 窗口中更新 SiteURL
    
   project online 将检查外接程序的应用程序范围和用户权限以管理对 Project Online 主机上的信息的访问权限。 如果在一个或两个设置中明确拒绝访问, Project Online 将拒绝对信息的访问。 否则, 将授予访问权限。
    
3. 在您的网站上启用[旁加载](https://docs.microsoft.com/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)。 
    
4. 生成项目。
    
5. 运行项目。
    
## <a name="externalstandalone-application-development-environment"></a>外部/独立应用程序开发环境

独立应用程序可以使用客户端对象模型 (CSOM) 或 REST 与 project online 进行通信以创建、检索、更新和删除服务器上的信息, 从而调用 project online。 这是一个独立的客户端应用程序, 它依赖于要运行的用户访问级别。 
  
此类应用程序的 Windows 开发环境示例包括以下各项:
  
- visual studio 2015 (首选) 或 visual studio 2013 
    
- 适用于 visual studio 的 Microsoft Office 开发工具 (由 visual studio 2015 Professional 和 Enterprise edition 提供)
    
- .net Framework 4.0 或更高版本
    
- [SharePointOnline CSOM 程序包](https://www.nuget.org/packages/Microsoft.SharePointOnline.CSOM)(对于 CSOM 呼叫) 
    
- 一种编程语言, 例如 c # 
    
请https://github.com/OfficeDev/Project-CSOM-Read-Enterprise-CustomFields访问示例应用程序。 
  
您可以通过以下几个步骤来运行该示例:
  
1. 下载示例应用程序
    
2. 进行几处更改, 以访问 Project Online 网站 (网站名称、用户帐户和密码)。
    
   确保用户有权访问所有项目。 Project Online 使用用户权限来管理对数据存储区中的信息的访问。
    
3. 通过在 nuget 控制台中键入以下内容, 使用 nuget 包管理器控制台将 SharePoint 程序集添加到引用中, 可从 "工具" 菜单中进行以下操作: 
    
   `Install-Package Microsoft.SharePointOnline.CSOM`

4. 生成项目。
    
5. 运行项目。
    
## <a name="next-steps"></a>后续步骤

每个示例应用程序都有一篇文章, 其中介绍了使用单个项目 API 的重点。 这些文章将显示在以下列表中, 以及一些描述实体关系、查询系统上的信息以及访问自定义字段的文章。 
  
- [使用客户端对象模型开发 Project Online 应用程序](developing-a-project-online-application-using-the-client-side-object-model.md)
    
- [使用 JavaScript 对象模型 (JSOM) 开发 Project Online 外接](developing-a-project-online-add-in-using-the-javascript-object-model-jsom.md)
    
- [访问 Project Online 企业自定义字段](accessing-project-online-enterprise-custom-fields.md)
    
## <a name="see-also"></a>另请参阅

有关 Project Online 和使用 CSOM 进行应用程序开发的文档和示例，请参阅 [Project 开发门户](https://developer.microsoft.com/en-us/project)。
    

