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
# <a name="mapi-programming-overview"></a><span data-ttu-id="af834-103">MAPI 编程概述</span><span class="sxs-lookup"><span data-stu-id="af834-103">MAPI Programming Overview</span></span>

  
  
<span data-ttu-id="af834-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="af834-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="af834-105">此 Microsoft Outlook 消息处理 API (MAPI) 引用是为 c 和 c + + 开发人员编写的, 其中包含针对消息传递的各种需求和体验。</span><span class="sxs-lookup"><span data-stu-id="af834-105">This Microsoft Outlook Messaging API (MAPI) Reference is written for C and C++ developers with a variety of needs and experience with messaging.</span></span> <span data-ttu-id="af834-106">对于想要使用 MAPI 来扩充其具有邮件功能的应用程序的开发人员, 不需要特定的先决条件知识。</span><span class="sxs-lookup"><span data-stu-id="af834-106">For those developers who want to use MAPI to augment their applications that have messaging features, no specific prerequisite knowledge is required.</span></span> <span data-ttu-id="af834-107">您需要在消息传递中有背景, 组件对象模型 (COM) 才能使用 MAPI 为专用邮件系统服务创建完全规模的工作组应用程序或驱动程序。</span><span class="sxs-lookup"><span data-stu-id="af834-107">You need a background in messaging and the Component Object Model (COM) to use MAPI to create full-scale workgroup applications or drivers for specialized messaging system services.</span></span>
  
<span data-ttu-id="af834-108">在开始开发工作之前, 应考虑以下有关如何使用 MAPI、登录过程以及如何创建和配置配置文件和邮件服务的信息的信息。</span><span class="sxs-lookup"><span data-stu-id="af834-108">Before starting development work, you should consider the following information about how to use MAPI, the logon process, and how profiles and message services are created and configured.</span></span>
  
<span data-ttu-id="af834-109">邮件应用程序接口 (MAPI) 是一组广泛的功能, 开发人员可使用这些函数创建启用邮件功能的应用程序。</span><span class="sxs-lookup"><span data-stu-id="af834-109">The Messaging Application Program Interface (MAPI) is an extensive set of functions that developers can use to create mail-enabled applications.</span></span> <span data-ttu-id="af834-110">完整的函数库称为 MAPI。</span><span class="sxs-lookup"><span data-stu-id="af834-110">The full function library is known as MAPI.</span></span> <span data-ttu-id="af834-111">MAPI 支持对客户端计算机上的邮件系统进行完全控制、创建和管理邮件、管理客户端邮箱、服务提供商等。</span><span class="sxs-lookup"><span data-stu-id="af834-111">MAPI enables complete control over the messaging system on the client computer, creation and management of messages, management of the client mailbox, service providers, and so on.</span></span>
  
> [!NOTE]
> <span data-ttu-id="af834-112">扩展 mapi 与 mapi 相同, 并在 mapi 文档中简称为 mapi。</span><span class="sxs-lookup"><span data-stu-id="af834-112">Extended MAPI is the same as MAPI, and is simply referred to as MAPI in the MAPI documentation.</span></span> 
  
 <span data-ttu-id="af834-113">**Simple MAPI**</span><span class="sxs-lookup"><span data-stu-id="af834-113">**Simple MAPI**</span></span>
  
<span data-ttu-id="af834-114">简单 MAPI 提供了一组功能, 使您能够向基于 Microsoft Windows 的应用程序中添加基本的邮件功能级别。</span><span class="sxs-lookup"><span data-stu-id="af834-114">Simple MAPI provides a set of functions that enables you to add a basic level of messaging functionality to Microsoft Windows-based applications.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="af834-115">microsoft outlook 2013 和 microsoft outlook 2010 支持简单 MAPI 函数 MAPISendMail。</span><span class="sxs-lookup"><span data-stu-id="af834-115">The Simple MAPI function MAPISendMail is supported by Microsoft Outlook 2013 and Microsoft Outlook 2010.</span></span> <span data-ttu-id="af834-116">Windows 中已弃用其他简单 MAPI 函数。</span><span class="sxs-lookup"><span data-stu-id="af834-116">Other Simple MAPI functions have been deprecated in Windows.</span></span> 
  

