---
title: MAPI 编程概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 30ac637a-874f-4660-b5d0-d28d69486f64
description: 上次修改时间：2012 年 6 月 25 日
ms.openlocfilehash: d69d15f0f635c81bea30401b3a6d6e3ccf620112
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408339"
---
# <a name="mapi-programming-overview"></a><span data-ttu-id="5de16-103">MAPI 编程概述</span><span class="sxs-lookup"><span data-stu-id="5de16-103">MAPI Programming Overview</span></span>

  
  
<span data-ttu-id="5de16-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5de16-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5de16-105">本 Microsoft Outlook消息传递 API (MAPI) 参考是针对 C 和 C++ 开发人员编写的，具有各种消息传递需求和经验。</span><span class="sxs-lookup"><span data-stu-id="5de16-105">This Microsoft Outlook Messaging API (MAPI) Reference is written for C and C++ developers with a variety of needs and experience with messaging.</span></span> <span data-ttu-id="5de16-106">对于想要使用 MAPI 扩充其具有邮件功能的应用程序的开发人员，不需要特定的必备知识。</span><span class="sxs-lookup"><span data-stu-id="5de16-106">For those developers who want to use MAPI to augment their applications that have messaging features, no specific prerequisite knowledge is required.</span></span> <span data-ttu-id="5de16-107">您需要具有邮件和组件对象模型 (COM) 的背景，以使用 MAPI 为专用邮件系统服务创建完整的工作组应用程序或驱动程序。</span><span class="sxs-lookup"><span data-stu-id="5de16-107">You need a background in messaging and the Component Object Model (COM) to use MAPI to create full-scale workgroup applications or drivers for specialized messaging system services.</span></span>
  
<span data-ttu-id="5de16-108">在开始开发工作之前，应考虑以下有关如何使用 MAPI、登录过程以及如何创建和配置配置文件和邮件服务的信息。</span><span class="sxs-lookup"><span data-stu-id="5de16-108">Before starting development work, you should consider the following information about how to use MAPI, the logon process, and how profiles and message services are created and configured.</span></span>
  
<span data-ttu-id="5de16-109">MAPI 应用程序接口 (MAPI) 是一组广泛的功能，开发人员可以使用这些功能创建启用邮件的应用程序。</span><span class="sxs-lookup"><span data-stu-id="5de16-109">The Messaging Application Program Interface (MAPI) is an extensive set of functions that developers can use to create mail-enabled applications.</span></span> <span data-ttu-id="5de16-110">完整的函数库称为 MAPI。</span><span class="sxs-lookup"><span data-stu-id="5de16-110">The full function library is known as MAPI.</span></span> <span data-ttu-id="5de16-111">MAPI 使用户可以完全控制客户端计算机上的邮件系统、创建和管理邮件、管理客户端邮箱、服务提供商等。</span><span class="sxs-lookup"><span data-stu-id="5de16-111">MAPI enables complete control over the messaging system on the client computer, creation and management of messages, management of the client mailbox, service providers, and so on.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5de16-112">扩展 MAPI 与 MAPI 相同，在 MAPI 文档中只称为 MAPI。</span><span class="sxs-lookup"><span data-stu-id="5de16-112">Extended MAPI is the same as MAPI, and is simply referred to as MAPI in the MAPI documentation.</span></span> 
  
 <span data-ttu-id="5de16-113">**Simple MAPI**</span><span class="sxs-lookup"><span data-stu-id="5de16-113">**Simple MAPI**</span></span>
  
<span data-ttu-id="5de16-114">简单 MAPI 提供了一组功能，使您能够将基本级别的邮件功能添加到基于 microsoft Windows应用程序。</span><span class="sxs-lookup"><span data-stu-id="5de16-114">Simple MAPI provides a set of functions that enables you to add a basic level of messaging functionality to Microsoft Windows-based applications.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5de16-115">简单 MAPI 函数 MAPISendMail 受 Microsoft Outlook 2013 和 Microsoft Outlook 2010。</span><span class="sxs-lookup"><span data-stu-id="5de16-115">The Simple MAPI function MAPISendMail is supported by Microsoft Outlook 2013 and Microsoft Outlook 2010.</span></span> <span data-ttu-id="5de16-116">其他简单 MAPI 函数在 Windows 中已弃Windows。</span><span class="sxs-lookup"><span data-stu-id="5de16-116">Other Simple MAPI functions have been deprecated in Windows.</span></span> 
  

