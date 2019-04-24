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
# <a name="javascript-library-and-rest-reference-for-project-server"></a><span data-ttu-id="42486-104">Project Server 的 JavaScript 库和 REST 引用</span><span class="sxs-lookup"><span data-stu-id="42486-104">JavaScript library and REST reference for Project Server</span></span>

<span data-ttu-id="42486-105">Project server 2013 的 javascript 库和 rest 参考包含有关 JavaScript 对象模型和用于访问 Project Server 功能的 REST 接口的信息。</span><span class="sxs-lookup"><span data-stu-id="42486-105">The JavaScript library and REST reference for Project Server 2013 contains information about the JavaScript object model and the REST interface that you use to access Project Server functionality.</span></span> <span data-ttu-id="42486-106">您可以使用这些 api 为访问 project Server 2013 和 project Online 的非 Windows 设备开发跨浏览器 web 应用程序、Project Professional 2013 外接程序和应用程序。</span><span class="sxs-lookup"><span data-stu-id="42486-106">You can use these APIs to develop cross-browser web apps, Project Professional 2013 add-ins, and apps for non-Windows devices that access Project Server 2013 and Project Online.</span></span>
  
> [!NOTE]
> <span data-ttu-id="42486-107">JavaScript 对象模型和 REST 接口与 Project Server 客户端对象模型 (CSOM) 相一致。</span><span class="sxs-lookup"><span data-stu-id="42486-107">The JavaScript object model and REST interface align with the Project Server client-side object model (CSOM).</span></span> <span data-ttu-id="42486-108">它们提供与 CSOM 中的**microsoft.projectserver.client**命名空间等效的功能。</span><span class="sxs-lookup"><span data-stu-id="42486-108">They provide equivalent functionality to the **Microsoft.ProjectServer.Client** namespace in the CSOM.</span></span> 
  
