---
title: Project Online 从入门到精通
manager: soliver
ms.date: 11/08/2016
ms.audience: Developer
localization_priority: Normal
ms.assetid: 5b48958e-6dab-4121-871f-fb15f58f1b24
description: 应用程序开发人员可以使用独立Project Online和/ (SharePoint加载项) 托管的网站Project网站集。大量的应用程序可能涵盖从满足项目中涉及的这些应用程序的需求到 PMO 支持功能，例如以下任一功能：
ms.openlocfilehash: 00f79b05b886bfd2c54c118245e22f10bb5451bf
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32344406"
---
# <a name="from-0-to-60-with-project-online"></a>Project Online 从入门到精通

应用程序开发人员可以使用独立Project Online和/ (SharePoint加载项) 托管的网站Project网站集。大量的应用程序可能涵盖从满足项目中涉及的这些应用程序的需求到 PMO 支持功能，例如以下任一功能：
  
- 简化工作人员的时间卡数据输入
- 高效的主管时间卡审批
- 监督许可证 (采购和) 项目所需的状态
- 活动项目的状态/运行状况检查
- 问题报告
- 更改管理状态报告
    
Project Online API 支持以适应以下方案：
  
- 对于Project (SharePoint) 加载项：
    
  - 托管 (Online) JavaScript、HTML、CSS SharePoint 代码
  - 下载到浏览器并针对 SharePoint Online 执行的资产。  
  - JavaScript 中的业务逻辑   
  - 访问存储在数据存储区或Project Online SharePoint数据 (但不限于) ：  
  - 自定义域  
  - 列表
    
- 对于Project (SharePoint) 托管的外接程序：
    
  - 存在于网站外部的网站上Project Online代码 
  - 外部网站，可以 (但不限于) ：  
  - 另SharePoint网站  
  - 在任何平台上构建的 Web 应用/服务  
  - 外部网站包含业务逻辑  
  - 浏览器将Project Online访问令牌重定向到外部Project Online  
  - 外部网站可以调用 SharePoint 和 Project Online
    
- 对于外部/独立外接程序：
    
  - 用户在设备上执行应用程序
  - 应用程序直接对 api Project Online进行身份验证和调用
    

|应用程序类型|API 实现|目标环境|应用程序示例|
|:-----|:-----|:-----|:-----|
|Project托管  <br/> |JSOM (Java脚本对象模型)   <br/> REST  <br/> |浏览器  <br/> |考勤卡条目  <br/> Timecard approval  <br/> 项目状态  <br/> 问题报告  <br/> |
|Project提供程序托管  <br/> |CSOM 客户端库  <br/> |Azure 网站/应用  <br/> 非Windows环境 (LAMP 等)   <br/> |外部时间表验证程序  <br/> Project导入程序  <br/> |
|外部/独立  <br/> |REST  <br/> CSOM  <br/> |REST - 任何平台  <br/> CSOM - 任何 .NET 支持的平台  <br/> |考勤卡条目  <br/> 将项目迁移到新网站  <br/> 更改管理状态。  <br/> |
   
## <a name="what-does-it-take-to-start-developing-applications-for-project-online"></a>开始为应用程序开发应用程序需要哪些Project Online？

开发应用程序所需的常见项目Project Online帐户和测试数据Project Online包括工作分配、任务、资源和自定义域的项目及项目相关信息。 还需要开发环境，但开发环境的具体内容取决于应用程序的类型和应用程序所需的 API 接口。 接下来的几节介绍了三个 API 接口的开发需求。
  
参考文档介绍了这三个接口通用的对象模型，以及显示对象模型组件之间的关系的实体映射。
  
## <a name="project-hosted-add-in-development-environment"></a>Project托管的外接程序开发环境

托管加载项是驻留在服务器上并下载到浏览器进行运行时执行的加载项。 托管加载项可以使用 JSOM 或 REST 接口，并且使用 JavaScript 编写。 Project Online为运行时执行提供对 JSOM 库的引用。 假设开发在Windows上，则所需的资源如下：
  
- Visual Studio 2015 (首选) 或 Visual Studio 2013
    
- Office开发工具Visual Studio
    
- JavaScript 语言
    
有关 https://github.com/OfficeDev/Project-JSOM-Copy-Work-Packages 示例应用程序，请访问 。 
  
可以通过几个简单的步骤下载并运行示例：
  
1. 下载并打开示例应用程序
    
