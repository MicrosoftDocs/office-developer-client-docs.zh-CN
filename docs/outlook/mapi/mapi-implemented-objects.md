---
title: MAPI 实现的对象
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 5d07c259-0ceb-4ea5-98b4-b01720edfe2a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 86aa8451b5b127764134f1a3a905366fd014d0c3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430628"
---
# <a name="mapi-implemented-objects"></a><span data-ttu-id="56e48-103">MAPI 实现的对象</span><span class="sxs-lookup"><span data-stu-id="56e48-103">MAPI-implemented objects</span></span>
  
<span data-ttu-id="56e48-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="56e48-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="56e48-105">MAPI 实现多个对象，供客户端应用程序和服务提供商使用。</span><span class="sxs-lookup"><span data-stu-id="56e48-105">MAPI implements several objects for use by client applications and service providers.</span></span> <span data-ttu-id="56e48-106">会话对象允许客户端使用会话服务、访问表以及与服务提供商通信。</span><span class="sxs-lookup"><span data-stu-id="56e48-106">The session object allows clients to use session services, to access tables, and to communicate with service providers.</span></span> <span data-ttu-id="56e48-107">通过通讯簿对象，客户端可以集成访问所有不同的通讯簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="56e48-107">The address book object provides clients with integrated access to all of the different address book providers.</span></span> 
  
<span data-ttu-id="56e48-108">MAPI 为客户端提供了多个表和状态对象，以便用于查看和监视会话和服务提供程序信息。</span><span class="sxs-lookup"><span data-stu-id="56e48-108">MAPI supplies multiple table and status objects for clients to use for viewing and monitoring session and service provider information.</span></span> <span data-ttu-id="56e48-109">例如，MAPI 提供了一个配置文件表，该表包含有关计算机上安装的所有配置文件的信息，以及一个包含当前配置文件中所有邮件服务的信息的邮件服务表。</span><span class="sxs-lookup"><span data-stu-id="56e48-109">For example, MAPI provides a profile table with information about all of the profiles that are installed on the computer and a message service table with information about all of the message services in the current profile.</span></span> <span data-ttu-id="56e48-110">MAPI 提供三种不同的状态对象：一个表示整个子系统，一个代表 MAPI 后台处理程序，另一个代表集成通讯簿。</span><span class="sxs-lookup"><span data-stu-id="56e48-110">MAPI provides three different status objects: one that represents the overall subsystem, one for the MAPI spooler, and one for the integrated address book.</span></span> 
  
<span data-ttu-id="56e48-111">MAPI 实现了四个不同的对象，用于管理邮件服务、服务提供程序和配置文件的配置。</span><span class="sxs-lookup"><span data-stu-id="56e48-111">MAPI implements four different objects for managing the configuration of message services, service providers, and profiles.</span></span> <span data-ttu-id="56e48-112">客户端和服务提供商均使用提供程序管理和配置文件节对象;这些对象允许它们配置服务提供程序和访问配置文件属性。</span><span class="sxs-lookup"><span data-stu-id="56e48-112">Both clients and service providers use provider administration and profile section objects; these objects enable them to configure service providers and access profile properties.</span></span> <span data-ttu-id="56e48-113">客户端仅使用邮件服务和配置文件管理对象，即支持邮件服务和配置文件管理的对象。</span><span class="sxs-lookup"><span data-stu-id="56e48-113">Clients use only message service and profile administration objects, the objects that support the administration of message services and profiles.</span></span> 
  
<span data-ttu-id="56e48-114">MAPI 为服务提供商提供两个对象：一个支持对象和一个 TNEF 对象。</span><span class="sxs-lookup"><span data-stu-id="56e48-114">MAPI provides two objects for service providers: a support object and a TNEF object.</span></span> <span data-ttu-id="56e48-115">所有服务提供程序都使用一个或多个支持对象;有四种不同的支持对象实现。</span><span class="sxs-lookup"><span data-stu-id="56e48-115">All service providers use one or more support objects; there are four different support object implementations.</span></span> <span data-ttu-id="56e48-116">MAPI 提供了一个实现来支持配置以及支持通讯簿、邮件存储和传输提供程序的特定实现。</span><span class="sxs-lookup"><span data-stu-id="56e48-116">MAPI supplies an implementation to support configuration as well as specific implementations to support address book, message store, and transport providers.</span></span> <span data-ttu-id="56e48-117">TNEF 对象由支持 TNEF 传输中性封装格式的传输 (TNEF) 。</span><span class="sxs-lookup"><span data-stu-id="56e48-117">The TNEF object is used by transport providers that support the Transport Neutral Encapsulation Format (TNEF).</span></span>
  
