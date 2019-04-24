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
ms.openlocfilehash: ecaad65d28f74b843b86ca82dab9a833ade77363
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351098"
---
# <a name="implementing-an-advise-sink-object"></a><span data-ttu-id="dbe30-103">实现通知接收器对象</span><span class="sxs-lookup"><span data-stu-id="dbe30-103">Implementing an Advise Sink Object</span></span>

  
  
<span data-ttu-id="dbe30-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="dbe30-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="dbe30-105">客户端可以实施其自己的通知接收器对象或使用实用工具函数[HrAllocAdviseSink](hrallocadvisesink.md)。</span><span class="sxs-lookup"><span data-stu-id="dbe30-105">A client can either implement its own advise sink objects or use a utility function, [HrAllocAdviseSink](hrallocadvisesink.md).</span></span> <span data-ttu-id="dbe30-106">**HrAllocAdviseSink**使用调用回调函数的**OnNotify**的实现创建一个通知接收器对象。</span><span class="sxs-lookup"><span data-stu-id="dbe30-106">**HrAllocAdviseSink** creates an advise sink object with an implementation of **OnNotify** that invokes a callback function.</span></span> 
  
<span data-ttu-id="dbe30-107">使用**HrAllocAdviseSink**的优点和缺点各不相同。</span><span class="sxs-lookup"><span data-stu-id="dbe30-107">There are advantages and disadvantages to using **HrAllocAdviseSink**.</span></span> <span data-ttu-id="dbe30-108">它可以节省工作, 但不能控制对它创建的 "通知接收器" 对象进行计数的引用计数。</span><span class="sxs-lookup"><span data-stu-id="dbe30-108">It can save work, but it provides no control over reference counting the advise sink object that it creates.</span></span> <span data-ttu-id="dbe30-109">因此, 需要仔细控制其通知接收器发布或在其通知接收器和另一个客户端对象之间存在相互依赖关系的客户端应构造其自己的**IMAPIAdviseSink**实现, 从而避免使用**完全 HrAllocAdviseSink** 。</span><span class="sxs-lookup"><span data-stu-id="dbe30-109">Therefore, clients that need to carefully control their advise sink's release or that have interdependencies between their advise sink and another client object should construct their own **IMAPIAdviseSink** implementation and avoid using **HrAllocAdviseSink** altogether.</span></span> 
  
<span data-ttu-id="dbe30-110">实现自己的通知接收器的客户端应使其不与任何其他对象相关或依赖于任何其他对象的独立对象, 以避免引用计数和对象释放中的潜在麻烦。</span><span class="sxs-lookup"><span data-stu-id="dbe30-110">A client implementing its own advise sink should make it an independent object not related to or dependent upon any other objects so as to eliminate potential complications in reference counting and object release.</span></span> <span data-ttu-id="dbe30-111">但是, 如果您必须将您的通知接收器作为另一个对象的一部分实现或包含指向另一个对象的 back 指针作为数据成员, 则建议保留两个单独的引用计数: 一个用于通知接收器引用的对象, 另一个用于通知接收器。</span><span class="sxs-lookup"><span data-stu-id="dbe30-111">However, if you must implement your advise sink as part of another object or include a back pointer to another object as a data member, it is recommended that two separate reference counts be maintained: one for the object referenced by the advise sink and one for the advise sink.</span></span> 
  
<span data-ttu-id="dbe30-112">当被引用对象的引用计数为零时, 它的所有方法都可能会失败, 并且可以销毁它的 vtable, 但建议接收器的内存必须保持不变, 直到其引用计数也降为零。</span><span class="sxs-lookup"><span data-stu-id="dbe30-112">When the reference count of the referenced object falls to zero, all of its methods can fail and its vtable can be destroyed, but the memory for the advise sink must remain intact until after its reference count also falls to zero.</span></span> <span data-ttu-id="dbe30-113">这意味着, 通知接收器的**Release**方法必须减小其引用计数, 并在该计数达到零时完成对该对象的销毁。</span><span class="sxs-lookup"><span data-stu-id="dbe30-113">This means that the advise sink's **Release** method must decrement its reference count and finish destroying the object when that count reaches zero.</span></span> <span data-ttu-id="dbe30-114">如果不保留两个单独的引用计数, 则很容易在包含对象的**发布**过程中不小心销毁建议接收器。</span><span class="sxs-lookup"><span data-stu-id="dbe30-114">If two separate reference counts are not maintained, it would be easy to inadvertently destroy the advise sink as part of the encompassing object's **Release** process.</span></span> 
  
