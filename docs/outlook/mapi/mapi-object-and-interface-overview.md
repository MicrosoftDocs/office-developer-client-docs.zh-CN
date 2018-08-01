---
title: MAPI 对象和接口概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d4ece3af-cb54-4727-8072-0c055381ec11
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 8882457ff99f4150f2c9b086b92af32de29d60a7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776264"
---
# <a name="mapi-object-and-interface-overview"></a><span data-ttu-id="5b8c7-103">MAPI 对象和接口概述</span><span class="sxs-lookup"><span data-stu-id="5b8c7-103">MAPI Object and Interface Overview</span></span>

  
  
<span data-ttu-id="5b8c7-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="5b8c7-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="5b8c7-105">C + + 对象类或 C 数据结构从一个或多个 MAPI 接口或相关的函数集继承，MAPI 对象。</span><span class="sxs-lookup"><span data-stu-id="5b8c7-105">A MAPI object is a C++ object class or C data structure inherited from one or more MAPI interfaces, or collections of related functions.</span></span> <span data-ttu-id="5b8c7-106">下面这些集合相关函数称为于 c + + 开发人员纯虚函数。</span><span class="sxs-lookup"><span data-stu-id="5b8c7-106">These collections of related functions are known to C++ developers as pure virtual functions.</span></span> <span data-ttu-id="5b8c7-107">对于纯虚函数，MAPI 提供仅函数原型，不实现。</span><span class="sxs-lookup"><span data-stu-id="5b8c7-107">For a pure virtual function, MAPI supplies only the function prototype, not an implementation.</span></span> <span data-ttu-id="5b8c7-108">预计的客户端应用程序、 服务提供商或 MAPI 将通过创建继承自接口，且符合的消息的 api 功能描述对象类提供此实现。</span><span class="sxs-lookup"><span data-stu-id="5b8c7-108">It is expected that a client application, a service provider, or MAPI will provide this implementation by creating an object class that inherits from the interface and conforms to the function descriptions of the Messaging API.</span></span> <span data-ttu-id="5b8c7-109">只能通过继承的类，可以实例化 MAPI 接口。</span><span class="sxs-lookup"><span data-stu-id="5b8c7-109">A MAPI interface can be instantiated only through an inherited class.</span></span>
  
<span data-ttu-id="5b8c7-110">有许多不同的 MAPI 对象，每个对象继承最终从[IUnknown](http://msdn.microsoft.com/library/33f1d79a-33fc-4ce5-a372-e08bda378332%28Office.15%29.aspx)接口继承的接口。</span><span class="sxs-lookup"><span data-stu-id="5b8c7-110">There are many different MAPI objects, each object inheriting from an interface that is ultimately inherited from the [IUnknown](http://msdn.microsoft.com/library/33f1d79a-33fc-4ce5-a372-e08bda378332%28Office.15%29.aspx) interface.</span></span> <span data-ttu-id="5b8c7-111">**IUnknown**是 OLE 组件对象模型 (COM) 基接口。</span><span class="sxs-lookup"><span data-stu-id="5b8c7-111">**IUnknown** is the OLE Component Object Model (COM) base interface.</span></span> <span data-ttu-id="5b8c7-112">它为 MAPI 对象提供的标准机制通信和控件。</span><span class="sxs-lookup"><span data-stu-id="5b8c7-112">It provides MAPI objects with a standard mechanism for communication and control.</span></span> <span data-ttu-id="5b8c7-113">COM 规定对象实施如何处理如内存管理、 参数管理、 问题和多线程。</span><span class="sxs-lookup"><span data-stu-id="5b8c7-113">COM dictates how object implementers handle issues such as memory management, parameter management, and multithreading.</span></span> <span data-ttu-id="5b8c7-114">通过与此模型，对象实施符合指定合同由对象中包含的接口。</span><span class="sxs-lookup"><span data-stu-id="5b8c7-114">By conforming to this model, an object implementer adheres to a contract as specified by the interfaces included in the object.</span></span> 
  
<span data-ttu-id="5b8c7-115">许多 MAPI 接口继承直接从**IUnknown**，而其他人通过其他两个基本接口之一间接继承： [IMAPIProp: IUnknown](imapipropiunknown.md)属性管理和[IMAPIContainer: IMAPIProp](imapicontainerimapiprop.md)文件夹和通讯簿访问。</span><span class="sxs-lookup"><span data-stu-id="5b8c7-115">Many MAPI interfaces are inherited directly from **IUnknown**, while others are inherited indirectly through one of two other base interfaces: [IMAPIProp : IUnknown](imapipropiunknown.md) for property management and [IMAPIContainer : IMAPIProp](imapicontainerimapiprop.md) for folder and address book access.</span></span> <span data-ttu-id="5b8c7-116">作为独立的独立对象; 从不实现基接口始终实现这些其他对象的一部分，实现的对象派生的接口。</span><span class="sxs-lookup"><span data-stu-id="5b8c7-116">Base interfaces are never implemented as separate, standalone objects; they are always implemented as part of other objects, objects that implement derived interfaces.</span></span> 
  
<span data-ttu-id="5b8c7-117">MAPI 定义许多类型的对象，每个由一个或多个 MAPI 组件实现。</span><span class="sxs-lookup"><span data-stu-id="5b8c7-117">MAPI defines many types of objects, each implemented by one or more MAPI components.</span></span> <span data-ttu-id="5b8c7-118">由客户端实现的对象习惯通过 MAPI、 服务提供商，以及自定义表单组件。</span><span class="sxs-lookup"><span data-stu-id="5b8c7-118">Objects implemented by clients are used by MAPI, by service providers, and by custom form components.</span></span> <span data-ttu-id="5b8c7-119">MAPI 和客户端，通常使用由服务提供商实现的对象。</span><span class="sxs-lookup"><span data-stu-id="5b8c7-119">Objects implemented by service providers are typically used by MAPI and by clients.</span></span> <span data-ttu-id="5b8c7-120">对象实现由表单库提供程序以及其他窗体组件和客户端使用窗体服务器。</span><span class="sxs-lookup"><span data-stu-id="5b8c7-120">Objects implemented by form library providers and form servers are used by other form components and by clients.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="5b8c7-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5b8c7-121">See also</span></span>



[<span data-ttu-id="5b8c7-122">IMAPIProp : IUnknown</span><span class="sxs-lookup"><span data-stu-id="5b8c7-122">IMAPIProp : IUnknown</span></span>](imapipropiunknown.md)
  
[<span data-ttu-id="5b8c7-123">IMAPIContainer : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="5b8c7-123">IMAPIContainer : IMAPIProp</span></span>](imapicontainerimapiprop.md)


[<span data-ttu-id="5b8c7-124">MAPI 概念</span><span class="sxs-lookup"><span data-stu-id="5b8c7-124">MAPI Concepts</span></span>](mapi-concepts.md)

