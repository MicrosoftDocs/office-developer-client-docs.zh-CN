---
title: 从 Windows 服务调用 MAPI
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: debf7ec3-e9f9-4912-b9a2-fc0953a56a01
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 6465b2d24c3a38da40f2d1e6df79c2fa256b64b0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774611"
---
# <a name="calling-mapi-from-windows-services"></a><span data-ttu-id="18710-103">从 Windows 服务调用 MAPI</span><span class="sxs-lookup"><span data-stu-id="18710-103">Calling MAPI from Windows Services</span></span>

  
  
<span data-ttu-id="18710-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="18710-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="18710-105">若要启用 MAPI 客户端应用程序作为 Windows 服务运行与 MAPI 兼容的服务提供商写入，MAPI 施加一些限制和要求。</span><span class="sxs-lookup"><span data-stu-id="18710-105">To enable MAPI client applications that are written as Windows services to operate with MAPI-compliant service providers, MAPI imposes several limitations and requirements.</span></span>
  
<span data-ttu-id="18710-106">MAPI 客户端具有以下限制：</span><span class="sxs-lookup"><span data-stu-id="18710-106">MAPI clients have the following limitations:</span></span>
  
- <span data-ttu-id="18710-107">他们无法允许的用户界面。</span><span class="sxs-lookup"><span data-stu-id="18710-107">They cannot allow a user interface.</span></span>
    
- <span data-ttu-id="18710-108">它们可以发送消息，只能通过紧密耦合的消息存储和传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="18710-108">They can send messages only through a tightly coupled message store and transport provider.</span></span> <span data-ttu-id="18710-109">此外，MAPI 客户端可以发送和接收邮件使用仅在 Microsoft Exchange Server 或其他基于服务器的传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="18710-109">In addition, MAPI clients can send and receive messages by using only the Microsoft Exchange Server or another server-based transport provider.</span></span> <span data-ttu-id="18710-110">客户端应用程序和 MAPI 后台处理程序之间的身份和安全问题，因为大多数传输提供程序不支持服务中。</span><span class="sxs-lookup"><span data-stu-id="18710-110">Because of identity and security issues between client applications and the MAPI spooler, most transport providers are not supported in a service.</span></span> 
    
