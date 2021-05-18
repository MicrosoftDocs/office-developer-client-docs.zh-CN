---
title: 实现 Advise Sink 对象
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 7461c4f6-7030-4ba2-ada4-26ebfbbfa001
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ecaad65d28f74b843b86ca82dab9a833ade77363
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412105"
---
# <a name="implementing-an-advise-sink-object"></a><span data-ttu-id="072fa-103">实现 Advise Sink 对象</span><span class="sxs-lookup"><span data-stu-id="072fa-103">Implementing an Advise Sink Object</span></span>

  
  
<span data-ttu-id="072fa-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="072fa-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="072fa-105">客户端可以实施自己的建议接收器对象或使用实用工具函数 [HrAllocAdviseSink](hrallocadvisesink.md)。</span><span class="sxs-lookup"><span data-stu-id="072fa-105">A client can either implement its own advise sink objects or use a utility function, [HrAllocAdviseSink](hrallocadvisesink.md).</span></span> <span data-ttu-id="072fa-106">**HrAllocAdviseSink** 使用调用回调函数的 **OnNotify** 实现创建建议接收器对象。</span><span class="sxs-lookup"><span data-stu-id="072fa-106">**HrAllocAdviseSink** creates an advise sink object with an implementation of **OnNotify** that invokes a callback function.</span></span> 
  
<span data-ttu-id="072fa-107">使用 **HrAllocAdviseSink 有一些优缺点**。</span><span class="sxs-lookup"><span data-stu-id="072fa-107">There are advantages and disadvantages to using **HrAllocAdviseSink**.</span></span> <span data-ttu-id="072fa-108">它可以省去工作，但无法控制对它创建的通知接收对象的引用计数。</span><span class="sxs-lookup"><span data-stu-id="072fa-108">It can save work, but it provides no control over reference counting the advise sink object that it creates.</span></span> <span data-ttu-id="072fa-109">因此，需要仔细控制其建议接收器的发布或在通知接收器与另一个客户端对象之间具有依赖关系的客户应构建自己的 **IMAPIAdviseSink** 实现，并避免完全使用 **HrAllocAdviseSink。**</span><span class="sxs-lookup"><span data-stu-id="072fa-109">Therefore, clients that need to carefully control their advise sink's release or that have interdependencies between their advise sink and another client object should construct their own **IMAPIAdviseSink** implementation and avoid using **HrAllocAdviseSink** altogether.</span></span> 
  
<span data-ttu-id="072fa-110">实现自己的建议接收器的客户端应使其成为不与任何其他对象相关或依赖于任何其他对象的独立对象，以便消除引用计数和对象释放中的潜在复杂性。</span><span class="sxs-lookup"><span data-stu-id="072fa-110">A client implementing its own advise sink should make it an independent object not related to or dependent upon any other objects so as to eliminate potential complications in reference counting and object release.</span></span> <span data-ttu-id="072fa-111">但是，如果您必须将建议接收器作为另一个对象的一部分实现，或者包含指向另一个对象的返回指针作为数据成员，则建议维护两个单独的引用计数：一个针对建议接收器引用的对象，另一个针对建议接收器。</span><span class="sxs-lookup"><span data-stu-id="072fa-111">However, if you must implement your advise sink as part of another object or include a back pointer to another object as a data member, it is recommended that two separate reference counts be maintained: one for the object referenced by the advise sink and one for the advise sink.</span></span> 
  
<span data-ttu-id="072fa-112">当引用对象的引用计数为零时，它的所有方法可能失败，并且其 vtable 可以销毁，但通知接收器的内存必须保持不变，直到其引用计数也降为零。</span><span class="sxs-lookup"><span data-stu-id="072fa-112">When the reference count of the referenced object falls to zero, all of its methods can fail and its vtable can be destroyed, but the memory for the advise sink must remain intact until after its reference count also falls to zero.</span></span> <span data-ttu-id="072fa-113">这意味着，通知接收器的 **Release** 方法必须缩小其引用计数，并完成在计数达到零时销毁对象。</span><span class="sxs-lookup"><span data-stu-id="072fa-113">This means that the advise sink's **Release** method must decrement its reference count and finish destroying the object when that count reaches zero.</span></span> <span data-ttu-id="072fa-114">如果未维护两个单独的引用计数，则很容易在包含对象的发布过程中无意中销毁 **通知接收器。**</span><span class="sxs-lookup"><span data-stu-id="072fa-114">If two separate reference counts are not maintained, it would be easy to inadvertently destroy the advise sink as part of the encompassing object's **Release** process.</span></span> 
  