<span data-ttu-id="56e48-118">两个实用程序对象（表数据和属性数据）通常由服务提供商使用。</span><span class="sxs-lookup"><span data-stu-id="56e48-118">Two utility objects, table data and property data, are typically used by service providers.</span></span> <span data-ttu-id="56e48-119">表数据对象有助于实现表对象;属性数据对象可帮助设置和查看属性访问，并帮助实现 [IMAPIProp ：IUnknown，](imapipropiunknown.md)基属性接口。</span><span class="sxs-lookup"><span data-stu-id="56e48-119">Table data objects help in the implementation of table objects; property data objects help to set and view property access and help in the implementation of [IMAPIProp : IUnknown](imapipropiunknown.md), the base property interface.</span></span> 
  
<span data-ttu-id="56e48-120">下表总结了 MAPI 实现的每个对象的用途。</span><span class="sxs-lookup"><span data-stu-id="56e48-120">The following table summarizes the purpose for each object that MAPI implements.</span></span>
  
|<span data-ttu-id="56e48-121">**MAPI 对象**</span><span class="sxs-lookup"><span data-stu-id="56e48-121">**MAPI object**</span></span>|<span data-ttu-id="56e48-122">**说明**</span><span class="sxs-lookup"><span data-stu-id="56e48-122">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="56e48-123">通讯簿</span><span class="sxs-lookup"><span data-stu-id="56e48-123">Address book</span></span>  <br/> |<span data-ttu-id="56e48-124">提供对属于活动配置文件中所有通讯簿提供程序的收件人信息的集成视图的访问。</span><span class="sxs-lookup"><span data-stu-id="56e48-124">Provides access to the integrated view of recipient information that belongs to all of the address book providers in the active profile.</span></span>  <br/> |
|<span data-ttu-id="56e48-125">邮件服务管理</span><span class="sxs-lookup"><span data-stu-id="56e48-125">Message service administration</span></span>  <br/> |<span data-ttu-id="56e48-126">提供对邮件服务信息的访问权限以用于配置。</span><span class="sxs-lookup"><span data-stu-id="56e48-126">Provides access to message service information for configuration.</span></span>  <br/> |
|<span data-ttu-id="56e48-127">配置文件管理</span><span class="sxs-lookup"><span data-stu-id="56e48-127">Profile administration</span></span>  <br/> |<span data-ttu-id="56e48-128">提供对配置文件信息的访问权限以用于配置。</span><span class="sxs-lookup"><span data-stu-id="56e48-128">Provides access to profile information for configuration.</span></span>  <br/> |
|<span data-ttu-id="56e48-129">配置文件部分</span><span class="sxs-lookup"><span data-stu-id="56e48-129">Profile section</span></span>  <br/> |<span data-ttu-id="56e48-130">用于描述特定邮件服务或服务提供商的配置文件的一部分。</span><span class="sxs-lookup"><span data-stu-id="56e48-130">A part of a profile used to describe a particular message service or service provider.</span></span>  <br/> |
|<span data-ttu-id="56e48-131">属性数据</span><span class="sxs-lookup"><span data-stu-id="56e48-131">Property data</span></span>  <br/> |<span data-ttu-id="56e48-132">维护对属性的访问权限，并帮助实现 **IMAPIProp**。</span><span class="sxs-lookup"><span data-stu-id="56e48-132">Maintains access to properties and helps implement **IMAPIProp**.</span></span>  <br/> |
|<span data-ttu-id="56e48-133">提供程序管理</span><span class="sxs-lookup"><span data-stu-id="56e48-133">Provider administration</span></span>  <br/> |<span data-ttu-id="56e48-134">提供对服务提供程序信息的访问权限以用于配置。</span><span class="sxs-lookup"><span data-stu-id="56e48-134">Provides access to service provider information for configuration.</span></span>  <br/> |
|<span data-ttu-id="56e48-135">会话</span><span class="sxs-lookup"><span data-stu-id="56e48-135">Session</span></span>  <br/> |<span data-ttu-id="56e48-136">表示与基础邮件系统的连接，并且向客户端提供对 MAPI 资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="56e48-136">Represents a connection to underlying messaging systems and provides clients with access to MAPI resources.</span></span>  <br/> |
|<span data-ttu-id="56e48-137">状态</span><span class="sxs-lookup"><span data-stu-id="56e48-137">Status</span></span>  <br/> |<span data-ttu-id="56e48-138">提供对 MAPI 子系统、通讯簿或 MAPI 后台处理程序的状态的访问。</span><span class="sxs-lookup"><span data-stu-id="56e48-138">Provides access to the state of the MAPI subsystem, the address book, or the MAPI spooler.</span></span>  <br/> |
|<span data-ttu-id="56e48-139">支持</span><span class="sxs-lookup"><span data-stu-id="56e48-139">Support</span></span>  <br/> |<span data-ttu-id="56e48-140">帮助服务提供商处理客户端请求。</span><span class="sxs-lookup"><span data-stu-id="56e48-140">Helps service providers handle client requests.</span></span>  <br/> |
|<span data-ttu-id="56e48-141">表格</span><span class="sxs-lookup"><span data-stu-id="56e48-141">Table</span></span>  <br/> |<span data-ttu-id="56e48-142">提供对行和列格式的对象数据的摘要视图的访问，类似于数据库表。</span><span class="sxs-lookup"><span data-stu-id="56e48-142">Provides access to a summary view of object data in row and column format, similar to a database table.</span></span>  <br/> |
|<span data-ttu-id="56e48-143">表数据</span><span class="sxs-lookup"><span data-stu-id="56e48-143">Table data</span></span>  <br/> |<span data-ttu-id="56e48-144">维护对基础表数据的访问，并实施表对象。</span><span class="sxs-lookup"><span data-stu-id="56e48-144">Maintains access to underlying table data and implements table objects.</span></span>  <br/> |
|<span data-ttu-id="56e48-145">TNEF</span><span class="sxs-lookup"><span data-stu-id="56e48-145">TNEF</span></span>  <br/> |<span data-ttu-id="56e48-146">支持使用传输中性封装格式 (TNEF) 。</span><span class="sxs-lookup"><span data-stu-id="56e48-146">Supports the use of the Transport Neutral Encapsulation Format (TNEF).</span></span>  <br/> |
   