<span data-ttu-id="18710-111">所有 MAPI 客户端应用程序，它们 Windows 服务，以实现是否必须都调用[MAPIInitialize](mapiinitialize.md)函数初始化 MAPI 库。</span><span class="sxs-lookup"><span data-stu-id="18710-111">All MAPI client applications, whether they are implemented as Windows services, must call the [MAPIInitialize](mapiinitialize.md) function to initialize the MAPI libraries.</span></span> <span data-ttu-id="18710-112">对[OleInitialize](http://msdn.microsoft.com/en-us/library/ms690134%28v=VS.85%29.aspx)函数的调用也是使用 OLE 库所必需的。</span><span class="sxs-lookup"><span data-stu-id="18710-112">A call to the [OleInitialize](http://msdn.microsoft.com/en-us/library/ms690134%28v=VS.85%29.aspx) function is also necessary to use the OLE libraries.</span></span> <span data-ttu-id="18710-113">[MAPIInitialize](mapiinitialize.md)和[OleInitialize](http://msdn.microsoft.com/en-us/library/ms690134%28v=VS.85%29.aspx)打给[CoInitialize](http://msdn.microsoft.com/en-us/library/ms678543%28VS.85%29.aspx)函数初始化组件对象模型 (COM) 库。</span><span class="sxs-lookup"><span data-stu-id="18710-113">Both [MAPIInitialize](mapiinitialize.md) and [OleInitialize](http://msdn.microsoft.com/en-us/library/ms690134%28v=VS.85%29.aspx) make calls to the [CoInitialize](http://msdn.microsoft.com/en-us/library/ms678543%28VS.85%29.aspx) function to initialize the Component Object Model (COM) libraries.</span></span> <span data-ttu-id="18710-114">在传递给[MAPIInitialize](mapiinitialize.md) [MAPIINIT_0](mapiinit_0.md)结构的**ulFlags**成员和_ulFlags_参数传递给[MAPILogonEx](mapilogonex.md)中，服务的客户端必须设置一个特殊的标志，MAPI_NT_SERVICE，若要向其特殊实现的 MAPI 的函数。</span><span class="sxs-lookup"><span data-stu-id="18710-114">Clients that are services must set a special flag, MAPI_NT_SERVICE, in the **ulFlags** member of the [MAPIINIT_0](mapiinit_0.md) structure that is passed to [MAPIInitialize](mapiinitialize.md) and in the  _ulFlags_ parameter that is passed to the [MAPILogonEx](mapilogonex.md) function to inform MAPI of their special implementation.</span></span> 
  
<span data-ttu-id="18710-115">MAPI 客户端的编写作为 Windows 服务并与 MAPI 客户端界面写入具有额外的要求。</span><span class="sxs-lookup"><span data-stu-id="18710-115">MAPI clients that are written as Windows services and written with the MAPI client interface have an additional requirement.</span></span> <span data-ttu-id="18710-116">必须对[MAPILogonEx](mapilogonex.md)的调用中设置 MAPI_NO_MAIL 标志。</span><span class="sxs-lookup"><span data-stu-id="18710-116">They must set the MAPI_NO_MAIL flag in the call to [MAPILogonEx](mapilogonex.md).</span></span> <span data-ttu-id="18710-117">其他类型的客户端不必设置进行登录的标志，因为它会自动设置的 MAPI。</span><span class="sxs-lookup"><span data-stu-id="18710-117">Other types of clients do not have to set a flag for logon because it is automatically set by MAPI.</span></span>
  
<span data-ttu-id="18710-118">若要处理初始化线程中的邮件，为服务实现 MAPI 客户端执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="18710-118">To handle messages in an initialization thread, a MAPI client that is implemented as a service does the following:</span></span>
  
1. <span data-ttu-id="18710-119">调用[MsgWaitForMultipleObjects](http://msdn.microsoft.com/en-us/library/ms684242%28VS.85%29.aspx)函数时的主线程块。</span><span class="sxs-lookup"><span data-stu-id="18710-119">Calls the [MsgWaitForMultipleObjects](http://msdn.microsoft.com/en-us/library/ms684242%28VS.85%29.aspx) function when the main thread blocks.</span></span> 
    
2. <span data-ttu-id="18710-120">调用 Windows 函数处理邮件时[MsgWaitForMultipleObjects](http://msdn.microsoft.com/en-us/library/ms684242%28VS.85%29.aspx)返回_nCount_参数的值的总和的[GetMessage](http://msdn.microsoft.com/en-us/library/ms644936%28VS.85%29.aspx)、 [TranslateMessage](http://msdn.microsoft.com/en-us/library/ms644955%28VS.85%29.aspx)和[DispatchMessage](http://msdn.microsoft.com/en-us/library/ms644934%28VS.85%29.aspx)序列和**WAIT_OBJECT_0**，表示一条消息队列中的值。</span><span class="sxs-lookup"><span data-stu-id="18710-120">Calls the [GetMessage](http://msdn.microsoft.com/en-us/library/ms644936%28VS.85%29.aspx), [TranslateMessage](http://msdn.microsoft.com/en-us/library/ms644955%28VS.85%29.aspx), and [DispatchMessage](http://msdn.microsoft.com/en-us/library/ms644934%28VS.85%29.aspx) sequence of Windows functions to handle the message when [MsgWaitForMultipleObjects](http://msdn.microsoft.com/en-us/library/ms684242%28VS.85%29.aspx) returns the sum of the value of the  _nCount_ parameter and the value of **WAIT_OBJECT_0**, which indicates that a message is in the queue.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="18710-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="18710-121">See also</span></span>



[<span data-ttu-id="18710-122">MAPIInitialize</span><span class="sxs-lookup"><span data-stu-id="18710-122">MAPIInitialize</span></span>](mapiinitialize.md)
  
[<span data-ttu-id="18710-123">MAPIINIT_0</span><span class="sxs-lookup"><span data-stu-id="18710-123">MAPIINIT_0</span></span>](mapiinit_0.md)
  
[<span data-ttu-id="18710-124">MAPILogonEx</span><span class="sxs-lookup"><span data-stu-id="18710-124">MAPILogonEx</span></span>](mapilogonex.md)


[<span data-ttu-id="18710-125">操作环境问题</span><span class="sxs-lookup"><span data-stu-id="18710-125">Operating Environment Issues</span></span>](operating-environment-issues.md)