<span data-ttu-id="072fa-115">使用 **HrAllocAdviseSink** 实现建议接收器的客户端必须同样小心，不要将回调函数作为方法包括在另一个建议接收器对象中。</span><span class="sxs-lookup"><span data-stu-id="072fa-115">Clients using **HrAllocAdviseSink** to implement an advise sink must be equally careful not to include their callback function as a method in another advise sink object.</span></span> <span data-ttu-id="072fa-116">对于 C++ 客户端，它很容易实现此要求，并作为  _参数传递此_ 指针。</span><span class="sxs-lookup"><span data-stu-id="072fa-116">For C++ clients, it is tempting to do this and pass the  _this_ pointer as a parameter.</span></span> <span data-ttu-id="072fa-117">这是一种危险策略，因为客户端通常在其引用计数达到零时释放对象。</span><span class="sxs-lookup"><span data-stu-id="072fa-117">This is a dangerous strategy because clients typically free an object when its reference count reaches zero.</span></span> <span data-ttu-id="072fa-118">释放通知接收对象的内存将使此  _指针_ 无效。</span><span class="sxs-lookup"><span data-stu-id="072fa-118">Freeing the memory for the advise sink object would render the  _this_ pointer invalid.</span></span> 
  
<span data-ttu-id="072fa-119">根据事件类型和建议源 **，OnNotify** 方法可以通过各种方式处理事件。</span><span class="sxs-lookup"><span data-stu-id="072fa-119">Depending on the type of event and the advise source, your **OnNotify** method can handle events in various ways.</span></span> <span data-ttu-id="072fa-120">下表提供了如何处理某些标准事件的建议。</span><span class="sxs-lookup"><span data-stu-id="072fa-120">The following table offers suggestions in how to handle some of the standard events.</span></span> 
  
|<span data-ttu-id="072fa-121">**事件类型**</span><span class="sxs-lookup"><span data-stu-id="072fa-121">**Type of event**</span></span>|<span data-ttu-id="072fa-122">**在 OnNotify 中处理**</span><span class="sxs-lookup"><span data-stu-id="072fa-122">**Handling in OnNotify**</span></span>|
|:-----|:-----|
|<span data-ttu-id="072fa-123">对象已移动</span><span class="sxs-lookup"><span data-stu-id="072fa-123">Object moved</span></span>  <br/> |<span data-ttu-id="072fa-124">如果移动对象的原始父对象与新父级相关，请从层次结构中最高的文件夹或通讯簿容器开始更新视图。</span><span class="sxs-lookup"><span data-stu-id="072fa-124">If the moved object's original parent is related to the new parent, update the view beginning with the folder or address book container highest in the hierarchy.</span></span> <span data-ttu-id="072fa-125">如果两个父容器不相关，请更新两个视图。</span><span class="sxs-lookup"><span data-stu-id="072fa-125">If the two parent containers are unrelated, update both of their views.</span></span>  <br/> |
|<span data-ttu-id="072fa-126">新邮件</span><span class="sxs-lookup"><span data-stu-id="072fa-126">New message</span></span>  <br/> |<span data-ttu-id="072fa-127">更改用户界面以通知用户一个或多个新邮件到达。</span><span class="sxs-lookup"><span data-stu-id="072fa-127">Change the user interface to inform the user of the arrival of one or more new messages.</span></span> <span data-ttu-id="072fa-128">将接收文件夹放在当前视图中。</span><span class="sxs-lookup"><span data-stu-id="072fa-128">Place the receive folder in the current view.</span></span>  <br/> |
|<span data-ttu-id="072fa-129">错误</span><span class="sxs-lookup"><span data-stu-id="072fa-129">Error</span></span>  <br/> |<span data-ttu-id="072fa-130">对于会话之外的所有对象，如有必要，请记录错误并返回。</span><span class="sxs-lookup"><span data-stu-id="072fa-130">For all objects except the session, log the error if necessary and return.</span></span> <span data-ttu-id="072fa-131">对于会话对象，如果可能，请注销。</span><span class="sxs-lookup"><span data-stu-id="072fa-131">For the session object, log off if possible.</span></span>  <br/> |
|<span data-ttu-id="072fa-132">搜索完成</span><span class="sxs-lookup"><span data-stu-id="072fa-132">Search complete</span></span>  <br/> |<span data-ttu-id="072fa-133">无需处理。</span><span class="sxs-lookup"><span data-stu-id="072fa-133">No processing necessary.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="072fa-134">通知处理程序应重新发送。</span><span class="sxs-lookup"><span data-stu-id="072fa-134">Notification handlers should be reentrant.</span></span> 
  

