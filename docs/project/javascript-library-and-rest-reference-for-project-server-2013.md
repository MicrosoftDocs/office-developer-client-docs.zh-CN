---
title: JavaScript 库和 Project server REST 参考
manager: soliver
ms.date: 08/10/2016
ms.audience: Developer
localization_priority: Normal
ms.assetid: 67b47b8b-d34b-4fad-af49-0c258c345ad2
description: JavaScript 库和 REST 引用的 Project Server 2013 包含有关 JavaScript 对象模型和 REST 接口用于访问 Project Server 功能的信息。 这些 Api 可用于开发跨浏览器的 web 应用程序、 Project Professional 2013 外接程序，和相关应用程序访问 Project Server 2013 和 Project Online 的非 Windows 设备。
ms.openlocfilehash: f834ffdc80de28eceb2d7ab9b30c1444b0478bd8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779436"
---
# <a name="javascript-library-and-rest-reference-for-project-server"></a>JavaScript 库和 Project server REST 参考

JavaScript 库和 REST 引用的 Project Server 2013 包含有关 JavaScript 对象模型和 REST 接口用于访问 Project Server 功能的信息。 这些 Api 可用于开发跨浏览器的 web 应用程序、 Project Professional 2013 外接程序，和相关应用程序访问 Project Server 2013 和 Project Online 的非 Windows 设备。
  
> [!NOTE]
> JavaScript 对象模型和 REST 接口与 Project Server 客户端对象模型 (CSOM) 对齐。 它们提供对**Microsoft.ProjectServer.Client**命名空间中 CSOM 的等效功能。 
  
您可以通过 JavaScript 对象模型中的[PS](http://msdn.microsoft.com/library/e3156167-a4fd-1bf6-8d1c-e180de1844ed%28Office.15%29.aspx)命名空间中定义访问 Project Server 功能`%ProgramFiles%\Common Files\Microsoft Shared\Web Server Extensions\15\TEMPLATE\LAYOUTS\PS.js`文件。 [PS](http://msdn.microsoft.com/library/e3156167-a4fd-1bf6-8d1c-e180de1844ed%28Office.15%29.aspx)命名空间中的[ProjectContext](http://msdn.microsoft.com/library/a490b675-a845-ee94-3877-b99ada9bf2b0%28Office.15%29.aspx)对象是对 JavaScript 对象模型的入口点。 
  
> [!NOTE]
> 若要浏览的 JavaScript 对象模型并帮助进行调试，您可以使用 PS.debug.js 文件位于同一目录中。 为了进行远程计算机上开发， [Project 2013 SDK 下载](https://www.microsoft.com/en-us/download/details.aspx?id=30435)包括.NET Framework 程序集 CSOM，以及所 PS.js 和 PS.debug.js 文件。 
  
您还可以通过 REST 界面访问 Project Server 功能。 REST 接口的入口点是**ProjectServer**资源，使用访问`http://ServerName/pwaName/_api/ProjectServer`终结点 URI。 例如，下面的查询指定项目中获取工作分配 （将_ServerName_和_pwaName_，并更改以匹配的项目的 GUID）。
  
`http://ServerName/pwaName/_api/ProjectServer/Projects('263fc8d7-427c-e111-92fc-00155d3ba208')/Assignments`

[在 REST 界面 ProjectServer 资源](http://msdn.microsoft.com/library/a490b675-a845-ee94-3877-b99ada9bf2b0%28Office.15%29.aspx#bk_ProjectServerResources)中介绍了**ProjectServer**资源。 其他 REST 资源的相应的 JavaScript 对象和成员本参考中的文档所述。 有关使用 REST 的详细信息，请参阅[Project server 的客户端对象模型 (CSOM)](client-side-object-model-csom-for-project-2013.md)和[编程使用 SharePoint 2013 REST 服务](http://msdn.microsoft.com/en-us/library/fp142385%28office.15%29.aspx)。
  
## <a name="javascript-library-and-rest-reference-for-project-server"></a>JavaScript 库和 Project server REST 参考
<a name="pj15_JavaScriptAPIReference_PS"> </a>

- [PS.js JavaScript 库和 REST 参考](http://msdn.microsoft.com/library/5a140021-380a-d9e0-e36d-106df85f56d6%28Office.15%29.aspx)包含有关 JavaScript 对象模型和 REST 接口的 Project Server 2013 的信息。 
    
## <a name="see-also"></a>另请参阅
<a name="bk_addresources"> </a>

- [Project 2013 开发人员文档](project-2013-developer-documentation.md)   
- [Project Server 的客户端对象模型 (CSOM)](client-side-object-model-csom-for-project-2013.md)   
- [JavaScript 对象模型入门](getting-started-with-the-project-server-2013-javascript-object-model.md)  
- [使用 JavaScript 对象模型处理项目](create-retrieve-update-delete-projects-using-project-server-javascript.md)
    