<span data-ttu-id="56e48-147">下图显示了 MAPI 实现的对象、它们从其继承的接口以及使用它们的组件之间的关系。</span><span class="sxs-lookup"><span data-stu-id="56e48-147">The following illustration shows the relationship between the objects that MAPI implements, the interfaces from which they inherit, and the components that use them.</span></span> 
  
<span data-ttu-id="56e48-148">**MAPI 实现的对象**</span><span class="sxs-lookup"><span data-stu-id="56e48-148">**Objects that MAPI implements**</span></span>
  
<span data-ttu-id="56e48-149">![MAPI 实现 MAPI](media/amapi_68.gif "实现的对象的对象")</span><span class="sxs-lookup"><span data-stu-id="56e48-149">![Objects that MAPI implements](media/amapi_68.gif "Objects that MAPI implements")</span></span>
  
## <a name="see-also"></a><span data-ttu-id="56e48-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="56e48-150">See also</span></span>

- [<span data-ttu-id="56e48-151">IMAPIProp : IUnknown</span><span class="sxs-lookup"><span data-stu-id="56e48-151">IMAPIProp : IUnknown</span></span>](imapipropiunknown.md)
- [<span data-ttu-id="56e48-152">MAPI 对象和接口概述</span><span class="sxs-lookup"><span data-stu-id="56e48-152">MAPI Object and Interface Overview</span></span>](mapi-object-and-interface-overview.md)

