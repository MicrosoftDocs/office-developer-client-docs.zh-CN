---
title: Project 2013 编程参考文档
manager: soliver
ms.date: 09/17/2015
ms.audience: Developer
f1_keywords:
- error codes
- object model
- Project Server errors
- Project VBA
- PSI
- PSI reference
- VBA
- VBA object model
keywords:
- project server interface, project server, 错误代码, VBA, project 对象模型, Project 2013, 平台, Visual Basic for Applications, project 对象模型, 对象模型, project VBA, project server, psi 引用, psi
localization_priority: Normal
ms.assetid: 79c78c44-1e08-4c9b-a7fe-a5089e666055
description: 查找有关 project server Interface (psi) 参考、如何使用 .asmx 接口和 PSI 的 WCF 接口的概述、有关 Project Server 错误代码的信息以及对 ProjectData OData 服务的引用。
ms.openlocfilehash: 27b2eb27d62ec1abdb1a835b5d874e211e7e793e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357034"
---
# <a name="project-2013-programming-references"></a><span data-ttu-id="c1c1a-104">Project 2013 编程参考文档</span><span class="sxs-lookup"><span data-stu-id="c1c1a-104">Project 2013 programming references</span></span>

<span data-ttu-id="c1c1a-105">查找有关 project server Interface (psi) 参考、如何使用 .asmx 接口和 PSI 的 WCF 接口的概述、有关 Project Server 错误代码的信息以及对**ProjectData** OData 服务的引用。</span><span class="sxs-lookup"><span data-stu-id="c1c1a-105">Find an overview of the Project Server Interface (PSI) reference, how to use the ASMX interface and the WCF interface of the PSI, information about Project Server error codes, and a reference for the **ProjectData** OData service.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c1c1a-106">有关 PSI 的主要参考和 project server 2013 中的客户端对象模型 (CSOM), 请参阅以下部分:[适用于 project server 2013](javascript-library-and-rest-reference-for-project-server-2013.md)的[类库和 web 服务参考](https://msdn.microsoft.com/library/ef1830e0-3c9a-4f98-aa0a-5556c298e7d1%28Office.15%29.aspx)和 JavaScript API reference。</span><span class="sxs-lookup"><span data-stu-id="c1c1a-106">For the primary references for the PSI and the client-side object model (CSOM) in Project Server 2013, see the following sections: [Class library and web service reference](https://msdn.microsoft.com/library/ef1830e0-3c9a-4f98-aa0a-5556c298e7d1%28Office.15%29.aspx) and [JavaScript API reference for Project Server 2013](javascript-library-and-rest-reference-for-project-server-2013.md).</span></span> <span data-ttu-id="c1c1a-107">> for office 外接程序引用 (包括 Project 2013 任务窗格应用程序的 javascript 引用), 请参阅[javascript API for Office](https://msdn.microsoft.com/library/fp142185.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c1c1a-107">> For the Office Add-ins references, which include the JavaScript reference for Project 2013 task pane apps, see [JavaScript API for Office](https://msdn.microsoft.com/library/fp142185.aspx).</span></span> <span data-ttu-id="c1c1a-108">> for the project Standard 2013 and project Professional 2013 的 vba 参考, 请参阅[project 2013 VBA 开发人员参考](https://msdn.microsoft.com/library/jj235035.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c1c1a-108">> For the VBA reference for Project Standard 2013 and Project Professional 2013, see [Project 2013 VBA developer reference](https://msdn.microsoft.com/library/jj235035.aspx).</span></span> <span data-ttu-id="c1c1a-109">> 对报告表和内部部署 Project Server 2013 数据库中的视图的引用尚不可用。</span><span class="sxs-lookup"><span data-stu-id="c1c1a-109">> The reference for the reporting tables and views in the on-premises Project Server 2013 database is not yet available.</span></span> 
  
## <a name="in-this-section"></a><span data-ttu-id="c1c1a-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="c1c1a-110">In this section</span></span>

<span data-ttu-id="c1c1a-111">[Project PSI 参考概述](project-psi-reference-overview.md)介绍了 Project Server 2013 的 PSI 参考中的程序集和命名空间。</span><span class="sxs-lookup"><span data-stu-id="c1c1a-111">[Project PSI reference overview](project-psi-reference-overview.md) Describes the assemblies and namespaces in the PSI reference for Project Server 2013.</span></span> 
  
<span data-ttu-id="c1c1a-112">[Project 中基于 .asmx 的代码示例的先决条件](prerequisites-for-asmx-based-code-samples-in-project.md)介绍如何使用在测试应用程序中使用 .asmx web 服务生成的 PSI 引用中的代码示例。</span><span class="sxs-lookup"><span data-stu-id="c1c1a-112">[Prerequisites for ASMX-based code samples in Project](prerequisites-for-asmx-based-code-samples-in-project.md) Describes how to use code samples in the PSI reference that are built by using ASMX web services in your test applications.</span></span> 
  
<span data-ttu-id="c1c1a-113">[Project 中基于 WCF 的代码示例的先决条件](prerequisites-for-wcf-based-code-samples-in-project.md)介绍如何使用在测试应用程序中使用 Windows Communication Foundation (WCF) 服务生成的 PSI 引用中的代码示例。</span><span class="sxs-lookup"><span data-stu-id="c1c1a-113">[Prerequisites for WCF-based code samples in Project](prerequisites-for-wcf-based-code-samples-in-project.md) Describes how to use code samples in the PSI reference that are built by using Windows Communication Foundation (WCF) services in your test applications.</span></span> 
  
<span data-ttu-id="c1c1a-114">[Project Server 错误代码](project-server-error-codes.md)按功能区域列出 Project Server 错误的代码和说明。</span><span class="sxs-lookup"><span data-stu-id="c1c1a-114">[Project Server error codes](project-server-error-codes.md) Lists the codes and descriptions of Project Server errors by functional area.</span></span> 
  
<span data-ttu-id="c1c1a-115">[ProjectData-Project OData 服务引用](https://msdn.microsoft.com/library/office/jj163015.aspx)概述了对 Project Server 报告数据的 odata 服务、将 odata 源与 LINQ 查询一起使用的简介, 以及对**ProjectData**服务中的 XML 元数据的引用。</span><span class="sxs-lookup"><span data-stu-id="c1c1a-115">[ProjectData - Project OData service reference](https://msdn.microsoft.com/library/office/jj163015.aspx) Includes an overview of the OData service for Project Server reporting data, an introduction to using the OData feeds with LINQ queries, and references for the XML metadata in the **ProjectData** service.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="c1c1a-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c1c1a-116">See also</span></span>



[<span data-ttu-id="c1c1a-117">适用于 Office 的 JavaScript API</span><span class="sxs-lookup"><span data-stu-id="c1c1a-117">JavaScript API for Office</span></span>](https://msdn.microsoft.com/library/fp142185.aspx)
  
[<span data-ttu-id="c1c1a-118">Project 2013 VBA 开发人员参考</span><span class="sxs-lookup"><span data-stu-id="c1c1a-118">Project 2013 VBA developer reference</span></span>](https://msdn.microsoft.com/library/jj235035.aspx)

