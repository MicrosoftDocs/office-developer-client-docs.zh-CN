---
title: MAPI 服务提供程序对象
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f8ade454-2450-49e6-a76f-93801055a7e5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0976e986a33d8b96366a84527f227bd05ef7845e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32251603"
---
# <a name="mapi-service-provider-objects"></a><span data-ttu-id="34b86-103">MAPI 服务提供程序对象</span><span class="sxs-lookup"><span data-stu-id="34b86-103">MAPI Service Provider Objects</span></span>

  
  
<span data-ttu-id="34b86-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="34b86-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="34b86-105">服务提供程序实现许多对象。</span><span class="sxs-lookup"><span data-stu-id="34b86-105">Service providers implement many objects.</span></span> <span data-ttu-id="34b86-106">一些主要由 MAPI 使用, 一些由客户端应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="34b86-106">Some are used primarily by MAPI and some are used by client applications.</span></span> <span data-ttu-id="34b86-107">一些对象由所有类型的服务提供程序实现;其余内容特定于单个提供程序类型。</span><span class="sxs-lookup"><span data-stu-id="34b86-107">A few objects are implemented by all types of service providers; the rest are specific to a single provider type.</span></span> <span data-ttu-id="34b86-108">下表介绍了所有服务提供程序对象。</span><span class="sxs-lookup"><span data-stu-id="34b86-108">The following table describes all of the service provider objects.</span></span>
  
|<span data-ttu-id="34b86-109">**服务提供程序对象**</span><span class="sxs-lookup"><span data-stu-id="34b86-109">**Service provider object**</span></span>|<span data-ttu-id="34b86-110">**Description**</span><span class="sxs-lookup"><span data-stu-id="34b86-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="34b86-111">通讯簿容器</span><span class="sxs-lookup"><span data-stu-id="34b86-111">Address book container</span></span>  <br/> |<span data-ttu-id="34b86-112">包含活动配置文件中一个通讯簿提供程序的收件人信息;通讯簿提供程序可以有一个或多个通讯簿容器。</span><span class="sxs-lookup"><span data-stu-id="34b86-112">Contains recipient information for one address book provider in the active profile; address book providers can have one or more address book containers.</span></span>  <br/> |
|<span data-ttu-id="34b86-113">附件</span><span class="sxs-lookup"><span data-stu-id="34b86-113">Attachment</span></span>  <br/> |<span data-ttu-id="34b86-114">包含要与邮件相关联的其他数据 (如文件或 OLE 对象)。</span><span class="sxs-lookup"><span data-stu-id="34b86-114">Contains additional data, such as a file or OLE object, to be associated with a message.</span></span>  <br/> |
|<span data-ttu-id="34b86-115">Control</span><span class="sxs-lookup"><span data-stu-id="34b86-115">Control</span></span>  <br/> |<span data-ttu-id="34b86-116">启用或禁用按钮, 并在单击按钮时启动处理。</span><span class="sxs-lookup"><span data-stu-id="34b86-116">Enables or disables a button and initiates processing when the button is clicked.</span></span>  <br/> |
|<span data-ttu-id="34b86-117">通讯组列表</span><span class="sxs-lookup"><span data-stu-id="34b86-117">Distribution list</span></span>  <br/> |<span data-ttu-id="34b86-118">描述单个邮件收件人的分组。</span><span class="sxs-lookup"><span data-stu-id="34b86-118">Describes a grouping of individual message recipients.</span></span>  <br/> |
|<span data-ttu-id="34b86-119">Folder</span><span class="sxs-lookup"><span data-stu-id="34b86-119">Folder</span></span>  <br/> |<span data-ttu-id="34b86-120">包含邮件和其他消息容器。</span><span class="sxs-lookup"><span data-stu-id="34b86-120">Contains messages and other message containers.</span></span>  <br/> |
|<span data-ttu-id="34b86-121">登录</span><span class="sxs-lookup"><span data-stu-id="34b86-121">Logon</span></span>  <br/> |<span data-ttu-id="34b86-122">处理服务提供程序事件通知和客户端请求。</span><span class="sxs-lookup"><span data-stu-id="34b86-122">Handles service provider event notification and client requests.</span></span>  <br/> |
|<span data-ttu-id="34b86-123">邮件用户</span><span class="sxs-lookup"><span data-stu-id="34b86-123">Messaging user</span></span>  <br/> |<span data-ttu-id="34b86-124">描述邮件的单个收件人。</span><span class="sxs-lookup"><span data-stu-id="34b86-124">Describes an individual recipient of a message.</span></span>  <br/> |
|<span data-ttu-id="34b86-125">消息</span><span class="sxs-lookup"><span data-stu-id="34b86-125">Message</span></span>  <br/> |<span data-ttu-id="34b86-126">包含可发送给一个或多个收件人的信息。</span><span class="sxs-lookup"><span data-stu-id="34b86-126">Contains information that can be sent to one or more recipients.</span></span>  <br/> |
|<span data-ttu-id="34b86-127">邮件存储</span><span class="sxs-lookup"><span data-stu-id="34b86-127">Message store</span></span>  <br/> |<span data-ttu-id="34b86-128">充当以分层方式组织的邮件数据库。</span><span class="sxs-lookup"><span data-stu-id="34b86-128">Acts as a hierarchically organized database of messages.</span></span>  <br/> |
|<span data-ttu-id="34b86-129">提供程序</span><span class="sxs-lookup"><span data-stu-id="34b86-129">Provider</span></span>  <br/> |<span data-ttu-id="34b86-130">处理服务提供程序启动和关闭。</span><span class="sxs-lookup"><span data-stu-id="34b86-130">Handles service provider startup and shutdown.</span></span>  <br/> |
|<span data-ttu-id="34b86-131">后台打印程序挂钩</span><span class="sxs-lookup"><span data-stu-id="34b86-131">Spooler hook</span></span>  <br/> |<span data-ttu-id="34b86-132">对入站和出站邮件执行特殊处理。</span><span class="sxs-lookup"><span data-stu-id="34b86-132">Performs special processing on inbound and outbound messages.</span></span>  <br/> |
|<span data-ttu-id="34b86-133">状态</span><span class="sxs-lookup"><span data-stu-id="34b86-133">Status</span></span>  <br/> |<span data-ttu-id="34b86-134">提供对服务提供程序状态的访问权限。</span><span class="sxs-lookup"><span data-stu-id="34b86-134">Provides access to the service provider's state.</span></span>  <br/> |
|<span data-ttu-id="34b86-135">Table</span><span class="sxs-lookup"><span data-stu-id="34b86-135">Table</span></span>  <br/> |<span data-ttu-id="34b86-136">提供对行和列格式的对象数据的摘要视图, 与数据库表类似。</span><span class="sxs-lookup"><span data-stu-id="34b86-136">Provides access to a summary view of object data in row and column format, similar to a database table.</span></span>  <br/> |
   
