---
title: Project Online 从入门到精通
manager: soliver
ms.date: 11/08/2016
ms.audience: Developer
localization_priority: Normal
ms.assetid: 5b48958e-6dab-4121-871f-fb15f58f1b24
description: 应用程序开发人员可以自定义 Project Online 承载的网站 （SharePoint） 使用独立应用程序和/或项目外接程序。丰富的应用程序是可能的范围从寻址的那些参与一个项目到 PMO 支持功能，如以下任一需求：
ms.openlocfilehash: 25a38a7c7359020058983e271067a87da29f1b3d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594528"
---
# <a name="from-0-to-60-with-project-online"></a>Project Online 从入门到精通

应用程序开发人员可以自定义 Project Online 承载的网站 （SharePoint） 使用独立应用程序和/或项目外接程序。丰富的应用程序是可能的范围从寻址的那些参与一个项目到 PMO 支持功能，如以下任一需求：
  
- 简化考勤卡工作者的数据输入
- 高效考勤卡审批的主管
- 允许 （采购和状态） 所需的项目的监督
- 活动项目的状态/状况检查
- 问题报告
- 更改管理状态报告
    
Project Online 包括 API 支持以适应以下方案：
  
- 为项目 (SharePoint) 托管外接程序：
    
  - SharePoint Online 中托管的代码 （JavaScript、 HTML、 CSS）
  - 下载到浏览器并执行针对 SharePoint Online 的资产。  
  - JavaScript 中的业务逻辑   
  - 访问数据的是在/存储在 Project Online 或 SharePoint 如 （但不限于）：  
  - 自定义域  
  - 列表
    
- 为项目 (SharePoint) 提供商托管外接程序：
    
  - Project Online 站点的外部网站上的代码 
  - 外部网站，它可以是 （但不限于）：  
  - 其他 SharePoint 网站  
  - 在任何平台上构建的 web 应用程序/服务  
  - 外部网站包含业务逻辑  
  - 将浏览器重定向从 Project Online 到具有访问令牌到 Project Online 的外部网站  
  - 对外部网站可以发出呼叫到 SharePoint 和 Project Online
    
- 对于外部/独立外接程序：
    
  - 用户在其设备上执行应用程序
  - 应用程序进行身份验证，并直接调用 Project Online Api
    

|应用程序类型|API 实现|目标环境|应用程序示例|
|:-----|:-----|:-----|:-----|
|托管项目  <br/> |JSOM （Java Script 对象模型）  <br/> REST  <br/> |浏览器  <br/> |考勤卡条目  <br/> 考勤卡审批  <br/> 项目状态  <br/> 问题报告  <br/> |
|项目提供程序承载  <br/> |CSOM 客户端库  <br/> |Azure 网站/应用程序  <br/> 非 Windows 环境 （LAMP 等）  <br/> |外部时间表验证程序  <br/> 项目导入程序  <br/> |
|外部/独立  <br/> |REST  <br/> CSOM  <br/> |REST-任何平台  <br/> CSOM 的任何支持的.NET 平台  <br/> |考勤卡条目  <br/> 向新网站的项目的迁移  <br/> 管理状态更改。  <br/> |
   
## <a name="what-does-it-take-to-start-developing-applications-for-project-online"></a>开始开发 for Project Online 中的应用程序需要什么？

所需的开发 Project Online 的应用程序的常见项的 Project Online 的帐户和测试数据-项目和项目相关的信息，包括分配、 任务、 资源和自定义字段。 开发环境所需以及，但开发环境具体情况取决于应用程序和应用程序所需的 API 接口的类型。 下面几节介绍的三个 API 接口的开发需求。
  
参考文档描述的所有三个接口，以及实体映射显示对象模型组件之间的关系的情况很常见的对象模型。
  
## <a name="project-hosted-add-in-development-environment"></a>Project 托管外接程序开发环境

托管加载项是外接程序驻留在服务器上，下载到浏览器中的运行时执行。 托管加载项可以使用 JSOM 或 REST 接口和 JavaScript 中写入。 Project Online 的运行时执行提供对 JSOM 库的引用。 假定开发与在 Windows 平台上，按所需的资源：
  
- Visual Studio 2015 （首选） 或 Visual Studio 2013
    
- Visual Studio 的 office 开发工具
    
- JavaScript 语言
    
请访问https://github.com/OfficeDev/Project-JSOM-Copy-Work-Packages示例应用程序。 
  
您可以下载并运行该示例中一些简单的步骤：
  
