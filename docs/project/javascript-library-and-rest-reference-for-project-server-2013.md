---
title: Project Server 的 JavaScript 库和 REST 引用
manager: soliver
ms.date: 08/10/2016
ms.audience: Developer
localization_priority: Normal
ms.assetid: 67b47b8b-d34b-4fad-af49-0c258c345ad2
description: Project server 2013 的 javascript 库和 rest 参考包含有关 JavaScript 对象模型和用于访问 Project Server 功能的 REST 接口的信息。 您可以使用这些 api 为访问 project Server 2013 和 project Online 的非 Windows 设备开发跨浏览器 web 应用程序、Project Professional 2013 外接程序和应用程序。
ms.openlocfilehash: fb58de1e3858a39f42cc9a643a7394cec191a462
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358105"
---
# <a name="javascript-library-and-rest-reference-for-project-server"></a>Project Server 的 JavaScript 库和 REST 引用

Project server 2013 的 javascript 库和 rest 参考包含有关 JavaScript 对象模型和用于访问 Project Server 功能的 REST 接口的信息。 您可以使用这些 api 为访问 project Server 2013 和 project Online 的非 Windows 设备开发跨浏览器 web 应用程序、Project Professional 2013 外接程序和应用程序。
  
> [!NOTE]
> JavaScript 对象模型和 REST 接口与 Project Server 客户端对象模型 (CSOM) 相一致。 它们提供与 CSOM 中的**microsoft.projectserver.client**命名空间等效的功能。 
  
您可以通过 JavaScript 对象模型访问 Project Server 功能, 该模型是在`%ProgramFiles%\Common Files\Microsoft Shared\Web Server Extensions\15\TEMPLATE\LAYOUTS\PS.js`文件的[PS](https://msdn.microsoft.com/library/e3156167-a4fd-1bf6-8d1c-e180de1844ed%28Office.15%29.aspx)命名空间中定义的。 [PS](https://msdn.microsoft.com/library/e3156167-a4fd-1bf6-8d1c-e180de1844ed%28Office.15%29.aspx)命名空间中的[ProjectContext](https://msdn.microsoft.com/library/a490b675-a845-ee94-3877-b99ada9bf2b0%28Office.15%29.aspx)对象是 JavaScript 对象模型的入口点。 
  
> [!NOTE]
> 若要浏览 JavaScript 对象模型并帮助进行调试, 可以使用同一目录中的 .ps 文件。 为帮助在远程计算机上进行开发, [Project 2013 SDK 下载](https://www.microsoft.com/en-us/download/details.aspx?id=30435)包括 CSOM 的 .net Framework 程序集, 以及 .ps 和 .ps。 
  
您还可以通过 REST 界面访问 Project Server 功能。 REST 接口的入口点是**microsoft.projectserver.client**资源, 您可以使用`https://ServerName/pwaName/_api/ProjectServer`终结点 URI 对其进行访问。 例如, 以下查询将获取指定项目中的分配 (replace _ServerName_和_pwaName_, 并将 GUID 更改为与项目匹配)。
  
`https://ServerName/pwaName/_api/ProjectServer/Projects('263fc8d7-427c-e111-92fc-00155d3ba208')/Assignments`

**microsoft.projectserver.client**资源在[REST 接口的 microsoft.projectserver.client 资源](https://msdn.microsoft.com/library/a490b675-a845-ee94-3877-b99ada9bf2b0%28Office.15%29.aspx#bk_ProjectServerResources)中进行了介绍。 其他 REST 资源在本参考中对应的 JavaScript 对象和成员的文档中进行了介绍。 有关使用 REST 的详细信息, 请参阅[Project Server 的客户端对象模型 (CSOM)](client-side-object-model-csom-for-project-2013.md)和[使用 SharePoint 2013 REST 服务编程](https://msdn.microsoft.com/library/fp142385%28office.15%29.aspx)。
  
## <a name="javascript-library-and-rest-reference-for-project-server"></a>Project Server 的 JavaScript 库和 REST 引用
<a name="pj15_JavaScriptAPIReference_PS"> </a>

- [PS js JavaScript 库和 REST 参考](https://msdn.microsoft.com/library/5a140021-380a-d9e0-e36d-106df85f56d6%28Office.15%29.aspx)包含有关适用于 Project Server 2013 的 JavaScript 对象模型和 REST 接口的信息。 
    
## <a name="see-also"></a>另请参阅
<a name="bk_addresources"> </a>

- [Project 2013 开发人员文档](project-2013-developer-documentation.md)   
- [Project Server 的客户端对象模型 (CSOM)](client-side-object-model-csom-for-project-2013.md)   
- [JavaScript 对象模型入门](getting-started-with-the-project-server-2013-javascript-object-model.md)  
- [使用 JavaScript 对象模型处理项目](create-retrieve-update-delete-projects-using-project-server-javascript.md)
    

