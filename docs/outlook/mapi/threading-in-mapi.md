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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405539"
---
# <a name="threading-in-mapi"></a><span data-ttu-id="29669-103">MAPI 中的线程</span><span class="sxs-lookup"><span data-stu-id="29669-103">Threading in MAPI</span></span>

  
  
<span data-ttu-id="29669-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="29669-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="29669-105">线程是操作系统为其分配 CPU 时间的基本实体。</span><span class="sxs-lookup"><span data-stu-id="29669-105">A thread is the basic entity to which an operating system allocates CPU time.</span></span> <span data-ttu-id="29669-106">线程具有其自己的注册、堆栈、优先级和存储，但共享地址空间并处理访问令牌等资源。</span><span class="sxs-lookup"><span data-stu-id="29669-106">A thread has its own registers, stack, priority, and storage, but shares an address space and process resources such as access tokens.</span></span> <span data-ttu-id="29669-107">线程还共享内存，一个线程读取另一个线程写入了哪些内容。</span><span class="sxs-lookup"><span data-stu-id="29669-107">Threads also share memory, with one thread reading what another thread has written.</span></span>
  
<span data-ttu-id="29669-108">MAPI 客户端使用以下通用线程模型。</span><span class="sxs-lookup"><span data-stu-id="29669-108">MAPI clients use the following generic threading models.</span></span>
  
|<span data-ttu-id="29669-109">**线程模型**</span><span class="sxs-lookup"><span data-stu-id="29669-109">**Threading model**</span></span>|<span data-ttu-id="29669-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="29669-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="29669-111">单线程模型</span><span class="sxs-lookup"><span data-stu-id="29669-111">Single threading model</span></span>  <br/> |<span data-ttu-id="29669-112">所有对象都用于单个线程。</span><span class="sxs-lookup"><span data-stu-id="29669-112">All objects are used on the single thread.</span></span>  <br/> |
|<span data-ttu-id="29669-113">单元线程模型</span><span class="sxs-lookup"><span data-stu-id="29669-113">Apartment threading model</span></span>  <br/> |<span data-ttu-id="29669-114">对象只能在创建该对象的线程上使用。</span><span class="sxs-lookup"><span data-stu-id="29669-114">An object can be used only on the thread that created it.</span></span>  <br/> |
|<span data-ttu-id="29669-115">自由线程或线程方模型</span><span class="sxs-lookup"><span data-stu-id="29669-115">Free threading, or thread-party, model</span></span>  <br/> |<span data-ttu-id="29669-116">对象可在任何线程上使用。</span><span class="sxs-lookup"><span data-stu-id="29669-116">An object can be used on any thread.</span></span>  <br/> |
   
<span data-ttu-id="29669-117">MAPI 使用自由线程模型，支持随时可在任何线程中使用的线程安全对象。</span><span class="sxs-lookup"><span data-stu-id="29669-117">MAPI uses the free threading model, supporting thread-safe objects that can be used on any thread at any time.</span></span> <span data-ttu-id="29669-118">OLE 使用单元线程模型。</span><span class="sxs-lookup"><span data-stu-id="29669-118">OLE uses the apartment threading model.</span></span> <span data-ttu-id="29669-119">单元线程模型支持当创建对象的线程外的其他线程需要使用该对象时必须显式传输的对象。</span><span class="sxs-lookup"><span data-stu-id="29669-119">The apartment threading model supports objects that must be explicitly transferred when a thread other than the one that created the object needs to use that object.</span></span>
  
<span data-ttu-id="29669-120">OLE 用于将对象从一个线程转移到另一个线程的机制称为封送。</span><span class="sxs-lookup"><span data-stu-id="29669-120">The mechanism that OLE uses to transfer objects from one thread to another is known as marshaling.</span></span> <span data-ttu-id="29669-121">封送涉及存根对象和代理对象。</span><span class="sxs-lookup"><span data-stu-id="29669-121">Marshaling involves a stub object and a proxy object.</span></span> <span data-ttu-id="29669-122">这些特殊对象打包要封送的对象中的接口参数，将这些参数传输给另一个线程，在到达时将其解包。</span><span class="sxs-lookup"><span data-stu-id="29669-122">These special objects package the parameters of the interface in the object to be marshaled, transfer these parameters to the other thread, and unpackage them upon arrival.</span></span> <span data-ttu-id="29669-123">当使用 OLE"轻型"远程过程调用或 LRPC 将自由线程 MAPI 对象发送到另一个进程时，两个多线程模型之间会出现冲突。</span><span class="sxs-lookup"><span data-stu-id="29669-123">Conflict between the two multithreaded models arises when a free-threading MAPI object is sent to another process using OLE "lightweight" Remote Procedure Call, or LRPC.</span></span> <span data-ttu-id="29669-124">LRPC 通过将存根和代理接口与对象及其调用方之间的单元线程行为进行互置，将对象的语义从自由线程更改到单元线程。</span><span class="sxs-lookup"><span data-stu-id="29669-124">LRPC changes the object's semantics from free threading to apartment threading by interposing stub and proxy interfaces with apartment threading behavior between the object and its caller.</span></span> <span data-ttu-id="29669-125">了解 MAPI 中导致此冲突的情况可帮助客户端和服务提供商防止出现问题。</span><span class="sxs-lookup"><span data-stu-id="29669-125">Awareness of the situations in MAPI that lead to this conflict can help clients and service providers prevent problems from occurring.</span></span>
  
<span data-ttu-id="29669-126">可以访问 MAPI 对象：</span><span class="sxs-lookup"><span data-stu-id="29669-126">A MAPI object can be accessed:</span></span>
  
- <span data-ttu-id="29669-127">通过使用服务提供商返回的接口指针或链接到客户端进程的 MAPI（如 [MAPILogonEx](mapilogonex.md)返回的会话对象）直接调用其方法。</span><span class="sxs-lookup"><span data-stu-id="29669-127">Through direct calls to its methods using an interface pointer returned by a service provider or MAPI linked to the client's process, such as the session object returned from [MAPILogonEx](mapilogonex.md).</span></span>
    
- <span data-ttu-id="29669-128">通过使用由任何服务提供商返回的接口指针（例如从 [IMAPIFolder：：CopyFolder](imapifolder-copyfolder.md)中的另一个文件夹复制的文件夹对象）间接调用其方法。</span><span class="sxs-lookup"><span data-stu-id="29669-128">Through indirect calls to its methods using an interface pointer returned by any service provider, such as the folder object copied from another folder in [IMAPIFolder::CopyFolder](imapifolder-copyfolder.md).</span></span>
    
- <span data-ttu-id="29669-129">通过回调函数（如 [IMAPIAdviseSink：：OnNotify](imapiadvisesink-onnotify.md) 方法传递到服务提供商或 **Advise** 调用中的 MAPI）或可以显示长时间操作进度的方法。</span><span class="sxs-lookup"><span data-stu-id="29669-129">Through a callback function, such as the [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method passed to a service provider or to MAPI in an **Advise** call or the methods that can show progress on a lengthy operation.</span></span> 
    

