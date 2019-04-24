---
title: 从 Windows 服务调用 MAPI
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: debf7ec3-e9f9-4912-b9a2-fc0953a56a01
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: a606b8bf82ce4c06c8e55f6e4df94220bc67501d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32318101"
---
# <a name="calling-mapi-from-windows-services"></a><span data-ttu-id="9dbf5-103">从 Windows 服务调用 MAPI</span><span class="sxs-lookup"><span data-stu-id="9dbf5-103">Calling MAPI from Windows Services</span></span>

  
  
<span data-ttu-id="9dbf5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9dbf5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9dbf5-105">若要启用作为 Windows 服务编写的 mapi 客户端应用程序以使用符合 MAPI 的服务提供程序运行, mapi 有多种限制和要求。</span><span class="sxs-lookup"><span data-stu-id="9dbf5-105">To enable MAPI client applications that are written as Windows services to operate with MAPI-compliant service providers, MAPI imposes several limitations and requirements.</span></span>
  
<span data-ttu-id="9dbf5-106">MAPI 客户端具有以下限制:</span><span class="sxs-lookup"><span data-stu-id="9dbf5-106">MAPI clients have the following limitations:</span></span>
  
- <span data-ttu-id="9dbf5-107">无法允许用户界面。</span><span class="sxs-lookup"><span data-stu-id="9dbf5-107">They cannot allow a user interface.</span></span>
    
- <span data-ttu-id="9dbf5-108">他们只能通过紧密耦合的邮件存储和传输提供程序发送邮件。</span><span class="sxs-lookup"><span data-stu-id="9dbf5-108">They can send messages only through a tightly coupled message store and transport provider.</span></span> <span data-ttu-id="9dbf5-109">此外, MAPI 客户端可以仅使用 Microsoft Exchange Server 或其他基于服务器的传输提供程序发送和接收邮件。</span><span class="sxs-lookup"><span data-stu-id="9dbf5-109">In addition, MAPI clients can send and receive messages by using only the Microsoft Exchange Server or another server-based transport provider.</span></span> <span data-ttu-id="9dbf5-110">由于客户端应用程序和 MAPI 后台处理程序之间的标识和安全问题, 在服务中不支持大多数传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="9dbf5-110">Because of identity and security issues between client applications and the MAPI spooler, most transport providers are not supported in a service.</span></span> 
    
