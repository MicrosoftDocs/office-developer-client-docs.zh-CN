---
title: 将 InfoPath 作为 XML 编辑器托管在另一个应用程序中
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: ae24b317-f486-763a-7009-e32c5cb85b59
description: Microsoft InfoPath 表单编辑环境可以托管在自定义 Windows 应用程序中，这样开发人员可以将 InfoPath 表单编辑环境集成到业务线应用程序中。
ms.openlocfilehash: b85e47d506b17982bb883c9d56ea13131807d1cf
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422577"
---
# <a name="hosting-infopath-as-an-xml-editor-in-another-application"></a><span data-ttu-id="6cd59-103">将 InfoPath 作为 XML 编辑器托管在另一个应用程序中</span><span class="sxs-lookup"><span data-stu-id="6cd59-103">Hosting InfoPath as an XML Editor in Another Application</span></span>

<span data-ttu-id="6cd59-p101">Microsoft InfoPath 表单编辑环境可以承载在自定义 Windows 应用程序中。该功能使开发人员可以将 InfoPath 表单编辑环境集成到业务线应用程序中。编写基于 COM 的传统应用程序的开发人员可以通过引用 IPEDITOR.DLL 来使用可用的 **InfoPathEditorObject** 对象，而编写基于 Microsoft .NET 的应用程序的开发人员可以使用 **Microsoft.Office.InfoPath.FormControl** 程序集，该程序集提供基于 COM 接口的托管类型。IPEDITOR.DLL 和 **Microsoft.Office.InfoPath.FormControl** 程序集都随 InfoPath 一起安装在 C:\Program Files\Microsoft Office\Office15 或 C:\Program Files (x86)\Microsoft Office\Office15 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="6cd59-p101">The Microsoft InfoPath form editing environment can be hosted in a custom Windows application. This feature enables developers to integrate the InfoPath form editing environment into line-of-business applications. Developers writing traditional COM-based applications can use the **InfoPathEditorObject** object that is available by referencing the IPEDITOR.DLL, and developers writing Microsoft .NET-based applications can use the **Microsoft.Office.InfoPath.FormControl** assembly, which provides managed types based on the COM interface. The IPEDITOR.DLL and **Microsoft.Office.InfoPath.FormControl** assembly are both installed along with InfoPath in the C:\Program Files\Microsoft Office\Office15 or C:\Program Files (x86)\Microsoft Office\Office15 folder.</span></span> 
  
<span data-ttu-id="6cd59-108">MSDN 文章“在自定义 Windows 表单应用程序中托管 InfoPath 2007 表单编辑环境”重点介绍了 **FormControl** 对象以及如何将该对象纳入基于 .NET 的自定义应用程序中。</span><span class="sxs-lookup"><span data-stu-id="6cd59-108">The MSDN article, Hosting the InfoPath 2007 Form Editing Environment in a Custom Windows Form Application, focuses on the **FormControl** object and how to incorporate it into your custom .NET-based applications.</span></span> <span data-ttu-id="6cd59-109">与这篇文章关联的下载内容包含一个可提供 .NET 功能的自定义应用程序，可通过使用 COM **IOleCommandTargets** 来复制 InfoPath 表单编辑环境。</span><span class="sxs-lookup"><span data-stu-id="6cd59-109">The download associated with the article contains a custom application that provides .NET functions for replicating the InfoPath form editing environment through the use of COM **IOleCommandTargets**.</span></span>
  