<span data-ttu-id="34b86-137">所有服务提供程序都实现一个提供程序对象和一个登录对象。</span><span class="sxs-lookup"><span data-stu-id="34b86-137">All service providers implement a provider object and a logon object.</span></span> <span data-ttu-id="34b86-138">提供程序对象完全用于簿记;MAPI 使用它们来控制启动和关闭进程。</span><span class="sxs-lookup"><span data-stu-id="34b86-138">Provider objects are strictly for bookkeeping; they are used by MAPI to control the startup and shutdown processes.</span></span> <span data-ttu-id="34b86-139">登录对象间接服务一些客户端请求。</span><span class="sxs-lookup"><span data-stu-id="34b86-139">Logon objects service some client requests indirectly.</span></span> <span data-ttu-id="34b86-140">例如, 邮件存储提供程序的登录对象处理通知注册和打开邮件存储对象的请求。</span><span class="sxs-lookup"><span data-stu-id="34b86-140">For example, the message store provider's logon object handles notification registration and requests to open message store objects.</span></span> 
  
<span data-ttu-id="34b86-141">提供程序和登录对象实现不同的接口, 具体取决于提供实现的服务提供程序的类型。</span><span class="sxs-lookup"><span data-stu-id="34b86-141">Provider and logon objects implement a different interface depending on the type of service provider that supplies the implementation.</span></span> <span data-ttu-id="34b86-142">邮件存储提供程序在其提供程序和登录对象中实现[IMSProvider: iunknown](imsprovideriunknown.md)和[IMSLogon: iunknown](imslogoniunknown.md)接口, 通讯簿提供程序实现[IABProvider: iunknown](iabprovideriunknown.md)和[IABLogon: iunknown](iablogoniunknown.md)接口, 传输提供程序实现[IXPProvider: iunknown](ixpprovideriunknown.md)和[IXPLogon: iunknown](ixplogoniunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="34b86-142">A message store provider implements the [IMSProvider : IUnknown](imsprovideriunknown.md) and [IMSLogon : IUnknown](imslogoniunknown.md) interfaces in its provider and logon objects, an address book provider implements the [IABProvider : IUnknown](iabprovideriunknown.md) and [IABLogon : IUnknown](iablogoniunknown.md) interfaces, and a transport provider implements the [IXPProvider : IUnknown](ixpprovideriunknown.md) and [IXPLogon : IUnknown](ixplogoniunknown.md) interfaces.</span></span> 
  
<span data-ttu-id="34b86-143">消息挂钩提供程序实现假脱机处理程序挂钩对象或筛选入站和出站邮件的对象。</span><span class="sxs-lookup"><span data-stu-id="34b86-143">Message hook providers implement spooler hook objects, or objects that filter inbound and outbound messages.</span></span>
  
<span data-ttu-id="34b86-144">服务提供商通常仅使用少数几个对象。</span><span class="sxs-lookup"><span data-stu-id="34b86-144">Service providers typically use only a few objects.</span></span> <span data-ttu-id="34b86-145">通常, 它们使用 MAPI 提供的支持对象来帮助实现客户端请求。</span><span class="sxs-lookup"><span data-stu-id="34b86-145">Most frequently, they use a support object that MAPI provides to help implement client requests.</span></span> <span data-ttu-id="34b86-146">支持对象是针对使用它的提供程序的类型进行自定义的。</span><span class="sxs-lookup"><span data-stu-id="34b86-146">The support object is customized for the type of provider that is using it.</span></span> <span data-ttu-id="34b86-147">对于所有服务提供程序, 支持对象包括处理事件通知、显示配置属性、打开对象和错误处理的方法。</span><span class="sxs-lookup"><span data-stu-id="34b86-147">For all service providers, the support object includes methods for handling event notification, displaying configuration properties, opening objects, and error handling.</span></span> <span data-ttu-id="34b86-148">其余方法特定于其用途;通讯簿、邮件存储和传输提供程序以及配置支持的自定义版本。</span><span class="sxs-lookup"><span data-stu-id="34b86-148">The rest of the methods are specific to its use; there are customized versions for address book, message store, and transport providers, and for configuration support.</span></span> <span data-ttu-id="34b86-149">例如, 通讯簿支持对象显示详细信息和自定义收件人对话框。</span><span class="sxs-lookup"><span data-stu-id="34b86-149">For example, the address book support object displays details and custom recipient dialog boxes.</span></span> <span data-ttu-id="34b86-150">邮件存储区支持对象支持文件夹和邮件的复制和移动操作。</span><span class="sxs-lookup"><span data-stu-id="34b86-150">The message store support object supports copy and move operations for folders and messages.</span></span> <span data-ttu-id="34b86-151">传输提供程序支持对象包括用于促进与 MAPI 后台处理程序的交互的方法。</span><span class="sxs-lookup"><span data-stu-id="34b86-151">The transport provider support object includes methods for facilitating interaction with the MAPI spooler.</span></span> 
  
<span data-ttu-id="34b86-152">某些服务提供程序使用表数据和属性数据对象, 即 MAPI 实现的实用工具对象。</span><span class="sxs-lookup"><span data-stu-id="34b86-152">Some service providers use table data and property data objects — utility objects that MAPI implements.</span></span> <span data-ttu-id="34b86-153">表数据对象使服务提供程序可以管理表的基础数据。</span><span class="sxs-lookup"><span data-stu-id="34b86-153">Table data objects enable service providers to manage the underlying data of a table.</span></span> <span data-ttu-id="34b86-154">使用属性数据对象, 服务提供程序可以设置对象和属性访问。</span><span class="sxs-lookup"><span data-stu-id="34b86-154">Property data objects enable service providers to set object and property access.</span></span> 
  
<span data-ttu-id="34b86-155">支持传输中性封装格式 (TNEF) 以传输属性的传输提供程序使用 MAPI 实现的 TNEF 对象来支持[ITnef: IUnknown](itnefiunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="34b86-155">Transport providers that support the Transport Neutral Encapsulation Format (TNEF) for transferring properties use a TNEF object that MAPI implements to support the [ITnef : IUnknown](itnefiunknown.md) interface.</span></span> <span data-ttu-id="34b86-156">有关详细信息, 请参阅[开发启用 TNEF 的传输提供程序](developing-a-tnef-enabled-transport-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="34b86-156">For more information, see [Developing a TNEF-Enabled Transport Provider](developing-a-tnef-enabled-transport-provider.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="34b86-157">另请参阅</span><span class="sxs-lookup"><span data-stu-id="34b86-157">See also</span></span>



[<span data-ttu-id="34b86-158">ITnef : IUnknown</span><span class="sxs-lookup"><span data-stu-id="34b86-158">ITnef : IUnknown</span></span>](itnefiunknown.md)
  
[<span data-ttu-id="34b86-159">IMSProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="34b86-159">IMSProvider : IUnknown</span></span>](imsprovideriunknown.md)
  
[<span data-ttu-id="34b86-160">IMSLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="34b86-160">IMSLogon : IUnknown</span></span>](imslogoniunknown.md)
  
[<span data-ttu-id="34b86-161">IABProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="34b86-161">IABProvider : IUnknown</span></span>](iabprovideriunknown.md)
  
[<span data-ttu-id="34b86-162">IABLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="34b86-162">IABLogon : IUnknown</span></span>](iablogoniunknown.md)
  
[<span data-ttu-id="34b86-163">IXPProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="34b86-163">IXPProvider : IUnknown</span></span>](ixpprovideriunknown.md)
  
[<span data-ttu-id="34b86-164">IXPLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="34b86-164">IXPLogon : IUnknown</span></span>](ixplogoniunknown.md)


[<span data-ttu-id="34b86-165">开发启用了 TNEF 的传输提供程序</span><span class="sxs-lookup"><span data-stu-id="34b86-165">Developing a TNEF-Enabled Transport Provider</span></span>](developing-a-tnef-enabled-transport-provider.md)

