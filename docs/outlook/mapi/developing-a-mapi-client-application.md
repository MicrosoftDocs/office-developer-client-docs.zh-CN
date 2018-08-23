---
title: 开发 MAPI 客户端应用程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: bcb59b08-e6d7-4739-8cb5-e545bd0d478f
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: bffcfdd6d688c483655b97d61075b147430e3fcc
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22564974"
---
# <a name="developing-a-mapi-client-application"></a><span data-ttu-id="27956-103">开发 MAPI 客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="27956-103">Developing a MAPI Client Application</span></span>

  
  
<span data-ttu-id="27956-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="27956-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="27956-105">MAPI 客户端应用程序是编写的面向对象的 MAPI 客户端接口。</span><span class="sxs-lookup"><span data-stu-id="27956-105">MAPI client applications are written with the object oriented MAPI client interface.</span></span> <span data-ttu-id="27956-106">MAPI 客户端与通过 MAPI 子系统和 MAPI 兼容的服务提供商的一个或多个邮件系统进行交互。</span><span class="sxs-lookup"><span data-stu-id="27956-106">MAPI clients interact with one or more messaging systems through the MAPI subsystem and MAPI-compliant service providers.</span></span> <span data-ttu-id="27956-107">多种不同的方式; 中可能发生这种交互客户端应用程序中没有巨大的各种。</span><span class="sxs-lookup"><span data-stu-id="27956-107">This interaction can occur in many different ways; there is an enormous variety in client applications.</span></span> <span data-ttu-id="27956-108">大多数客户端的消息客户端，可以将集成到其已建立的功能集中消息或执行消息作为其主要功能。</span><span class="sxs-lookup"><span data-stu-id="27956-108">Most clients are messaging clients, either integrating messaging into their established feature set or performing messaging as their primary feature.</span></span> <span data-ttu-id="27956-109">MAPI 客户端可能提供其他功能包括配置文件管理或通讯簿和消息存储管理。</span><span class="sxs-lookup"><span data-stu-id="27956-109">Other features that MAPI clients might provide include profile administration or address book and message store management.</span></span>
  
<span data-ttu-id="27956-110">所有消息客户端初始化 MAPI 库，并开始与 MAPI 子系统**会话**。</span><span class="sxs-lookup"><span data-stu-id="27956-110">All messaging clients initialize the MAPI libraries and start a **session** with the MAPI subsystem.</span></span> <span data-ttu-id="27956-111">有关详细信息，请参阅[使用会话访问对象](accessing-objects-by-using-the-session.md)。</span><span class="sxs-lookup"><span data-stu-id="27956-111">For more information, see [Accessing Objects by Using the Session](accessing-objects-by-using-the-session.md).</span></span> <span data-ttu-id="27956-112">在建立会话后，客户端可以：</span><span class="sxs-lookup"><span data-stu-id="27956-112">After a session has been established, a client can:</span></span>
  
- <span data-ttu-id="27956-113">处理传出邮件，包括答复，转发邮件和重新传输。</span><span class="sxs-lookup"><span data-stu-id="27956-113">Handle outgoing messages, including replies, forwarded messages, and retransmissions.</span></span>
    
- <span data-ttu-id="27956-114">处理传入消息。</span><span class="sxs-lookup"><span data-stu-id="27956-114">Handle incoming messages.</span></span>
    
- <span data-ttu-id="27956-115">处理通过打开文件夹和邮件、 创建、 修改、 复制和发送邮件、 跟踪对话和搜索一个或多个文件夹的邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="27956-115">Handle the message store by opening folders and messages, creating, modifying, copying, and sending messages, tracking conversations, and searching one or more folders.</span></span>
    
- <span data-ttu-id="27956-116">创建和修改收件人、 查找条目，并将遍历容器层次结构通过以下方式处理通讯簿。</span><span class="sxs-lookup"><span data-stu-id="27956-116">Handle the address book by creating and modifying recipients, locating entries, and traversing the container hierarchy.</span></span>
    
- <span data-ttu-id="27956-117">通过执行重新配置、 设置选项和传输顺序，并根据需要发送邮件处理传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="27956-117">Handle a transport provider by performing reconfiguration, setting options and transport order, and sending messages on demand.</span></span>
    
- <span data-ttu-id="27956-118">处理事件通知。</span><span class="sxs-lookup"><span data-stu-id="27956-118">Handle event notification.</span></span>
    
- <span data-ttu-id="27956-119">处理窗体。</span><span class="sxs-lookup"><span data-stu-id="27956-119">Handle forms.</span></span>
    
- <span data-ttu-id="27956-120">处理配置文件和消息服务。</span><span class="sxs-lookup"><span data-stu-id="27956-120">Handle profiles and message services.</span></span>
    
<span data-ttu-id="27956-121">使用本节中的主题可帮助您实现这些基本任务和特定功能使您的 MAPI 客户端唯一。</span><span class="sxs-lookup"><span data-stu-id="27956-121">Use the topics in this section to help you implement these basic tasks and the specific features that will make your MAPI client unique.</span></span>
  

