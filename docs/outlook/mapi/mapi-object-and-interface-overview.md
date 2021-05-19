---
title: MAPI 对象和接口概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d4ece3af-cb54-4727-8072-0c055381ec11
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: fcd85bf518f4e6466bf15a09e417767bc34df78d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345785"
---
# <a name="mapi-object-and-interface-overview"></a><span data-ttu-id="c620a-103">MAPI 对象和接口概述</span><span class="sxs-lookup"><span data-stu-id="c620a-103">MAPI Object and Interface Overview</span></span>

  
  
<span data-ttu-id="c620a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c620a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c620a-105">MAPI 对象是从一个或多个 MAPI 接口或相关函数集合继承的 C++ 对象类或 C 数据结构。</span><span class="sxs-lookup"><span data-stu-id="c620a-105">A MAPI object is a C++ object class or C data structure inherited from one or more MAPI interfaces, or collections of related functions.</span></span> <span data-ttu-id="c620a-106">C++ 开发人员知道这些相关函数集合是纯虚拟函数。</span><span class="sxs-lookup"><span data-stu-id="c620a-106">These collections of related functions are known to C++ developers as pure virtual functions.</span></span> <span data-ttu-id="c620a-107">对于纯虚拟函数，MAPI 仅提供函数原型，而不是实现。</span><span class="sxs-lookup"><span data-stu-id="c620a-107">For a pure virtual function, MAPI supplies only the function prototype, not an implementation.</span></span> <span data-ttu-id="c620a-108">客户端应用程序、服务提供商或 MAPI 预期会通过创建继承自接口且符合消息 API 的函数说明的对象类来提供此实现。</span><span class="sxs-lookup"><span data-stu-id="c620a-108">It is expected that a client application, a service provider, or MAPI will provide this implementation by creating an object class that inherits from the interface and conforms to the function descriptions of the Messaging API.</span></span> <span data-ttu-id="c620a-109">MAPI 接口只能通过继承的类实例化。</span><span class="sxs-lookup"><span data-stu-id="c620a-109">A MAPI interface can be instantiated only through an inherited class.</span></span>
  
<span data-ttu-id="c620a-110">存在许多不同的 MAPI 对象，每个对象都继承自最终继承自 [IUnknown](https://msdn.microsoft.com/library/33f1d79a-33fc-4ce5-a372-e08bda378332%28Office.15%29.aspx) 接口的接口。</span><span class="sxs-lookup"><span data-stu-id="c620a-110">There are many different MAPI objects, each object inheriting from an interface that is ultimately inherited from the [IUnknown](https://msdn.microsoft.com/library/33f1d79a-33fc-4ce5-a372-e08bda378332%28Office.15%29.aspx) interface.</span></span> <span data-ttu-id="c620a-111">**IUnknown** 是 OLE 组件对象模型 (COM) 接口。</span><span class="sxs-lookup"><span data-stu-id="c620a-111">**IUnknown** is the OLE Component Object Model (COM) base interface.</span></span> <span data-ttu-id="c620a-112">它为 MAPI 对象提供了用于通信和控制的标准机制。</span><span class="sxs-lookup"><span data-stu-id="c620a-112">It provides MAPI objects with a standard mechanism for communication and control.</span></span> <span data-ttu-id="c620a-113">COM 规定对象实施者如何处理内存管理、参数管理和多线程等问题。</span><span class="sxs-lookup"><span data-stu-id="c620a-113">COM dictates how object implementers handle issues such as memory management, parameter management, and multithreading.</span></span> <span data-ttu-id="c620a-114">通过遵循此模型，对象实现者将遵守对象中包含的接口所指定的协定。</span><span class="sxs-lookup"><span data-stu-id="c620a-114">By conforming to this model, an object implementer adheres to a contract as specified by the interfaces included in the object.</span></span> 
  
<span data-ttu-id="c620a-115">许多 MAPI 接口直接继承自 **IUnknown**，而其他接口通过其他两个基接口之一间接继承 [：IMAPIProp：用于属性管理的 IUnknown](imapipropiunknown.md) 和 [IMAPIContainer：用于](imapicontainerimapiprop.md) 文件夹和通讯簿访问的 IMAPIProp。</span><span class="sxs-lookup"><span data-stu-id="c620a-115">Many MAPI interfaces are inherited directly from **IUnknown**, while others are inherited indirectly through one of two other base interfaces: [IMAPIProp : IUnknown](imapipropiunknown.md) for property management and [IMAPIContainer : IMAPIProp](imapicontainerimapiprop.md) for folder and address book access.</span></span> <span data-ttu-id="c620a-116">基接口从不作为独立的独立对象实现;它们始终作为其他对象的一部分实现，即实现派生接口的对象。</span><span class="sxs-lookup"><span data-stu-id="c620a-116">Base interfaces are never implemented as separate, standalone objects; they are always implemented as part of other objects, objects that implement derived interfaces.</span></span> 
  
<span data-ttu-id="c620a-117">MAPI 定义许多类型的对象，每种类型的对象都由一个或多个 MAPI 组件实现。</span><span class="sxs-lookup"><span data-stu-id="c620a-117">MAPI defines many types of objects, each implemented by one or more MAPI components.</span></span> <span data-ttu-id="c620a-118">由客户端实现的对象由 MAPI、服务提供商和自定义表单组件使用。</span><span class="sxs-lookup"><span data-stu-id="c620a-118">Objects implemented by clients are used by MAPI, by service providers, and by custom form components.</span></span> <span data-ttu-id="c620a-119">服务提供商实现的对象通常由 MAPI 和客户端使用。</span><span class="sxs-lookup"><span data-stu-id="c620a-119">Objects implemented by service providers are typically used by MAPI and by clients.</span></span> <span data-ttu-id="c620a-120">由表单库提供程序和表单服务器实现的对象由其他表单组件和客户端使用。</span><span class="sxs-lookup"><span data-stu-id="c620a-120">Objects implemented by form library providers and form servers are used by other form components and by clients.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="c620a-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c620a-121">See also</span></span>



[<span data-ttu-id="c620a-122">IMAPIProp : IUnknown</span><span class="sxs-lookup"><span data-stu-id="c620a-122">IMAPIProp : IUnknown</span></span>](imapipropiunknown.md)
  
[<span data-ttu-id="c620a-123">IMAPIContainer : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="c620a-123">IMAPIContainer : IMAPIProp</span></span>](imapicontainerimapiprop.md)


[<span data-ttu-id="c620a-124">MAPI 概念</span><span class="sxs-lookup"><span data-stu-id="c620a-124">MAPI Concepts</span></span>](mapi-concepts.md)

