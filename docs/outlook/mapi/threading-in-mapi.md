---
title: MAPI 中的线程
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 259297d2-acd7-4bc5-9a77-0df92cbfa33e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 15fb6113e9c3428cff3865307736592fd6e2b2f7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778974"
---
# <a name="threading-in-mapi"></a><span data-ttu-id="b01a1-103">MAPI 中的线程</span><span class="sxs-lookup"><span data-stu-id="b01a1-103">Threading in MAPI</span></span>

  
  
<span data-ttu-id="b01a1-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="b01a1-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="b01a1-105">线程是操作系统向其分配 CPU 时间的基本实体。</span><span class="sxs-lookup"><span data-stu-id="b01a1-105">A thread is the basic entity to which an operating system allocates CPU time.</span></span> <span data-ttu-id="b01a1-106">线程都有其自己的 register、 堆栈、 优先级和存储，但共享地址空间和处理资源如访问令牌。</span><span class="sxs-lookup"><span data-stu-id="b01a1-106">A thread has its own registers, stack, priority, and storage, but shares an address space and process resources such as access tokens.</span></span> <span data-ttu-id="b01a1-107">线程还与另一个线程具有写入中读取的一个线程共享内存。</span><span class="sxs-lookup"><span data-stu-id="b01a1-107">Threads also share memory, with one thread reading what another thread has written.</span></span>
  
<span data-ttu-id="b01a1-108">MAPI 客户端使用的以下泛型线程模型。</span><span class="sxs-lookup"><span data-stu-id="b01a1-108">MAPI clients use the following generic threading models.</span></span>
  
|<span data-ttu-id="b01a1-109">**线程模型**</span><span class="sxs-lookup"><span data-stu-id="b01a1-109">**Threading model**</span></span>|<span data-ttu-id="b01a1-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="b01a1-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b01a1-111">单线程模型</span><span class="sxs-lookup"><span data-stu-id="b01a1-111">Single threading model</span></span>  <br/> |<span data-ttu-id="b01a1-112">在单个线程中使用的所有对象。</span><span class="sxs-lookup"><span data-stu-id="b01a1-112">All objects are used on the single thread.</span></span>  <br/> |
|<span data-ttu-id="b01a1-113">单元线程模型</span><span class="sxs-lookup"><span data-stu-id="b01a1-113">Apartment threading model</span></span>  <br/> |<span data-ttu-id="b01a1-114">对象仅用于创建它的线程。</span><span class="sxs-lookup"><span data-stu-id="b01a1-114">An object can be used only on the thread that created it.</span></span>  <br/> |
|<span data-ttu-id="b01a1-115">自由线程，或线程方模型</span><span class="sxs-lookup"><span data-stu-id="b01a1-115">Free threading, or thread-party, model</span></span>  <br/> |<span data-ttu-id="b01a1-116">可在任何线程上一个对象。</span><span class="sxs-lookup"><span data-stu-id="b01a1-116">An object can be used on any thread.</span></span>  <br/> |
   
<span data-ttu-id="b01a1-117">MAPI 使用自由线程模型中，支持随时都可以在任何线程上使用的线程安全对象。</span><span class="sxs-lookup"><span data-stu-id="b01a1-117">MAPI uses the free threading model, supporting thread-safe objects that can be used on any thread at any time.</span></span> <span data-ttu-id="b01a1-118">OLE 使用单元线程模型。</span><span class="sxs-lookup"><span data-stu-id="b01a1-118">OLE uses the apartment threading model.</span></span> <span data-ttu-id="b01a1-119">单元线程模型支持之外创建对象的线程需要使用该对象时必须明确转接的对象。</span><span class="sxs-lookup"><span data-stu-id="b01a1-119">The apartment threading model supports objects that must be explicitly transferred when a thread other than the one that created the object needs to use that object.</span></span>
  
<span data-ttu-id="b01a1-120">OLE 用来将对象从一个线程传输到另一个机制称为封送处理。</span><span class="sxs-lookup"><span data-stu-id="b01a1-120">The mechanism that OLE uses to transfer objects from one thread to another is known as marshaling.</span></span> <span data-ttu-id="b01a1-121">封送涉及存根对象和代理对象。</span><span class="sxs-lookup"><span data-stu-id="b01a1-121">Marshaling involves a stub object and a proxy object.</span></span> <span data-ttu-id="b01a1-122">这些特殊对象打包对象封送，转接到其他线程，这些参数并将它们时到达解包中的接口的参数。</span><span class="sxs-lookup"><span data-stu-id="b01a1-122">These special objects package the parameters of the interface in the object to be marshaled, transfer these parameters to the other thread, and unpackage them upon arrival.</span></span> <span data-ttu-id="b01a1-123">发送到另一个进程使用 OLE"轻型"远程过程调用，或 LRPC 自由线程 MAPI 对象时，则会发生两个线程模型之间的冲突。</span><span class="sxs-lookup"><span data-stu-id="b01a1-123">Conflict between the two multithreaded models arises when a free-threading MAPI object is sent to another process using OLE "lightweight" Remote Procedure Call, or LRPC.</span></span> <span data-ttu-id="b01a1-124">LRPC 从到单元线程通过单元线程对象和其呼叫者之间的行为与在仅存根和代理接口的自由线程更改对象的语义。</span><span class="sxs-lookup"><span data-stu-id="b01a1-124">LRPC changes the object's semantics from free threading to apartment threading by interposing stub and proxy interfaces with apartment threading behavior between the object and its caller.</span></span> <span data-ttu-id="b01a1-125">认知度的 MAPI 中在此冲突导致的情况下可帮助客户端和服务提供商防止出现问题。</span><span class="sxs-lookup"><span data-stu-id="b01a1-125">Awareness of the situations in MAPI that lead to this conflict can help clients and service providers prevent problems from occurring.</span></span>
  
<span data-ttu-id="b01a1-126">可访问 MAPI 对象：</span><span class="sxs-lookup"><span data-stu-id="b01a1-126">A MAPI object can be accessed:</span></span>
  
- <span data-ttu-id="b01a1-127">通过直接调用使用界面及其方法返回的服务提供商或 MAPI 指针链接到客户端的过程，如从[MAPILogonEx](mapilogonex.md)返回会话对象。</span><span class="sxs-lookup"><span data-stu-id="b01a1-127">Through direct calls to its methods using an interface pointer returned by a service provider or MAPI linked to the client's process, such as the session object returned from [MAPILogonEx](mapilogonex.md).</span></span>
    
- <span data-ttu-id="b01a1-128">通过间接调用其方法使用返回的任何服务提供商，如 folder 对象的接口指针从另一个文件夹复制[IMAPIFolder::CopyFolder](imapifolder-copyfolder.md)中。</span><span class="sxs-lookup"><span data-stu-id="b01a1-128">Through indirect calls to its methods using an interface pointer returned by any service provider, such as the folder object copied from another folder in [IMAPIFolder::CopyFolder](imapifolder-copyfolder.md).</span></span>
    
- <span data-ttu-id="b01a1-129">通过如**Advise**呼叫或可以显示在冗长的操作的进度的方法中传递到服务提供商或 MAPI [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法的回调函数。</span><span class="sxs-lookup"><span data-stu-id="b01a1-129">Through a callback function, such as the [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method passed to a service provider or to MAPI in an **Advise** call or the methods that can show progress on a lengthy operation.</span></span> 
    

