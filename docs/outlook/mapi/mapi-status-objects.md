---
title: MAPI 状态对象
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 38310619-1b1d-4934-8533-d0612676c0b0
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 69a4d25fc6a7abec68c94cc947e5944322d230a6
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594948"
---
# <a name="mapi-status-objects"></a><span data-ttu-id="46405-103">MAPI 状态对象</span><span class="sxs-lookup"><span data-stu-id="46405-103">MAPI Status Objects</span></span>

  
  
<span data-ttu-id="46405-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="46405-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="46405-105">状态对象报告 MAPI 资源的信息。</span><span class="sxs-lookup"><span data-stu-id="46405-105">Status objects report information about MAPI resources.</span></span> <span data-ttu-id="46405-106">例如，服务提供程序、 MAPI 发送/接收进程或通讯簿。</span><span class="sxs-lookup"><span data-stu-id="46405-106">For example, a service provider, the MAPI send/receive process, or the address book.</span></span>
  
<span data-ttu-id="46405-107">没有状态对象提供有关当前配置文件中每个单独的服务提供商的信息。</span><span class="sxs-lookup"><span data-stu-id="46405-107">There is a status object supplying information about each individual service provider in the current profile.</span></span> <span data-ttu-id="46405-108">MAPI 负责实现子系统、 MAPI 发送/接收过程和通讯簿状态对象。</span><span class="sxs-lookup"><span data-stu-id="46405-108">MAPI is responsible for implementing status objects for the subsystem, the MAPI send/receive process, and the address book.</span></span> <span data-ttu-id="46405-109">子系统状态对象提供全球信息。</span><span class="sxs-lookup"><span data-stu-id="46405-109">The subsystem status object supplies global information.</span></span> <span data-ttu-id="46405-110">集成的通讯簿的状态对象提供的正在运行的所有通讯簿提供程序的状态。</span><span class="sxs-lookup"><span data-stu-id="46405-110">The status object for the integrated address book supplies the status of all address book providers currently operating.</span></span>
  
<span data-ttu-id="46405-111">在状态表中，客户端提供的所有会话状态信息的 MAPI 维护的表包含每个状态对象。</span><span class="sxs-lookup"><span data-stu-id="46405-111">Every status object is included in the status table, a table maintained by MAPI that provides clients with all of the status information for the session.</span></span> <span data-ttu-id="46405-112">有关详细信息，请参阅[状态表](status-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="46405-112">For more information, see [Status Tables](status-tables.md).</span></span> <span data-ttu-id="46405-113">客户端可以访问的特定状态对象，通过表或，针对服务提供程序，通过其登录对象。</span><span class="sxs-lookup"><span data-stu-id="46405-113">Clients can access a particular status object either through the table or, for a service provider, through its logon object.</span></span> <span data-ttu-id="46405-114">例如，若要访问通讯簿提供程序的状态对象，客户端可以调用**IABLogon::OpenStatusEntry**。</span><span class="sxs-lookup"><span data-stu-id="46405-114">For example, to access an address book provider's status object, a client can call **IABLogon::OpenStatusEntry**.</span></span> <span data-ttu-id="46405-115">有关详细信息，请参阅[IABLogon::OpenStatusEntry](iablogon-openstatusentry.md)。</span><span class="sxs-lookup"><span data-stu-id="46405-115">For more information, see [IABLogon::OpenStatusEntry](iablogon-openstatusentry.md).</span></span>
  
<span data-ttu-id="46405-116">客户端可以使用状态对象：</span><span class="sxs-lookup"><span data-stu-id="46405-116">Clients can use status objects to:</span></span>
  
- <span data-ttu-id="46405-117">了解有关会话的状态信息。</span><span class="sxs-lookup"><span data-stu-id="46405-117">Learn about the state of a session.</span></span>
    
- <span data-ttu-id="46405-118">监视服务提供商。</span><span class="sxs-lookup"><span data-stu-id="46405-118">Monitor a service provider.</span></span>
    
- <span data-ttu-id="46405-119">控制消息传输。</span><span class="sxs-lookup"><span data-stu-id="46405-119">Control message transmission.</span></span>
    
- <span data-ttu-id="46405-120">查看或更改资源的配置和状态。</span><span class="sxs-lookup"><span data-stu-id="46405-120">View or change a resource's configuration and status.</span></span>
    
<span data-ttu-id="46405-121">每个状态对象实现**IMAPIStatus**接口。</span><span class="sxs-lookup"><span data-stu-id="46405-121">Every status object implements the **IMAPIStatus** interface.</span></span> <span data-ttu-id="46405-122">有关详细信息，请参阅[IMAPIStatus: IMAPIProp](imapistatusimapiprop.md)。</span><span class="sxs-lookup"><span data-stu-id="46405-122">For more information, see [IMAPIStatus : IMAPIProp](imapistatusimapiprop.md).</span></span> <span data-ttu-id="46405-123">但是，不是每个状态对象完全支持每个**IMAPIStatus**方法。</span><span class="sxs-lookup"><span data-stu-id="46405-123">However, not every status object fully supports every **IMAPIStatus** method.</span></span> <span data-ttu-id="46405-124">因为没有状态对象支持的方法中的变体，客户端需要了解的特定状态对象，然后才能使用它。</span><span class="sxs-lookup"><span data-stu-id="46405-124">Because there is variation in the methods that are supported by a status object, clients need to learn about a particular status object before they can use it.</span></span> <span data-ttu-id="46405-125">状态对象所需的以下三个属性中发布有关其功能的信息：</span><span class="sxs-lookup"><span data-stu-id="46405-125">Status objects are required to publish information about their features in the following three properties:</span></span> 
  
 <span data-ttu-id="46405-126">**PR_RESOURCE_METHODS**([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="46405-126">**PR_RESOURCE_METHODS** ([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md))</span></span> 
  
 <span data-ttu-id="46405-127">**PR_RESOURCE_TYPE**([PidTagResourceType](pidtagresourcetype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="46405-127">**PR_RESOURCE_TYPE** ([PidTagResourceType](pidtagresourcetype-canonical-property.md))</span></span> 
  
 <span data-ttu-id="46405-128">**PR_RESOURCE_FLAGS**([PidTagResourceFlags](pidtagresourceflags-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="46405-128">**PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md))</span></span> 
  
<span data-ttu-id="46405-129">有关实现状态对象的详细信息，请参阅[状态对象实现](status-object-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="46405-129">For more information about implementing a status object, see [Status Object Implementation](status-object-implementation.md).</span></span> <span data-ttu-id="46405-130">有关使用状态对象的详细信息，请参阅[状态表和状态对象](status-table-and-status-objects.md)。</span><span class="sxs-lookup"><span data-stu-id="46405-130">For more information about using a status object, see [Status Table and Status Objects](status-table-and-status-objects.md).</span></span>
  