1. 下载并打开示例应用程序
    
2. 更新属性窗口中的 siteurl 属性
    
   Project Online 检查外接程序和管理访问的 Project Online 主机上的信息的用户权限的应用程序范围。 如果访问明确拒绝中任意一种或两个设置，Project Online 拒绝访问的信息。 否则，授予访问权限。
    
3. 启用[sideloading](https://docs.microsoft.com/en-us/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)网站上。  
    
4. 生成项目。
    
5. 运行项目。
    
## <a name="project-provider-hosted-add-in-development-environment"></a>项目提供托管外接程序开发环境

提供程序承载的加载项是编写的应用程序和驻留在任何 web 平台上。 他们可以连接并执行数据操作使用 REST （或 Microsoft 平台的 CSOM） API。 任何语言和环境支持 REST 接口的可用于开发。 
  
这种应用程序的 Windows 开发环境的示例包括以下各项：
  
-  Visual Studio 2015 （首选） 或 Visual Studio 2013 
    
- Visual Studio （提供与 Visual Studio 2015 专业版和企业版） 的 Microsoft Office 开发工具
    
- .NET framework 4.0 或更高版本
    
- [SharePointOnline CSOM 包](https://www.nuget.org/packages/Microsoft.SharePointOnline.CSOM)（对于 CSOM 调用） 
    
- 编程语言，例如，C# 
    
请访问https://github.com/OfficeDev/Project-Add-in-REST-BasicDataOperations的示例脚本。 
  
您可以运行该示例在几个步骤：
  
1. 下载并打开示例应用程序
    
2. 更新属性窗口中的 siteurl 属性
    
   Project Online 检查外接程序和管理访问的 Project Online 主机上的信息的用户权限的应用程序范围。 如果访问明确拒绝中任意一种或两个设置，Project Online 拒绝访问的信息。 否则，授予访问权限。
    
3. 启用[sideloading](https://docs.microsoft.com/en-us/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)网站上。 
    
4. 生成项目。
    
5. 运行项目。
    
## <a name="externalstandalone-application-development-environment"></a>外部/独立应用程序开发环境

独立的应用程序可以呼叫 Project Online 中使用的客户端对象模型 (CSOM) 或 REST 进行通信与 Project Online 中创建、 检索、 更新和删除驻留在服务器上的信息。 这是取决于用户的访问级别，以运行独立客户端应用程序。 
  
这种应用程序的 Windows 开发环境的示例包括以下各项：
  
- Visual Studio 2015 （首选） 或 Visual Studio 2013 
    
- Visual Studio （提供与 Visual Studio 2015 专业版和企业版） 的 Microsoft Office 开发工具
    
- .NET framework 4.0 或更高版本
    
- [SharePointOnline CSOM 包](https://www.nuget.org/packages/Microsoft.SharePointOnline.CSOM)（对于 CSOM 调用） 
    
- 编程语言，例如，C# 
    
请访问https://github.com/OfficeDev/Project-CSOM-Read-Enterprise-CustomFields示例应用程序。 
  
您可以运行该示例在几个步骤：
  
1. 下载示例应用程序
    
2. 进行几个更改以访问 Project Online 网站 — 站点名称、 用户帐户和密码。
    
   确保用户有权访问所有项目。 Project Online 使用用户权限来控制对数据存储中的信息的访问。
    
3. 将 SharePoint 程序集添加到使用 Nuget 程序包管理器控制台，可从工具菜单下 Nuget 控制台中键入以下内容的引用： 
    
   `Install-Package Microsoft.SharePointOnline.CSOM`

4. 生成项目。
    
5. 运行项目。
    
## <a name="next-steps"></a>后续步骤

每个示例应用程序具有文章介绍使用单个项目 API 的要点。 文章将显示以下列表中，一些文章的描述的实体关系，以及查询系统，并在访问自定义字段的信息。 
  
- [开发 Project Online 应用程序使用的客户端对象模型](developing-a-project-online-application-using-the-client-side-object-model.md)
    
- [开发的 Project Online 外接程序使用 JavaScript 对象模型 (JSOM)](developing-a-project-online-add-in-using-the-javascript-object-model-jsom.md)
    
- [访问 Project Online 企业自定义字段](accessing-project-online-enterprise-custom-fields.md)
    
## <a name="see-also"></a>另请参阅

有关文档和与 Project Online 和使用 CSOM 的应用程序开发相关的示例，请参阅[Project 开发门户](https://developer.microsoft.com/en-us/project)。
    

