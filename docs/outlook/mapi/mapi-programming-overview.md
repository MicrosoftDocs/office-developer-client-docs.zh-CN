---
title: MAPI 编程概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 30ac637a-874f-4660-b5d0-d28d69486f64
description: 上次修改时间： 2012 年 6 月 25 日
ms.openlocfilehash: bd9cdd9119f94e1f7684be34e1b4ef6fb40ab2bf
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576503"
---
# <a name="mapi-programming-overview"></a><span data-ttu-id="e9cb7-103">MAPI 编程概述</span><span class="sxs-lookup"><span data-stu-id="e9cb7-103">MAPI Programming Overview</span></span>

  
  
<span data-ttu-id="e9cb7-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e9cb7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e9cb7-105">本 Microsoft Outlook 消息处理 API (MAPI) 参考专为 C 的 c + + 开发人员提供的各种需要和体验的消息。</span><span class="sxs-lookup"><span data-stu-id="e9cb7-105">This Microsoft Outlook Messaging API (MAPI) Reference is written for C and C++ developers with a variety of needs and experience with messaging.</span></span> <span data-ttu-id="e9cb7-106">这些开发人员希望使用 MAPI 来增加其具有邮件传送功能的应用程序，需要不的任何特定的必备知识。</span><span class="sxs-lookup"><span data-stu-id="e9cb7-106">For those developers who want to use MAPI to augment their applications that have messaging features, no specific prerequisite knowledge is required.</span></span> <span data-ttu-id="e9cb7-107">您需要在消息中的背景和使用 MAPI 创建全面工作组应用程序或专用消息系统服务驱动程序组件对象模型 (COM)。</span><span class="sxs-lookup"><span data-stu-id="e9cb7-107">You need a background in messaging and the Component Object Model (COM) to use MAPI to create full-scale workgroup applications or drivers for specialized messaging system services.</span></span>
  
<span data-ttu-id="e9cb7-108">在开始之前开发工作，应考虑以下有关如何使用 MAPI，信息登录过程中，以及如何创建和配置配置文件和消息服务。</span><span class="sxs-lookup"><span data-stu-id="e9cb7-108">Before starting development work, you should consider the following information about how to use MAPI, the logon process, and how profiles and message services are created and configured.</span></span>
  
<span data-ttu-id="e9cb7-109">邮件应用程序接口 (MAPI) 是一组广泛的开发人员可用于创建启用邮件的应用程序的功能。</span><span class="sxs-lookup"><span data-stu-id="e9cb7-109">The Messaging Application Program Interface (MAPI) is an extensive set of functions that developers can use to create mail-enabled applications.</span></span> <span data-ttu-id="e9cb7-110">全功能库称为 MAPI。</span><span class="sxs-lookup"><span data-stu-id="e9cb7-110">The full function library is known as MAPI.</span></span> <span data-ttu-id="e9cb7-111">MAPI 允许完全控制消息系统对客户端计算机、 创建和管理消息的、 管理客户端邮箱、 服务提供商，等等。</span><span class="sxs-lookup"><span data-stu-id="e9cb7-111">MAPI enables complete control over the messaging system on the client computer, creation and management of messages, management of the client mailbox, service providers, and so on.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e9cb7-112">扩展的 MAPI 是 MAPI，相同，只需称为 MAPI MAPI 文档中。</span><span class="sxs-lookup"><span data-stu-id="e9cb7-112">Extended MAPI is the same as MAPI, and is simply referred to as MAPI in the MAPI documentation.</span></span> 
  
 <span data-ttu-id="e9cb7-113">**简单 MAPI**</span><span class="sxs-lookup"><span data-stu-id="e9cb7-113">**Simple MAPI**</span></span>
  
<span data-ttu-id="e9cb7-114">简单 MAPI 提供了一组功能，使您能够添加基本级别的消息到 Microsoft 基于 Windows 的应用程序的功能。</span><span class="sxs-lookup"><span data-stu-id="e9cb7-114">Simple MAPI provides a set of functions that enables you to add a basic level of messaging functionality to Microsoft Windows-based applications.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e9cb7-115">简单 MAPI 函数 MAPISendMail 受支持 Microsoft Outlook 2013 和 Microsoft Outlook 2010。</span><span class="sxs-lookup"><span data-stu-id="e9cb7-115">The Simple MAPI function MAPISendMail is supported by Microsoft Outlook 2013 and Microsoft Outlook 2010.</span></span> <span data-ttu-id="e9cb7-116">在 Windows 中已弃用其他简单 MAPI 函数。</span><span class="sxs-lookup"><span data-stu-id="e9cb7-116">Other Simple MAPI functions have been deprecated in Windows.</span></span> 
  

