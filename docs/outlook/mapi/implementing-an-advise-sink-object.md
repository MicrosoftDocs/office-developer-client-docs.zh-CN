---
title: 实现通知接收器对象
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 7461c4f6-7030-4ba2-ada4-26ebfbbfa001
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b457fce208923ce01686812f20031e365842ccd8
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22593674"
---
# <a name="implementing-an-advise-sink-object"></a><span data-ttu-id="cc242-103">实现通知接收器对象</span><span class="sxs-lookup"><span data-stu-id="cc242-103">Implementing an Advise Sink Object</span></span>

  
  
<span data-ttu-id="cc242-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cc242-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cc242-105">客户端可以实现自己 advise 接收器对象也可以使用的实用工具函数， [HrAllocAdviseSink](hrallocadvisesink.md)。</span><span class="sxs-lookup"><span data-stu-id="cc242-105">A client can either implement its own advise sink objects or use a utility function, [HrAllocAdviseSink](hrallocadvisesink.md).</span></span> <span data-ttu-id="cc242-106">**HrAllocAdviseSink**调用的回调函数的**OnNotify**实现用来创建 advise 接收器对象。</span><span class="sxs-lookup"><span data-stu-id="cc242-106">**HrAllocAdviseSink** creates an advise sink object with an implementation of **OnNotify** that invokes a callback function.</span></span> 
  
<span data-ttu-id="cc242-107">有其优点和缺点使用**HrAllocAdviseSink**。</span><span class="sxs-lookup"><span data-stu-id="cc242-107">There are advantages and disadvantages to using **HrAllocAdviseSink**.</span></span> <span data-ttu-id="cc242-108">它可以保存的工作，但它提供无法控制它创建 advise 接收器对象进行引用计数。</span><span class="sxs-lookup"><span data-stu-id="cc242-108">It can save work, but it provides no control over reference counting the advise sink object that it creates.</span></span> <span data-ttu-id="cc242-109">因此，客户端的需要来仔细控制其通知接收器版本或具有其通知接收器和其他客户端对象之间的依赖关系的应构造自己**IMAPIAdviseSink**实现并避免使用**HrAllocAdviseSink**完全忽略。</span><span class="sxs-lookup"><span data-stu-id="cc242-109">Therefore, clients that need to carefully control their advise sink's release or that have interdependencies between their advise sink and another client object should construct their own **IMAPIAdviseSink** implementation and avoid using **HrAllocAdviseSink** altogether.</span></span> 
  
<span data-ttu-id="cc242-110">客户端实现自己通知接收器应使独立对象不相关的或依赖于以便消除潜在的问题，引用计数和对象版本中的任何其他对象。</span><span class="sxs-lookup"><span data-stu-id="cc242-110">A client implementing its own advise sink should make it an independent object not related to or dependent upon any other objects so as to eliminate potential complications in reference counting and object release.</span></span> <span data-ttu-id="cc242-111">但是，如果您必须实现通知接收器另一个对象的一部分或包括指向后向另一个对象的数据成员作为指针，它建议的维护两个单独的引用计数： 一个用于通知接收器，另一个用于所引用的对象建议接收器。</span><span class="sxs-lookup"><span data-stu-id="cc242-111">However, if you must implement your advise sink as part of another object or include a back pointer to another object as a data member, it is recommended that two separate reference counts be maintained: one for the object referenced by the advise sink and one for the advise sink.</span></span> 
  
<span data-ttu-id="cc242-112">当引用的对象的引用计数降为零时，所有其方法可能会失败和可以销毁其 vtable，但通知接收器的内存必须保持不变，直到后引用计数还会为零。</span><span class="sxs-lookup"><span data-stu-id="cc242-112">When the reference count of the referenced object falls to zero, all of its methods can fail and its vtable can be destroyed, but the memory for the advise sink must remain intact until after its reference count also falls to zero.</span></span> <span data-ttu-id="cc242-113">这意味着通知接收器**释放**方法必须引用计数递减并完成时的计数为零时销毁的对象。</span><span class="sxs-lookup"><span data-stu-id="cc242-113">This means that the advise sink's **Release** method must decrement its reference count and finish destroying the object when that count reaches zero.</span></span> <span data-ttu-id="cc242-114">如果两个单独的引用计数不会被保留，它可以轻松地无意大对象的**发布**过程的一部分销毁通知接收器。</span><span class="sxs-lookup"><span data-stu-id="cc242-114">If two separate reference counts are not maintained, it would be easy to inadvertently destroy the advise sink as part of the encompassing object's **Release** process.</span></span> 
  
