---
title: JavaScript 库和 Project server REST 参考
manager: soliver
ms.date: 08/10/2016
ms.audience: Developer
localization_priority: Normal
ms.assetid: 67b47b8b-d34b-4fad-af49-0c258c345ad2
description: JavaScript 库和 REST 引用的 Project Server 2013 包含有关 JavaScript 对象模型和 REST 接口用于访问 Project Server 功能的信息。 这些 Api 可用于开发跨浏览器的 web 应用程序、 Project Professional 2013 外接程序，和相关应用程序访问 Project Server 2013 和 Project Online 的非 Windows 设备。
ms.openlocfilehash: fb58de1e3858a39f42cc9a643a7394cec191a462
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25399030"
---
# <a name="javascript-library-and-rest-reference-for-project-server"></a><span data-ttu-id="8090d-104">JavaScript 库和 Project server REST 参考</span><span class="sxs-lookup"><span data-stu-id="8090d-104">JavaScript library and REST reference for Project Server</span></span>

<span data-ttu-id="8090d-105">JavaScript 库和 REST 引用的 Project Server 2013 包含有关 JavaScript 对象模型和 REST 接口用于访问 Project Server 功能的信息。</span><span class="sxs-lookup"><span data-stu-id="8090d-105">The JavaScript library and REST reference for Project Server 2013 contains information about the JavaScript object model and the REST interface that you use to access Project Server functionality.</span></span> <span data-ttu-id="8090d-106">这些 Api 可用于开发跨浏览器的 web 应用程序、 Project Professional 2013 外接程序，和相关应用程序访问 Project Server 2013 和 Project Online 的非 Windows 设备。</span><span class="sxs-lookup"><span data-stu-id="8090d-106">You can use these APIs to develop cross-browser web apps, Project Professional 2013 add-ins, and apps for non-Windows devices that access Project Server 2013 and Project Online.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8090d-107">JavaScript 对象模型和 REST 接口与 Project Server 客户端对象模型 (CSOM) 对齐。</span><span class="sxs-lookup"><span data-stu-id="8090d-107">The JavaScript object model and REST interface align with the Project Server client-side object model (CSOM).</span></span> <span data-ttu-id="8090d-108">它们提供对**Microsoft.ProjectServer.Client**命名空间中 CSOM 的等效功能。</span><span class="sxs-lookup"><span data-stu-id="8090d-108">They provide equivalent functionality to the **Microsoft.ProjectServer.Client** namespace in the CSOM.</span></span> 
  