<span data-ttu-id="42486-109">您可以通过 JavaScript 对象模型访问 Project Server 功能, 该模型是在`%ProgramFiles%\Common Files\Microsoft Shared\Web Server Extensions\15\TEMPLATE\LAYOUTS\PS.js`文件的[PS](https://msdn.microsoft.com/library/e3156167-a4fd-1bf6-8d1c-e180de1844ed%28Office.15%29.aspx)命名空间中定义的。</span><span class="sxs-lookup"><span data-stu-id="42486-109">You can access Project Server functionality through the JavaScript object model, which is defined in the [PS](https://msdn.microsoft.com/library/e3156167-a4fd-1bf6-8d1c-e180de1844ed%28Office.15%29.aspx) namespace in the  `%ProgramFiles%\Common Files\Microsoft Shared\Web Server Extensions\15\TEMPLATE\LAYOUTS\PS.js` file.</span></span> <span data-ttu-id="42486-110">[PS](https://msdn.microsoft.com/library/e3156167-a4fd-1bf6-8d1c-e180de1844ed%28Office.15%29.aspx)命名空间中的[ProjectContext](https://msdn.microsoft.com/library/a490b675-a845-ee94-3877-b99ada9bf2b0%28Office.15%29.aspx)对象是 JavaScript 对象模型的入口点。</span><span class="sxs-lookup"><span data-stu-id="42486-110">The [ProjectContext](https://msdn.microsoft.com/library/a490b675-a845-ee94-3877-b99ada9bf2b0%28Office.15%29.aspx) object in the [PS](https://msdn.microsoft.com/library/e3156167-a4fd-1bf6-8d1c-e180de1844ed%28Office.15%29.aspx) namespace is the entry point to the JavaScript object model.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="42486-111">若要浏览 JavaScript 对象模型并帮助进行调试, 可以使用同一目录中的 .ps 文件。</span><span class="sxs-lookup"><span data-stu-id="42486-111">To browse the JavaScript object model and to help with debugging, you can use the PS.debug.js file in the same directory.</span></span> <span data-ttu-id="42486-112">为帮助在远程计算机上进行开发, [Project 2013 SDK 下载](https://www.microsoft.com/en-us/download/details.aspx?id=30435)包括 CSOM 的 .net Framework 程序集, 以及 .ps 和 .ps。</span><span class="sxs-lookup"><span data-stu-id="42486-112">To help with development on a remote computer, the [Project 2013 SDK download](https://www.microsoft.com/en-us/download/details.aspx?id=30435) includes the .NET Framework assemblies for the CSOM, and the PS.js and PS.debug.js files.</span></span> 
  
<span data-ttu-id="42486-113">您还可以通过 REST 界面访问 Project Server 功能。</span><span class="sxs-lookup"><span data-stu-id="42486-113">You can also access Project Server functionality through the REST interface.</span></span> <span data-ttu-id="42486-114">REST 接口的入口点是**microsoft.projectserver.client**资源, 您可以使用`https://ServerName/pwaName/_api/ProjectServer`终结点 URI 对其进行访问。</span><span class="sxs-lookup"><span data-stu-id="42486-114">The entry point to the REST interface is the **ProjectServer** resource, which you access by using the  `https://ServerName/pwaName/_api/ProjectServer` endpoint URI.</span></span> <span data-ttu-id="42486-115">例如, 以下查询将获取指定项目中的分配 (replace _ServerName_和_pwaName_, 并将 GUID 更改为与项目匹配)。</span><span class="sxs-lookup"><span data-stu-id="42486-115">For example, the following query gets the assignments in the specified project (replace  _ServerName_ and  _pwaName_, and change the GUID to match a project).</span></span>
  
`https://ServerName/pwaName/_api/ProjectServer/Projects('263fc8d7-427c-e111-92fc-00155d3ba208')/Assignments`

<span data-ttu-id="42486-116">**microsoft.projectserver.client**资源在[REST 接口的 microsoft.projectserver.client 资源](https://msdn.microsoft.com/library/a490b675-a845-ee94-3877-b99ada9bf2b0%28Office.15%29.aspx#bk_ProjectServerResources)中进行了介绍。</span><span class="sxs-lookup"><span data-stu-id="42486-116">The **ProjectServer** resource is described in [ProjectServer resources in the REST interface](https://msdn.microsoft.com/library/a490b675-a845-ee94-3877-b99ada9bf2b0%28Office.15%29.aspx#bk_ProjectServerResources).</span></span> <span data-ttu-id="42486-117">其他 REST 资源在本参考中对应的 JavaScript 对象和成员的文档中进行了介绍。</span><span class="sxs-lookup"><span data-stu-id="42486-117">Other REST resources are described in the documentation for the corresponding JavaScript objects and members in this reference.</span></span> <span data-ttu-id="42486-118">有关使用 REST 的详细信息, 请参阅[Project Server 的客户端对象模型 (CSOM)](client-side-object-model-csom-for-project-2013.md)和[使用 SharePoint 2013 REST 服务编程](https://msdn.microsoft.com/library/fp142385%28office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="42486-118">For more information about using REST, see [Client-side object model (CSOM) for Project Server](client-side-object-model-csom-for-project-2013.md) and [Programming using the SharePoint 2013 REST service](https://msdn.microsoft.com/library/fp142385%28office.15%29.aspx).</span></span>
  
## <a name="javascript-library-and-rest-reference-for-project-server"></a><span data-ttu-id="42486-119">Project Server 的 JavaScript 库和 REST 引用</span><span class="sxs-lookup"><span data-stu-id="42486-119">JavaScript library and REST reference for Project Server</span></span>
<span data-ttu-id="42486-120"><a name="pj15_JavaScriptAPIReference_PS"> </a></span><span class="sxs-lookup"><span data-stu-id="42486-120"></span></span>

- <span data-ttu-id="42486-121">[PS js JavaScript 库和 REST 参考](https://msdn.microsoft.com/library/5a140021-380a-d9e0-e36d-106df85f56d6%28Office.15%29.aspx)包含有关适用于 Project Server 2013 的 JavaScript 对象模型和 REST 接口的信息。</span><span class="sxs-lookup"><span data-stu-id="42486-121">[PS.js JavaScript library and REST reference](https://msdn.microsoft.com/library/5a140021-380a-d9e0-e36d-106df85f56d6%28Office.15%29.aspx) Contains information about the JavaScript object model and the REST interface for Project Server 2013.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="42486-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="42486-122">See also</span></span>
<span data-ttu-id="42486-123"><a name="bk_addresources"> </a></span><span class="sxs-lookup"><span data-stu-id="42486-123"></span></span>

- [<span data-ttu-id="42486-124">Project 2013 开发人员文档</span><span class="sxs-lookup"><span data-stu-id="42486-124">Project 2013 developer documentation</span></span>](project-2013-developer-documentation.md)   
- [<span data-ttu-id="42486-125">Project Server 的客户端对象模型 (CSOM)</span><span class="sxs-lookup"><span data-stu-id="42486-125">Client-side object model (CSOM) for Project Server</span></span>](client-side-object-model-csom-for-project-2013.md)   
- [<span data-ttu-id="42486-126">JavaScript 对象模型入门</span><span class="sxs-lookup"><span data-stu-id="42486-126">Getting started with the JavaScript object model</span></span>](getting-started-with-the-project-server-2013-javascript-object-model.md)  
- [<span data-ttu-id="42486-127">使用 JavaScript 对象模型处理项目</span><span class="sxs-lookup"><span data-stu-id="42486-127">Work with projects by using the JavaScript object model</span></span>](create-retrieve-update-delete-projects-using-project-server-javascript.md)
    