<span data-ttu-id="9dbf5-111">所有 MAPI 客户端应用程序 (无论是作为 Windows 服务实现的) 都必须调用[MAPIInitialize](mapiinitialize.md)函数来初始化 mapi 库。</span><span class="sxs-lookup"><span data-stu-id="9dbf5-111">All MAPI client applications, whether they are implemented as Windows services, must call the [MAPIInitialize](mapiinitialize.md) function to initialize the MAPI libraries.</span></span> <span data-ttu-id="9dbf5-112">若要使用 OLE 库, 还需要调用[OleInitialize](https://msdn.microsoft.com/library/ms690134%28v=VS.85%29.aspx)函数。</span><span class="sxs-lookup"><span data-stu-id="9dbf5-112">A call to the [OleInitialize](https://msdn.microsoft.com/library/ms690134%28v=VS.85%29.aspx) function is also necessary to use the OLE libraries.</span></span> <span data-ttu-id="9dbf5-113">[MAPIInitialize](mapiinitialize.md)和[OleInitialize](https://msdn.microsoft.com/library/ms690134%28v=VS.85%29.aspx)调用[CoInitialize](https://msdn.microsoft.com/library/ms678543%28VS.85%29.aspx)函数以初始化组件对象模型 (COM) 库。</span><span class="sxs-lookup"><span data-stu-id="9dbf5-113">Both [MAPIInitialize](mapiinitialize.md) and [OleInitialize](https://msdn.microsoft.com/library/ms690134%28v=VS.85%29.aspx) make calls to the [CoInitialize](https://msdn.microsoft.com/library/ms678543%28VS.85%29.aspx) function to initialize the Component Object Model (COM) libraries.</span></span> <span data-ttu-id="9dbf5-114">作为服务的客户端必须在[MAPIINIT_0](mapiinit_0.md)结构的**ulFlags**成员中设置一个特殊标志 MAPI_NT_SERVICE, 该标志将传递给[MAPIInitialize](mapiinitialize.md) , 并在传递到[ulFlags](mapilogonex.md)的_MAPILogonEx_参数中进行设置。用于通知 MAPI 其特殊实现的函数。</span><span class="sxs-lookup"><span data-stu-id="9dbf5-114">Clients that are services must set a special flag, MAPI_NT_SERVICE, in the **ulFlags** member of the [MAPIINIT_0](mapiinit_0.md) structure that is passed to [MAPIInitialize](mapiinitialize.md) and in the  _ulFlags_ parameter that is passed to the [MAPILogonEx](mapilogonex.md) function to inform MAPI of their special implementation.</span></span> 
  
<span data-ttu-id="9dbf5-115">作为 Windows 服务编写并使用 mapi 客户端接口写入的 mapi 客户端具有其他要求。</span><span class="sxs-lookup"><span data-stu-id="9dbf5-115">MAPI clients that are written as Windows services and written with the MAPI client interface have an additional requirement.</span></span> <span data-ttu-id="9dbf5-116">必须在对[MAPILogonEx](mapilogonex.md)的调用中设置 MAPI_NO_MAIL 标志。</span><span class="sxs-lookup"><span data-stu-id="9dbf5-116">They must set the MAPI_NO_MAIL flag in the call to [MAPILogonEx](mapilogonex.md).</span></span> <span data-ttu-id="9dbf5-117">其他类型的客户端无需设置用于登录的标志, 因为它是由 MAPI 自动设置的。</span><span class="sxs-lookup"><span data-stu-id="9dbf5-117">Other types of clients do not have to set a flag for logon because it is automatically set by MAPI.</span></span>
  
<span data-ttu-id="9dbf5-118">若要在初始化线程中处理邮件, 作为服务实现的 MAPI 客户端将执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="9dbf5-118">To handle messages in an initialization thread, a MAPI client that is implemented as a service does the following:</span></span>
  
1. <span data-ttu-id="9dbf5-119">在主线程阻塞时调用[MsgWaitForMultipleObjects](https://msdn.microsoft.com/library/ms684242%28VS.85%29.aspx)函数。</span><span class="sxs-lookup"><span data-stu-id="9dbf5-119">Calls the [MsgWaitForMultipleObjects](https://msdn.microsoft.com/library/ms684242%28VS.85%29.aspx) function when the main thread blocks.</span></span> 
    
2. <span data-ttu-id="9dbf5-120">调用 Windows 函数的[GetMessage](https://msdn.microsoft.com/library/ms644936%28VS.85%29.aspx)、 [TranslateMessage](https://msdn.microsoft.com/library/ms644955%28VS.85%29.aspx)和[DispatchMessage](https://msdn.microsoft.com/library/ms644934%28VS.85%29.aspx)序列, 以处理当[MsgWaitForMultipleObjects](https://msdn.microsoft.com/library/ms684242%28VS.85%29.aspx)返回_nCount_参数值的总和和**WAIT_OBJECT_0**的值, 该值指示邮件在队列中。</span><span class="sxs-lookup"><span data-stu-id="9dbf5-120">Calls the [GetMessage](https://msdn.microsoft.com/library/ms644936%28VS.85%29.aspx), [TranslateMessage](https://msdn.microsoft.com/library/ms644955%28VS.85%29.aspx), and [DispatchMessage](https://msdn.microsoft.com/library/ms644934%28VS.85%29.aspx) sequence of Windows functions to handle the message when [MsgWaitForMultipleObjects](https://msdn.microsoft.com/library/ms684242%28VS.85%29.aspx) returns the sum of the value of the  _nCount_ parameter and the value of **WAIT_OBJECT_0**, which indicates that a message is in the queue.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="9dbf5-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9dbf5-121">See also</span></span>



[<span data-ttu-id="9dbf5-122">MAPIInitialize</span><span class="sxs-lookup"><span data-stu-id="9dbf5-122">MAPIInitialize</span></span>](mapiinitialize.md)
  
[<span data-ttu-id="9dbf5-123">MAPIINIT_0</span><span class="sxs-lookup"><span data-stu-id="9dbf5-123">MAPIINIT_0</span></span>](mapiinit_0.md)
  
[<span data-ttu-id="9dbf5-124">MAPILogonEx</span><span class="sxs-lookup"><span data-stu-id="9dbf5-124">MAPILogonEx</span></span>](mapilogonex.md)


[<span data-ttu-id="9dbf5-125">操作环境问题</span><span class="sxs-lookup"><span data-stu-id="9dbf5-125">Operating Environment Issues</span></span>](operating-environment-issues.md)