<span data-ttu-id="8090d-109">您可以通过 JavaScript 对象模型中的[PS](https://msdn.microsoft.com/library/e3156167-a4fd-1bf6-8d1c-e180de1844ed%28Office.15%29.aspx)命名空间中定义访问 Project Server 功能`%ProgramFiles%\Common Files\Microsoft Shared\Web Server Extensions\15\TEMPLATE\LAYOUTS\PS.js`文件。</span><span class="sxs-lookup"><span data-stu-id="8090d-109">You can access Project Server functionality through the JavaScript object model, which is defined in the [PS](https://msdn.microsoft.com/library/e3156167-a4fd-1bf6-8d1c-e180de1844ed%28Office.15%29.aspx) namespace in the  `%ProgramFiles%\Common Files\Microsoft Shared\Web Server Extensions\15\TEMPLATE\LAYOUTS\PS.js` file.</span></span> <span data-ttu-id="8090d-110">[PS](https://msdn.microsoft.com/library/e3156167-a4fd-1bf6-8d1c-e180de1844ed%28Office.15%29.aspx)命名空间中的[ProjectContext](https://msdn.microsoft.com/library/a490b675-a845-ee94-3877-b99ada9bf2b0%28Office.15%29.aspx)对象是对 JavaScript 对象模型的入口点。</span><span class="sxs-lookup"><span data-stu-id="8090d-110">The [ProjectContext](https://msdn.microsoft.com/library/a490b675-a845-ee94-3877-b99ada9bf2b0%28Office.15%29.aspx) object in the [PS](https://msdn.microsoft.com/library/e3156167-a4fd-1bf6-8d1c-e180de1844ed%28Office.15%29.aspx) namespace is the entry point to the JavaScript object model.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="8090d-111">若要浏览的 JavaScript 对象模型并帮助进行调试，您可以使用 PS.debug.js 文件位于同一目录中。</span><span class="sxs-lookup"><span data-stu-id="8090d-111">To browse the JavaScript object model and to help with debugging, you can use the PS.debug.js file in the same directory.</span></span> <span data-ttu-id="8090d-112">为了进行远程计算机上开发， [Project 2013 SDK 下载](https://www.microsoft.com/en-us/download/details.aspx?id=30435)包括.NET Framework 程序集 CSOM，以及所 PS.js 和 PS.debug.js 文件。</span><span class="sxs-lookup"><span data-stu-id="8090d-112">To help with development on a remote computer, the [Project 2013 SDK download](https://www.microsoft.com/en-us/download/details.aspx?id=30435) includes the .NET Framework assemblies for the CSOM, and the PS.js and PS.debug.js files.</span></span> 
  
<span data-ttu-id="8090d-113">您还可以通过 REST 界面访问 Project Server 功能。</span><span class="sxs-lookup"><span data-stu-id="8090d-113">You can also access Project Server functionality through the REST interface.</span></span> <span data-ttu-id="8090d-114">REST 接口的入口点是**ProjectServer**资源，使用访问`https://ServerName/pwaName/_api/ProjectServer`终结点 URI。</span><span class="sxs-lookup"><span data-stu-id="8090d-114">The entry point to the REST interface is the **ProjectServer** resource, which you access by using the  `https://ServerName/pwaName/_api/ProjectServer` endpoint URI.</span></span> <span data-ttu-id="8090d-115">例如，下面的查询指定项目中获取工作分配 （将_ServerName_和_pwaName_，并更改以匹配的项目的 GUID）。</span><span class="sxs-lookup"><span data-stu-id="8090d-115">For example, the following query gets the assignments in the specified project (replace  _ServerName_ and  _pwaName_, and change the GUID to match a project).</span></span>
  
`https://ServerName/pwaName/_api/ProjectServer/Projects('263fc8d7-427c-e111-92fc-00155d3ba208')/Assignments`

<span data-ttu-id="8090d-116">[在 REST 界面 ProjectServer 资源](https://msdn.microsoft.com/library/a490b675-a845-ee94-3877-b99ada9bf2b0%28Office.15%29.aspx#bk_ProjectServerResources)中介绍了**ProjectServer**资源。</span><span class="sxs-lookup"><span data-stu-id="8090d-116">The **ProjectServer** resource is described in [ProjectServer resources in the REST interface](https://msdn.microsoft.com/library/a490b675-a845-ee94-3877-b99ada9bf2b0%28Office.15%29.aspx#bk_ProjectServerResources).</span></span> <span data-ttu-id="8090d-117">其他 REST 资源的相应的 JavaScript 对象和成员本参考中的文档所述。</span><span class="sxs-lookup"><span data-stu-id="8090d-117">Other REST resources are described in the documentation for the corresponding JavaScript objects and members in this reference.</span></span> <span data-ttu-id="8090d-118">有关使用 REST 的详细信息，请参阅[Project server 的客户端对象模型 (CSOM)](client-side-object-model-csom-for-project-2013.md)和[编程使用 SharePoint 2013 REST 服务](https://msdn.microsoft.com/library/fp142385%28office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="8090d-118">For more information about using REST, see [Client-side object model (CSOM) for Project Server](client-side-object-model-csom-for-project-2013.md) and [Programming using the SharePoint 2013 REST service](https://msdn.microsoft.com/library/fp142385%28office.15%29.aspx).</span></span>
  
## <a name="javascript-library-and-rest-reference-for-project-server"></a><span data-ttu-id="8090d-119">JavaScript 库和 Project server REST 参考</span><span class="sxs-lookup"><span data-stu-id="8090d-119">JavaScript library and REST reference for Project Server</span></span>
<span data-ttu-id="8090d-120"><a name="pj15_JavaScriptAPIReference_PS"> </a></span><span class="sxs-lookup"><span data-stu-id="8090d-120"></span></span>

- <span data-ttu-id="8090d-121">[PS.js JavaScript 库和 REST 参考](https://msdn.microsoft.com/library/5a140021-380a-d9e0-e36d-106df85f56d6%28Office.15%29.aspx)包含有关 JavaScript 对象模型和 REST 接口的 Project Server 2013 的信息。</span><span class="sxs-lookup"><span data-stu-id="8090d-121">[PS.js JavaScript library and REST reference](https://msdn.microsoft.com/library/5a140021-380a-d9e0-e36d-106df85f56d6%28Office.15%29.aspx) Contains information about the JavaScript object model and the REST interface for Project Server 2013.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="8090d-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8090d-122">See also</span></span>
<span data-ttu-id="8090d-123"><a name="bk_addresources"> </a></span><span class="sxs-lookup"><span data-stu-id="8090d-123"></span></span>

- [<span data-ttu-id="8090d-124">Project 2013 开发人员文档</span><span class="sxs-lookup"><span data-stu-id="8090d-124">Project 2013 developer documentation</span></span>](project-2013-developer-documentation.md)   
- [<span data-ttu-id="8090d-125">Project Server 的客户端对象模型 (CSOM)</span><span class="sxs-lookup"><span data-stu-id="8090d-125">Client-side object model (CSOM) for Project Server</span></span>](client-side-object-model-csom-for-project-2013.md)   
- [<span data-ttu-id="8090d-126">JavaScript 对象模型入门</span><span class="sxs-lookup"><span data-stu-id="8090d-126">Getting started with the JavaScript object model</span></span>](getting-started-with-the-project-server-2013-javascript-object-model.md)  
- [<span data-ttu-id="8090d-127">使用 JavaScript 对象模型处理项目</span><span class="sxs-lookup"><span data-stu-id="8090d-127">Work with projects by using the JavaScript object model</span></span>](create-retrieve-update-delete-projects-using-project-server-javascript.md)
    

