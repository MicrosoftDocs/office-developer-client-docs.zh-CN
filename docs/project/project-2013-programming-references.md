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
- project server 接口，Project Server 错误代码，VBA，Project 对象模型，Project 2013 平台，Visual Basic for Applications Project 对象模型，对象模型，Project VBA、 Project Server、 PSI 引用 PSI
localization_priority: Normal
ms.assetid: 79c78c44-1e08-4c9b-a7fe-a5089e666055
description: 查找概述的 Project Server 接口 (PSI) 参考，如何 ProjectData OData 服务中使用 ASMX 接口和 PSI、 有关 Project Server 错误代码的信息和引用的 WCF 接口。
ms.openlocfilehash: 8e2ee8730e737408899b6fe26ce55210e0c68e81
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/15/2018
ms.locfileid: "19779544"
---
# <a name="project-2013-programming-references"></a><span data-ttu-id="51b33-104">Project 2013 编程参考文档</span><span class="sxs-lookup"><span data-stu-id="51b33-104">Project 2013 programming references</span></span>

<span data-ttu-id="51b33-105">查找概述的 Project Server 接口 (PSI) 参考，如何使用**ProjectData** OData 服务的 ASMX 接口和 PSI、 有关 Project Server 错误代码的信息和引用的 WCF 接口。</span><span class="sxs-lookup"><span data-stu-id="51b33-105">Find an overview of the Project Server Interface (PSI) reference, how to use the ASMX interface and the WCF interface of the PSI, information about Project Server error codes, and a reference for the **ProjectData** OData service.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="51b33-106">PSI 和 Project Server 2013 中的客户端对象模型 (CSOM) 的主要引用，请参阅以下各节：[类类库和 web 服务引用](http://msdn.microsoft.com/library/ef1830e0-3c9a-4f98-aa0a-5556c298e7d1%28Office.15%29.aspx)和[Project Server 2013 的 JavaScript API 参考](javascript-library-and-rest-reference-for-project-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="51b33-106">For the primary references for the PSI and the client-side object model (CSOM) in Project Server 2013, see the following sections: [Class library and web service reference](http://msdn.microsoft.com/library/ef1830e0-3c9a-4f98-aa0a-5556c298e7d1%28Office.15%29.aspx) and [JavaScript API reference for Project Server 2013](javascript-library-and-rest-reference-for-project-server-2013.md).</span></span> <span data-ttu-id="51b33-107">> Office 加载项，其中包括 Project 2013 任务窗格应用程序的 JavaScript 引用，请参阅[JavaScript API for Office](http://msdn.microsoft.com/en-us/library/fp142185.aspx)。</span><span class="sxs-lookup"><span data-stu-id="51b33-107">> For the Office Add-ins references, which include the JavaScript reference for Project 2013 task pane apps, see [JavaScript API for Office](http://msdn.microsoft.com/en-us/library/fp142185.aspx).</span></span> <span data-ttu-id="51b33-108">> 的 Project Standard 2013 和 Project Professional 2013 的 VBA 参考，请参阅[Project 2013 VBA 开发人员参考](http://msdn.microsoft.com/en-us/library/jj235035.aspx)。</span><span class="sxs-lookup"><span data-stu-id="51b33-108">> For the VBA reference for Project Standard 2013 and Project Professional 2013, see [Project 2013 VBA developer reference](http://msdn.microsoft.com/en-us/library/jj235035.aspx).</span></span> <span data-ttu-id="51b33-109">> 报告表和本地 Project Server 2013 数据库中的视图参考尚不可用。</span><span class="sxs-lookup"><span data-stu-id="51b33-109">> The reference for the reporting tables and views in the on-premises Project Server 2013 database is not yet available.</span></span> 
  
## <a name="in-this-section"></a><span data-ttu-id="51b33-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="51b33-110">In this section</span></span>

<span data-ttu-id="51b33-111">[Project PSI 参考概述](project-psi-reference-overview.md)Project Server 2013 中介绍的程序集和 PSI 引用中的命名空间。</span><span class="sxs-lookup"><span data-stu-id="51b33-111">[Project PSI reference overview](project-psi-reference-overview.md) Describes the assemblies and namespaces in the PSI reference for Project Server 2013.</span></span> 
  
<span data-ttu-id="51b33-112">[在项目中的基于 ASMX 的代码示例的先决条件](prerequisites-for-asmx-based-code-samples-in-project.md)介绍如何使用 PSI 引用中测试应用程序中使用 ASMX web 服务构建的代码示例。</span><span class="sxs-lookup"><span data-stu-id="51b33-112">[Prerequisites for ASMX-based code samples in Project](prerequisites-for-asmx-based-code-samples-in-project.md) Describes how to use code samples in the PSI reference that are built by using ASMX web services in your test applications.</span></span> 
  
<span data-ttu-id="51b33-113">[在项目中的基于 WCF 的代码示例的先决条件](prerequisites-for-wcf-based-code-samples-in-project.md)介绍如何使用 PSI 引用中由您测试应用程序中使用 Windows Communication Foundation (WCF) 服务构建的代码示例。</span><span class="sxs-lookup"><span data-stu-id="51b33-113">[Prerequisites for WCF-based code samples in Project](prerequisites-for-wcf-based-code-samples-in-project.md) Describes how to use code samples in the PSI reference that are built by using Windows Communication Foundation (WCF) services in your test applications.</span></span> 
  
<span data-ttu-id="51b33-114">[Project Server 错误代码](project-server-error-codes.md)列出的代码和按功能区域的 Project Server 错误的说明。</span><span class="sxs-lookup"><span data-stu-id="51b33-114">[Project Server error codes](project-server-error-codes.md) Lists the codes and descriptions of Project Server errors by functional area.</span></span> 
  
<span data-ttu-id="51b33-115">[ProjectData-Project OData 服务引用](https://msdn.microsoft.com/en-us/library/office/jj163015.aspx)包括 Project Server 报告数据的 OData 服务、 简介使用 LINQ 查询和引用用于**ProjectData**服务中的 XML 元数据的 OData 源的概述。</span><span class="sxs-lookup"><span data-stu-id="51b33-115">[ProjectData - Project OData service reference](https://msdn.microsoft.com/en-us/library/office/jj163015.aspx) Includes an overview of the OData service for Project Server reporting data, an introduction to using the OData feeds with LINQ queries, and references for the XML metadata in the **ProjectData** service.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="51b33-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="51b33-116">See also</span></span>



[<span data-ttu-id="51b33-117">适用于 Office 的 JavaScript API</span><span class="sxs-lookup"><span data-stu-id="51b33-117">JavaScript API for Office</span></span>](http://msdn.microsoft.com/en-us/library/fp142185.aspx)
  
[<span data-ttu-id="51b33-118">Project 2013 VBA 开发人员参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="51b33-118">Project 2013 VBA developer reference</span></span>](http://msdn.microsoft.com/en-us/library/jj235035.aspx)