<span data-ttu-id="cc242-115">使用**HrAllocAdviseSink**来实现通知接收器的客户端必须同样不要将其回调函数为在另一个 advise 接收器对象的方法。</span><span class="sxs-lookup"><span data-stu-id="cc242-115">Clients using **HrAllocAdviseSink** to implement an advise sink must be equally careful not to include their callback function as a method in another advise sink object.</span></span> <span data-ttu-id="cc242-116">对于 c + + 客户端，它很容易执行此操作，并作为参数传递_此_指针。</span><span class="sxs-lookup"><span data-stu-id="cc242-116">For C++ clients, it is tempting to do this and pass the  _this_ pointer as a parameter.</span></span> <span data-ttu-id="cc242-117">这是危险策略，因为客户端通常释放对象，当其引用计数为零时。</span><span class="sxs-lookup"><span data-stu-id="cc242-117">This is a dangerous strategy because clients typically free an object when its reference count reaches zero.</span></span> <span data-ttu-id="cc242-118">释放 advise 接收器对象的内存，将会呈现_this_指针无效。</span><span class="sxs-lookup"><span data-stu-id="cc242-118">Freeing the memory for the advise sink object would render the  _this_ pointer invalid.</span></span> 
  
<span data-ttu-id="cc242-119">根据事件和 advise 源类型， **OnNotify**方法可以处理事件以各种方式。</span><span class="sxs-lookup"><span data-stu-id="cc242-119">Depending on the type of event and the advise source, your **OnNotify** method can handle events in various ways.</span></span> <span data-ttu-id="cc242-120">下表提供了建议中如何处理的某些标准事件。</span><span class="sxs-lookup"><span data-stu-id="cc242-120">The following table offers suggestions in how to handle some of the standard events.</span></span> 
  
|<span data-ttu-id="cc242-121">**事件的类型**</span><span class="sxs-lookup"><span data-stu-id="cc242-121">**Type of event**</span></span>|<span data-ttu-id="cc242-122">**在 OnNotify 处理**</span><span class="sxs-lookup"><span data-stu-id="cc242-122">**Handling in OnNotify**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cc242-123">移动对象</span><span class="sxs-lookup"><span data-stu-id="cc242-123">Object moved</span></span>  <br/> |<span data-ttu-id="cc242-124">如果移动的对象的原始父与新父级，更新文件夹或通讯簿容器层次结构中最高视图开头。</span><span class="sxs-lookup"><span data-stu-id="cc242-124">If the moved object's original parent is related to the new parent, update the view beginning with the folder or address book container highest in the hierarchy.</span></span> <span data-ttu-id="cc242-125">如果两个父容器无关，更新这两个其视图。</span><span class="sxs-lookup"><span data-stu-id="cc242-125">If the two parent containers are unrelated, update both of their views.</span></span>  <br/> |
|<span data-ttu-id="cc242-126">新的邮件</span><span class="sxs-lookup"><span data-stu-id="cc242-126">New message</span></span>  <br/> |<span data-ttu-id="cc242-127">更改通知的一个或多个新邮件到达用户的用户界面。</span><span class="sxs-lookup"><span data-stu-id="cc242-127">Change the user interface to inform the user of the arrival of one or more new messages.</span></span> <span data-ttu-id="cc242-128">当前视图中放置的接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="cc242-128">Place the receive folder in the current view.</span></span>  <br/> |
|<span data-ttu-id="cc242-129">Error</span><span class="sxs-lookup"><span data-stu-id="cc242-129">Error</span></span>  <br/> |<span data-ttu-id="cc242-130">对于除会话的所有对象，如果必要和返回记录错误。</span><span class="sxs-lookup"><span data-stu-id="cc242-130">For all objects except the session, log the error if necessary and return.</span></span> <span data-ttu-id="cc242-131">对于会话对象中，先注销如果可能。</span><span class="sxs-lookup"><span data-stu-id="cc242-131">For the session object, log off if possible.</span></span>  <br/> |
|<span data-ttu-id="cc242-132">搜索完成</span><span class="sxs-lookup"><span data-stu-id="cc242-132">Search complete</span></span>  <br/> |<span data-ttu-id="cc242-133">没有必要的处理。</span><span class="sxs-lookup"><span data-stu-id="cc242-133">No processing necessary.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="cc242-134">应重入通知处理程序。</span><span class="sxs-lookup"><span data-stu-id="cc242-134">Notification handlers should be reentrant.</span></span> 
  

