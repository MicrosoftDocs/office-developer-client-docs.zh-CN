---
title: MAPI 状态对象
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 38310619-1b1d-4934-8533-d0612676c0b0
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 816d1b7c9c0b8c5a80a2351580ce3224fccf0b14
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309532"
---
# <a name="mapi-status-objects"></a><span data-ttu-id="84593-103">MAPI 状态对象</span><span class="sxs-lookup"><span data-stu-id="84593-103">MAPI Status Objects</span></span>

  
  
<span data-ttu-id="84593-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="84593-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="84593-105">状态对象报告有关 MAPI 资源的信息。</span><span class="sxs-lookup"><span data-stu-id="84593-105">Status objects report information about MAPI resources.</span></span> <span data-ttu-id="84593-106">例如, 服务提供商、MAPI 发送/接收进程或通讯簿。</span><span class="sxs-lookup"><span data-stu-id="84593-106">For example, a service provider, the MAPI send/receive process, or the address book.</span></span>
  
<span data-ttu-id="84593-107">有一个 status 对象, 提供有关当前配置文件中每个服务提供程序的信息。</span><span class="sxs-lookup"><span data-stu-id="84593-107">There is a status object supplying information about each individual service provider in the current profile.</span></span> <span data-ttu-id="84593-108">mapi 负责实现子系统、MAPI 发送/接收进程和通讯簿的状态对象。</span><span class="sxs-lookup"><span data-stu-id="84593-108">MAPI is responsible for implementing status objects for the subsystem, the MAPI send/receive process, and the address book.</span></span> <span data-ttu-id="84593-109">子系统状态对象提供全局信息。</span><span class="sxs-lookup"><span data-stu-id="84593-109">The subsystem status object supplies global information.</span></span> <span data-ttu-id="84593-110">集成通讯簿的 status 对象提供当前正在运行的所有通讯簿提供程序的状态。</span><span class="sxs-lookup"><span data-stu-id="84593-110">The status object for the integrated address book supplies the status of all address book providers currently operating.</span></span>
  
<span data-ttu-id="84593-111">每个 status 对象都包含在状态表中, 由 MAPI 维护的表, 为客户端提供会话的所有状态信息。</span><span class="sxs-lookup"><span data-stu-id="84593-111">Every status object is included in the status table, a table maintained by MAPI that provides clients with all of the status information for the session.</span></span> <span data-ttu-id="84593-112">有关详细信息, 请参阅[状态表](status-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="84593-112">For more information, see [Status Tables](status-tables.md).</span></span> <span data-ttu-id="84593-113">客户端可以通过表或服务提供商 (通过其登录对象) 访问特定的状态对象。</span><span class="sxs-lookup"><span data-stu-id="84593-113">Clients can access a particular status object either through the table or, for a service provider, through its logon object.</span></span> <span data-ttu-id="84593-114">例如, 若要访问通讯簿提供程序的 status 对象, 客户端可以调用**IABLogon:: OpenStatusEntry**。</span><span class="sxs-lookup"><span data-stu-id="84593-114">For example, to access an address book provider's status object, a client can call **IABLogon::OpenStatusEntry**.</span></span> <span data-ttu-id="84593-115">有关详细信息, 请参阅[IABLogon:: OpenStatusEntry](iablogon-openstatusentry.md)。</span><span class="sxs-lookup"><span data-stu-id="84593-115">For more information, see [IABLogon::OpenStatusEntry](iablogon-openstatusentry.md).</span></span>
  
<span data-ttu-id="84593-116">客户端可以使用 status 对象执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="84593-116">Clients can use status objects to:</span></span>
  
- <span data-ttu-id="84593-117">了解会话的状态。</span><span class="sxs-lookup"><span data-stu-id="84593-117">Learn about the state of a session.</span></span>
    
- <span data-ttu-id="84593-118">监视服务提供商。</span><span class="sxs-lookup"><span data-stu-id="84593-118">Monitor a service provider.</span></span>
    
- <span data-ttu-id="84593-119">控制邮件传输。</span><span class="sxs-lookup"><span data-stu-id="84593-119">Control message transmission.</span></span>
    
- <span data-ttu-id="84593-120">查看或更改资源的配置和状态。</span><span class="sxs-lookup"><span data-stu-id="84593-120">View or change a resource's configuration and status.</span></span>
    
<span data-ttu-id="84593-121">每个 status 对象都实现**IMAPIStatus**接口。</span><span class="sxs-lookup"><span data-stu-id="84593-121">Every status object implements the **IMAPIStatus** interface.</span></span> <span data-ttu-id="84593-122">有关详细信息, 请参阅[IMAPIStatus: IMAPIProp](imapistatusimapiprop.md)。</span><span class="sxs-lookup"><span data-stu-id="84593-122">For more information, see [IMAPIStatus : IMAPIProp](imapistatusimapiprop.md).</span></span> <span data-ttu-id="84593-123">但是, 并不是每个 status 对象完全支持每个**IMAPIStatus**方法。</span><span class="sxs-lookup"><span data-stu-id="84593-123">However, not every status object fully supports every **IMAPIStatus** method.</span></span> <span data-ttu-id="84593-124">由于 status 对象支持的方法有变体, 因此客户端需要先了解特定状态对象, 然后才能使用该对象。</span><span class="sxs-lookup"><span data-stu-id="84593-124">Because there is variation in the methods that are supported by a status object, clients need to learn about a particular status object before they can use it.</span></span> <span data-ttu-id="84593-125">必须有 Status 对象才能发布以下三个属性中有关其功能的信息:</span><span class="sxs-lookup"><span data-stu-id="84593-125">Status objects are required to publish information about their features in the following three properties:</span></span> 
  
 <span data-ttu-id="84593-126">**PR_RESOURCE_METHODS**([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="84593-126">**PR_RESOURCE_METHODS** ([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md))</span></span> 
  
 <span data-ttu-id="84593-127">**PR_RESOURCE_TYPE**([PidTagResourceType](pidtagresourcetype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="84593-127">**PR_RESOURCE_TYPE** ([PidTagResourceType](pidtagresourcetype-canonical-property.md))</span></span> 
  
 <span data-ttu-id="84593-128">**PR_RESOURCE_FLAGS**([PidTagResourceFlags](pidtagresourceflags-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="84593-128">**PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md))</span></span> 
  
<span data-ttu-id="84593-129">有关实现 status 对象的详细信息, 请参阅[status object 实现](status-object-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="84593-129">For more information about implementing a status object, see [Status Object Implementation](status-object-implementation.md).</span></span> <span data-ttu-id="84593-130">有关使用 status 对象的详细信息, 请参阅[status Table 和 status 对象](status-table-and-status-objects.md)。</span><span class="sxs-lookup"><span data-stu-id="84593-130">For more information about using a status object, see [Status Table and Status Objects](status-table-and-status-objects.md).</span></span>
  