2. 在"属性"窗口中更新 SiteURL
    
   Project Online检查加载项的应用程序范围以及管理对加载项主机上信息的访问Project Online权限。 如果在任一设置或两种设置中都明确拒绝访问，Project Online拒绝访问该信息。 否则，将授予访问权限。
    
3. 在你的 [网站上启用](https://docs.microsoft.com/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins) 旁加载。  
    
4. 生成项目。
    
5. 运行项目。
    
## <a name="project-provider-hosted-add-in-development-environment"></a>Project提供程序托管的外接程序开发环境

提供程序托管的外接程序是在任何 Web 平台上编写和驻留的应用程序。 他们可以使用适用于 Microsoft 平台和 API 的 REST (CSOM 连接并执行) 操作。 支持 REST 接口的任何语言和环境都可用于开发。 
  
此类型的Windows开发环境的示例包括以下项目：
  
-  Visual Studio 2015 (首选) 或 Visual Studio 2013 
    
- Microsoft OfficeVisual Studio (2015 Visual Studio 2015 Professional 和 Enterprise 版本) 
    
- .NET Framework 4.0 或更高版本
    
- [用于 CSOM 调用 (SharePointOnline](https://www.nuget.org/packages/Microsoft.SharePointOnline.CSOM) CSOM)  
    
- 编程语言，如 C# 
    
请访问 https://github.com/OfficeDev/Project-Add-in-REST-BasicDataOperations ，以使用示例脚本。 
  
可以通过几个步骤运行示例：
  
1. 下载并打开示例应用程序
    
2. 在"属性"窗口中更新 SiteURL
    
   Project Online检查加载项的应用程序范围以及管理对加载项主机上信息的访问Project Online权限。 如果在任一设置或两种设置中都明确拒绝访问，Project Online拒绝访问该信息。 否则，将授予访问权限。
    
3. 在你的 [网站上启用](https://docs.microsoft.com/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins) 旁加载。 
    
4. 生成项目。
    
5. 运行项目。
    
## <a name="externalstandalone-application-development-environment"></a>外部/独立应用程序开发环境

独立应用程序可以使用客户端对象模型 (CSOM) 或 REST 调用 Project Online 以与 Project Online 通信，以创建、检索、更新和删除驻留在服务器上的信息。 这是一个独立的客户端应用程序，它依赖于要运行的用户访问级别。 
  
此类型的Windows开发环境的示例包括以下项目：
  
- Visual Studio 2015 (首选) 或 Visual Studio 2013 
    
- Microsoft OfficeVisual Studio (2015 Visual Studio 2015 Professional 和 Enterprise 版本) 
    
- .NET Framework 4.0 或更高版本
    
- [用于 CSOM 调用 (SharePointOnline](https://www.nuget.org/packages/Microsoft.SharePointOnline.CSOM) CSOM)  
    
- 编程语言，如 C# 
    
有关 https://github.com/OfficeDev/Project-CSOM-Read-Enterprise-CustomFields 示例应用程序，请访问 。 
  
可以通过几个步骤运行示例：
  
1. 下载示例应用程序
    
2. 进行一些更改以访问Project Online网站- 网站名称、用户帐户和密码。
    
   确保用户有权访问所有项目。 Project Online使用用户权限来管理对数据存储中信息的访问。
    
3. 使用SharePoint Nuget 程序包管理器控制台（通过在 Nuget 控制台中键入以下内容从"工具"菜单提供）将程序集添加到引用中： 
    
   `Install-Package Microsoft.SharePointOnline.CSOM`

4. 生成项目。
    
5. 运行项目。
    
## <a name="next-steps"></a>后续步骤

每个示例应用程序都有一篇文章，解释使用单个应用程序 API 的Project点。 这些文章显示在以下列表中，以及介绍实体关系、查询系统信息和访问自定义字段的一些文章。 
  
- [使用Project Online对象模型开发应用程序](developing-a-project-online-application-using-the-client-side-object-model.md)
    
- [使用 JAVAScript Project Online JSOM 模型开发 (加载项) ](developing-a-project-online-add-in-using-the-javascript-object-model-jsom.md)
    
- [访问 Project Online 企业自定义字段](accessing-project-online-enterprise-custom-fields.md)
    
## <a name="see-also"></a>另请参阅

有关 Project Online 和使用 CSOM 进行应用程序开发的文档和示例，请参阅 [Project 开发门户](https://developer.microsoft.com/en-us/project)。
    

