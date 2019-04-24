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
ms.openlocfilehash: 5d94aeaa75ede85983a678f448b05ad90c1e458a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32344826"
---
# <a name="threading-in-mapi"></a><span data-ttu-id="16511-103">MAPI 中的线程</span><span class="sxs-lookup"><span data-stu-id="16511-103">Threading in MAPI</span></span>

  
  
<span data-ttu-id="16511-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="16511-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="16511-105">线程是操作系统为其分配 CPU 时间的基本实体。</span><span class="sxs-lookup"><span data-stu-id="16511-105">A thread is the basic entity to which an operating system allocates CPU time.</span></span> <span data-ttu-id="16511-106">线程具有自己的寄存器、堆栈、优先级和存储, 但会共享地址空间和处理资源 (如访问令牌)。</span><span class="sxs-lookup"><span data-stu-id="16511-106">A thread has its own registers, stack, priority, and storage, but shares an address space and process resources such as access tokens.</span></span> <span data-ttu-id="16511-107">线程也共享内存, 其中一个线程读取另一个线程已写入的内容。</span><span class="sxs-lookup"><span data-stu-id="16511-107">Threads also share memory, with one thread reading what another thread has written.</span></span>
  
<span data-ttu-id="16511-108">MAPI 客户端使用以下通用线程模型。</span><span class="sxs-lookup"><span data-stu-id="16511-108">MAPI clients use the following generic threading models.</span></span>
  
|<span data-ttu-id="16511-109">**线程模型**</span><span class="sxs-lookup"><span data-stu-id="16511-109">**Threading model**</span></span>|<span data-ttu-id="16511-110">**Description**</span><span class="sxs-lookup"><span data-stu-id="16511-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="16511-111">单线程模型</span><span class="sxs-lookup"><span data-stu-id="16511-111">Single threading model</span></span>  <br/> |<span data-ttu-id="16511-112">在单个线程上使用所有对象。</span><span class="sxs-lookup"><span data-stu-id="16511-112">All objects are used on the single thread.</span></span>  <br/> |
|<span data-ttu-id="16511-113">单元线程模型</span><span class="sxs-lookup"><span data-stu-id="16511-113">Apartment threading model</span></span>  <br/> |<span data-ttu-id="16511-114">只能在创建对象的线程上使用该对象。</span><span class="sxs-lookup"><span data-stu-id="16511-114">An object can be used only on the thread that created it.</span></span>  <br/> |
|<span data-ttu-id="16511-115">自由线程或线程方模型</span><span class="sxs-lookup"><span data-stu-id="16511-115">Free threading, or thread-party, model</span></span>  <br/> |<span data-ttu-id="16511-116">可以在任何线程上使用对象。</span><span class="sxs-lookup"><span data-stu-id="16511-116">An object can be used on any thread.</span></span>  <br/> |
   
<span data-ttu-id="16511-117">MAPI 使用自由线程模型, 支持可在任何时候在任何线程上使用的线程安全对象。</span><span class="sxs-lookup"><span data-stu-id="16511-117">MAPI uses the free threading model, supporting thread-safe objects that can be used on any thread at any time.</span></span> <span data-ttu-id="16511-118">OLE 使用单元线程模型。</span><span class="sxs-lookup"><span data-stu-id="16511-118">OLE uses the apartment threading model.</span></span> <span data-ttu-id="16511-119">单元线程模型支持当不是创建对象的线程需要使用该对象时, 必须显式转移的对象。</span><span class="sxs-lookup"><span data-stu-id="16511-119">The apartment threading model supports objects that must be explicitly transferred when a thread other than the one that created the object needs to use that object.</span></span>
  
<span data-ttu-id="16511-120">OLE 用来将对象从一个线程传输到另一个线程的机制称为封送。</span><span class="sxs-lookup"><span data-stu-id="16511-120">The mechanism that OLE uses to transfer objects from one thread to another is known as marshaling.</span></span> <span data-ttu-id="16511-121">封送处理涉及一个存根对象和一个代理对象。</span><span class="sxs-lookup"><span data-stu-id="16511-121">Marshaling involves a stub object and a proxy object.</span></span> <span data-ttu-id="16511-122">这些特殊对象打包要封送的对象中接口的参数, 将这些参数转移到另一个线程, 并在到达时将其解开。</span><span class="sxs-lookup"><span data-stu-id="16511-122">These special objects package the parameters of the interface in the object to be marshaled, transfer these parameters to the other thread, and unpackage them upon arrival.</span></span> <span data-ttu-id="16511-123">当使用 OLE "轻型" 远程过程调用或 LRPC 将自由线程的 MAPI 对象发送到另一个进程时, 会出现两个多线程模型之间的冲突。</span><span class="sxs-lookup"><span data-stu-id="16511-123">Conflict between the two multithreaded models arises when a free-threading MAPI object is sent to another process using OLE "lightweight" Remote Procedure Call, or LRPC.</span></span> <span data-ttu-id="16511-124">LRPC 通过 interposing 存根和代理接口将对象的语义从自由线程处理更改为单元线程, 在对象与其调用方之间具有单元线程行为。</span><span class="sxs-lookup"><span data-stu-id="16511-124">LRPC changes the object's semantics from free threading to apartment threading by interposing stub and proxy interfaces with apartment threading behavior between the object and its caller.</span></span> <span data-ttu-id="16511-125">对 MAPI 中导致此冲突的情况的感知可帮助客户端和服务提供商防止出现问题。</span><span class="sxs-lookup"><span data-stu-id="16511-125">Awareness of the situations in MAPI that lead to this conflict can help clients and service providers prevent problems from occurring.</span></span>
  
<span data-ttu-id="16511-126">可以访问 MAPI 对象:</span><span class="sxs-lookup"><span data-stu-id="16511-126">A MAPI object can be accessed:</span></span>
  
- <span data-ttu-id="16511-127">通过使用服务提供程序返回的接口指针或链接到客户端进程的 MAPI (如从[MAPILogonEx](mapilogonex.md)返回的 session 对象) 直接调用其方法。</span><span class="sxs-lookup"><span data-stu-id="16511-127">Through direct calls to its methods using an interface pointer returned by a service provider or MAPI linked to the client's process, such as the session object returned from [MAPILogonEx](mapilogonex.md).</span></span>
    
- <span data-ttu-id="16511-128">通过使用任何服务提供程序返回的接口指针间接调用其方法, 如从[IMAPIFolder:: CopyFolder](imapifolder-copyfolder.md)中的另一个文件夹复制的 folder 对象。</span><span class="sxs-lookup"><span data-stu-id="16511-128">Through indirect calls to its methods using an interface pointer returned by any service provider, such as the folder object copied from another folder in [IMAPIFolder::CopyFolder](imapifolder-copyfolder.md).</span></span>
    
- <span data-ttu-id="16511-129">通过回调函数 (如[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)方法) 传递给服务提供程序或**通知**调用中的 MAPI, 或者可以显示长操作进度的方法。</span><span class="sxs-lookup"><span data-stu-id="16511-129">Through a callback function, such as the [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method passed to a service provider or to MAPI in an **Advise** call or the methods that can show progress on a lengthy operation.</span></span> 
    

