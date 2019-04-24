---
title: 使用 SharePoint 对象模型成员
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 8cbafca3-7831-4231-8e61-38330b5ad61b
description: 在您可以通过运行在 InfoPath 表单模板中的代码针对 SharePoint 对象模型的成员进行编程之前，您必须在表单的 Visual Studio 2008 项目中引用 Microsoft.SharePoint.dll 程序集。为此，您必须具有对 Microsoft SharePoint Server 2010 的授权副本或运行 Microsoft SharePoint Foundation 2010 的服务器的文件系统的访问权限，这样您才能够获得 Microsoft.SharePoint.dll 程序集的副本。
ms.openlocfilehash: e29725450a6a1bdcba99215e337493f8686491e3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303589"
---
# <a name="use-sharepoint-object-model-members"></a>使用 SharePoint 对象模型成员

在您可以通过运行在 InfoPath 表单模板中的代码针对 SharePoint 对象模型的成员进行编程之前，您必须在表单的 Visual Studio 2008 项目中引用 Microsoft.SharePoint.dll 程序集。为此，您必须具有对 Microsoft SharePoint Server 2010 的授权副本或运行 Microsoft SharePoint Foundation 2010 的服务器的文件系统的访问权限，这样您才能够获得 Microsoft.SharePoint.dll 程序集的副本。 
  
此外，还必须将您的表单模板作为沙盒解决方案或经管理员核准的解决方案部署到服务器中。有关这些部署选项的详细信息，请参阅[发布包含代码的表单](publishing-forms-with-code.md)。
  
## <a name="add-and-reference-the-microsoftsharepoint-assembly-from-an-infopath-form-template"></a>从 InfoPath 表单模板中添加和引用 Microsoft.SharePoint 程序集

> [!IMPORTANT]
> 为了避免与 InfoPath 项目系统管理文件（即添加到表单模板中文件）的方式相冲突，请勿将要引用的任何程序集复制到表单模板项目的顶级文件夹中。默认情况下，其路径的格式如下：< *驱动器*  >:\Users\  *用户名*  \Documents\InfoPath Projects\  *项目名* > 如果确实要将所引用的程序集移动到项目文件夹内的某个位置，则必须在主 *项目名*  项目文件夹下创建一个子文件夹，然后从该子文件夹复制和引用程序集。但是请注意，为引用的程序集创建子文件夹不是必需的。只要引用的程序集不在项目的顶级文件夹内，InfoPath 项目系统就会在编译和发布项目时，将程序集复制到表单模板文件 (.xsn) 中。 
  
默认情况下，Microsoft.SharePoint.Server.dll 安装在 SharePoint Server 2010 或运行 SharePoint Foundation 2010 的服务器的文件系统中的 C:\Program Files\Common Files\Microsoft Shared\Web Server\Extensions\14\ISAPI 中。
  
### <a name="to-reference-the-microsoftsharepoint-assembly-from-an-infopath-forms-code-project"></a>从 InfoPath 表单的代码项目中引用 Microsoft.SharePoint 程序集

1. 将服务器上的 Microsoft.SharePoint.Server.dll 程序集复制到本地文件夹，或者获取从共享文件夹访问该程序集的权限。
    
2. 在 Visual Studio 2008 中打开表单模板项目。
    
3. 在“项目”**** 菜单上，单击“添加引用”****。
    
4. 单击“浏览”**** 选项卡，找到并指定程序集，再单击“确定”****，以添加引用。 
    
现在，您即可通过表单代码针对 SharePoint 对象模型的成员编写代码。为了使引用 Microsoft.SharePoint 命名空间的成员更加容易，请将  `using Microsoft.SharePoint;` 或  `Imports Microsoft.SharePoint` 添加到代码文件开始处的指令中。有关演示如何在 InfoPath 表单中使用 SharePoint 对象模型的成员的示例，请参阅 [示例沙盒解决方案](sample-sandboxed-solutions.md)中的"示例 2：使用 SharePoint 列表管理供应商"。