<span data-ttu-id="dbe30-115">使用**HrAllocAdviseSink**实现通知接收器的客户端必须同样小心, 不要将其回调函数作为另一个建议接收器对象中的方法。</span><span class="sxs-lookup"><span data-stu-id="dbe30-115">Clients using **HrAllocAdviseSink** to implement an advise sink must be equally careful not to include their callback function as a method in another advise sink object.</span></span> <span data-ttu-id="dbe30-116">对于 c + + 客户端, 实现此目的并将_此_指针作为参数传递是很有吸引力的。</span><span class="sxs-lookup"><span data-stu-id="dbe30-116">For C++ clients, it is tempting to do this and pass the  _this_ pointer as a parameter.</span></span> <span data-ttu-id="dbe30-117">这是一种危险策略, 因为客户端通常会在其引用计数达到零时释放对象。</span><span class="sxs-lookup"><span data-stu-id="dbe30-117">This is a dangerous strategy because clients typically free an object when its reference count reaches zero.</span></span> <span data-ttu-id="dbe30-118">释放通知接收器对象的内存将导致_此_指针无效。</span><span class="sxs-lookup"><span data-stu-id="dbe30-118">Freeing the memory for the advise sink object would render the  _this_ pointer invalid.</span></span> 
  
<span data-ttu-id="dbe30-119">根据事件的类型和建议源, **OnNotify**方法可以通过多种方式处理事件。</span><span class="sxs-lookup"><span data-stu-id="dbe30-119">Depending on the type of event and the advise source, your **OnNotify** method can handle events in various ways.</span></span> <span data-ttu-id="dbe30-120">下表提供了有关如何处理一些标准事件的建议。</span><span class="sxs-lookup"><span data-stu-id="dbe30-120">The following table offers suggestions in how to handle some of the standard events.</span></span> 
  
|<span data-ttu-id="dbe30-121">**事件类型**</span><span class="sxs-lookup"><span data-stu-id="dbe30-121">**Type of event**</span></span>|<span data-ttu-id="dbe30-122">**在 OnNotify 中处理**</span><span class="sxs-lookup"><span data-stu-id="dbe30-122">**Handling in OnNotify**</span></span>|
|:-----|:-----|
|<span data-ttu-id="dbe30-123">移动的对象</span><span class="sxs-lookup"><span data-stu-id="dbe30-123">Object moved</span></span>  <br/> |<span data-ttu-id="dbe30-124">如果移动的对象的原始父对象与新的父对象相关联, 请从层次结构中最高的文件夹或通讯簿容器开始更新视图。</span><span class="sxs-lookup"><span data-stu-id="dbe30-124">If the moved object's original parent is related to the new parent, update the view beginning with the folder or address book container highest in the hierarchy.</span></span> <span data-ttu-id="dbe30-125">如果两个父容器不相关, 请更新其两个视图。</span><span class="sxs-lookup"><span data-stu-id="dbe30-125">If the two parent containers are unrelated, update both of their views.</span></span>  <br/> |
|<span data-ttu-id="dbe30-126">新邮件</span><span class="sxs-lookup"><span data-stu-id="dbe30-126">New message</span></span>  <br/> |<span data-ttu-id="dbe30-127">更改用户界面以通知用户有一个或多个新邮件到达。</span><span class="sxs-lookup"><span data-stu-id="dbe30-127">Change the user interface to inform the user of the arrival of one or more new messages.</span></span> <span data-ttu-id="dbe30-128">将接收文件夹放置在当前视图中。</span><span class="sxs-lookup"><span data-stu-id="dbe30-128">Place the receive folder in the current view.</span></span>  <br/> |
|<span data-ttu-id="dbe30-129">Error</span><span class="sxs-lookup"><span data-stu-id="dbe30-129">Error</span></span>  <br/> |<span data-ttu-id="dbe30-130">对于除会话之外的所有对象, 请记录错误 (如有必要) 并返回。</span><span class="sxs-lookup"><span data-stu-id="dbe30-130">For all objects except the session, log the error if necessary and return.</span></span> <span data-ttu-id="dbe30-131">对于 session 对象, 请注销 (如果可能)。</span><span class="sxs-lookup"><span data-stu-id="dbe30-131">For the session object, log off if possible.</span></span>  <br/> |
|<span data-ttu-id="dbe30-132">搜索完成</span><span class="sxs-lookup"><span data-stu-id="dbe30-132">Search complete</span></span>  <br/> |<span data-ttu-id="dbe30-133">无需处理。</span><span class="sxs-lookup"><span data-stu-id="dbe30-133">No processing necessary.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="dbe30-134">通知处理程序应是可重入的。</span><span class="sxs-lookup"><span data-stu-id="dbe30-134">Notification handlers should be reentrant.</span></span> 
  

