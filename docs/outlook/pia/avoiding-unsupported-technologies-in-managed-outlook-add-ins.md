---
title: 避免在托管 Outlook 加载项中使用不受支持的技术
TOCTitle: Avoiding unsupported technologies in managed Outlook add-ins
ms:assetid: 365fd319-725f-4c4b-b6e7-575f78ed8bda
ms:mtpsurl: https://msdn.microsoft.com/library/office/bb610014(v=office.15)
ms:contentKeyID: 55119789
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 99cdfc2447e6bf63078eb87bb9546d8b07ee83e1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359056"
---
# <a name="avoiding-unsupported-technologies-in-managed-outlook-add-ins"></a><span data-ttu-id="fdeaf-102">避免在托管 Outlook 加载项中使用不受支持的技术</span><span class="sxs-lookup"><span data-stu-id="fdeaf-102">Avoiding unsupported technologies in managed Outlook add-ins</span></span>

<span data-ttu-id="fdeaf-103">托管代码编程不支持先于 .NET Framework 出现的某些技术。</span><span class="sxs-lookup"><span data-stu-id="fdeaf-103">Certain technologies that predate the .NET Framework are not supported in managed code programming.</span></span> <span data-ttu-id="fdeaf-104">这些技术包括，协作数据对象 (CDO)、消息处理应用程序编程接口（MAPI，通常称为“扩展 MAPI”）和简单 MAPI。</span><span class="sxs-lookup"><span data-stu-id="fdeaf-104">These technologies include Collaboration Data Objects (CDO), Messaging Application Programming Interface (MAPI, often known as Extended MAPI), and Simple MAPI.</span></span> <span data-ttu-id="fdeaf-105">这些技术是使用非托管代码进行设计和开发，Microsoft 不提供官方托管包装器来支持在托管应用程序中使用它们。</span><span class="sxs-lookup"><span data-stu-id="fdeaf-105">These technologies were designed and developed with unmanaged code, and Microsoft does not provide official managed wrappers to support their use in managed applications.</span></span> 

<span data-ttu-id="fdeaf-106">有关详细信息，请参阅 [KB 266353：客户端消息处理开发的支持指南](https://go.microsoft.com/fwlink/?linkid=89209)一文中的“托管代码支持的 API”部分。</span><span class="sxs-lookup"><span data-stu-id="fdeaf-106">For more information, see the section "APIs that are supported in managed code" in the article [KB 266353: The support guidelines for client-side messaging development](https://go.microsoft.com/fwlink/?linkid=89209).</span></span>

<span data-ttu-id="fdeaf-107">尽管如此，Microsoft Outlook 提供了许多对象模型功能，解决了以前只有 CDO 和 Exchange 客户端扩展 (ECE) 才能为开发人员解决的问题。</span><span class="sxs-lookup"><span data-stu-id="fdeaf-107">Nonetheless, Microsoft Outlook offers many object model features that achieve what previously only CDO and Exchange Client Extensions (ECE) solved for developers.</span></span> <span data-ttu-id="fdeaf-108">如果您在现有的非托管 Outlook 应用程序中使用 CDO，并且由于托管解决方案中缺少对 CDO 的支持导致您无法将应用程序迁移到托管代码中，您现在可以考虑只使用 Outlook 对象模型和主互操作程序集 (PIA) 将解决方案更新到托管代码中，而不必求助于 CDO。</span><span class="sxs-lookup"><span data-stu-id="fdeaf-108">If you use CDO in an existing unmanaged Outlook application and the lack of support for CDO in managed solutions has hindered you from migrating the application to managed code, you can now consider updating your solution to managed code, using only the Outlook object model and the Primary Interop Assembly (PIA), without having to resort to CDO.</span></span> 

<span data-ttu-id="fdeaf-109">有关 Outlook 2007 为了减少对 CDO 和 ECE 的依赖而引入的更综合的 Outlook 平台的详细信息，请参阅 [What's New for Developers in Outlook 2007 (Part 1 of 2)](https://msdn.microsoft.com/library/bb226711\(v=office.15\))。</span><span class="sxs-lookup"><span data-stu-id="fdeaf-109">For more information about a more comprehensive Outlook platform introduced in Outlook 2007 to reduce reliance on CDO and ECE, see [What's New for Developers in Outlook 2007 (Part 1 of 2)](https://msdn.microsoft.com/library/bb226711\(v=office.15\)).</span></span>

