---
title: MAPI 服务提供商对象
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f8ade454-2450-49e6-a76f-93801055a7e5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 85a67216822360bcaf9544389f79980891951757
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584854"
---
# <a name="mapi-service-provider-objects"></a><span data-ttu-id="c92cc-103">MAPI 服务提供商对象</span><span class="sxs-lookup"><span data-stu-id="c92cc-103">MAPI Service Provider Objects</span></span>

  
  
<span data-ttu-id="c92cc-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c92cc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c92cc-105">服务提供程序实现多个对象。</span><span class="sxs-lookup"><span data-stu-id="c92cc-105">Service providers implement many objects.</span></span> <span data-ttu-id="c92cc-106">某些使用 MAPI 的主要和一些使用客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="c92cc-106">Some are used primarily by MAPI and some are used by client applications.</span></span> <span data-ttu-id="c92cc-107">所有类型的服务提供商; 由实现几个对象rest 是特定于单个提供程序类型。</span><span class="sxs-lookup"><span data-stu-id="c92cc-107">A few objects are implemented by all types of service providers; the rest are specific to a single provider type.</span></span> <span data-ttu-id="c92cc-108">下表介绍的所有服务提供商对象。</span><span class="sxs-lookup"><span data-stu-id="c92cc-108">The following table describes all of the service provider objects.</span></span>
  
|<span data-ttu-id="c92cc-109">**服务提供商对象**</span><span class="sxs-lookup"><span data-stu-id="c92cc-109">**Service provider object**</span></span>|<span data-ttu-id="c92cc-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="c92cc-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c92cc-111">通讯簿容器</span><span class="sxs-lookup"><span data-stu-id="c92cc-111">Address book container</span></span>  <br/> |<span data-ttu-id="c92cc-112">包含一个通讯簿提供程序中的活动配置文件; 收件人信息通讯簿提供程序可以具有一个或多个地址簿容器。</span><span class="sxs-lookup"><span data-stu-id="c92cc-112">Contains recipient information for one address book provider in the active profile; address book providers can have one or more address book containers.</span></span>  <br/> |
|<span data-ttu-id="c92cc-113">附件</span><span class="sxs-lookup"><span data-stu-id="c92cc-113">Attachment</span></span>  <br/> |<span data-ttu-id="c92cc-114">包含其他数据，如文件或 OLE 对象，与邮件相关联。</span><span class="sxs-lookup"><span data-stu-id="c92cc-114">Contains additional data, such as a file or OLE object, to be associated with a message.</span></span>  <br/> |
|<span data-ttu-id="c92cc-115">Control</span><span class="sxs-lookup"><span data-stu-id="c92cc-115">Control</span></span>  <br/> |<span data-ttu-id="c92cc-116">启用或禁用按钮并启动处理单击按钮时。</span><span class="sxs-lookup"><span data-stu-id="c92cc-116">Enables or disables a button and initiates processing when the button is clicked.</span></span>  <br/> |
|<span data-ttu-id="c92cc-117">通讯组列表</span><span class="sxs-lookup"><span data-stu-id="c92cc-117">Distribution list</span></span>  <br/> |<span data-ttu-id="c92cc-118">描述单个邮件的收件人的分组。</span><span class="sxs-lookup"><span data-stu-id="c92cc-118">Describes a grouping of individual message recipients.</span></span>  <br/> |
|<span data-ttu-id="c92cc-119">Folder</span><span class="sxs-lookup"><span data-stu-id="c92cc-119">Folder</span></span>  <br/> |<span data-ttu-id="c92cc-120">包含消息以及其他消息容器。</span><span class="sxs-lookup"><span data-stu-id="c92cc-120">Contains messages and other message containers.</span></span>  <br/> |
|<span data-ttu-id="c92cc-121">登录</span><span class="sxs-lookup"><span data-stu-id="c92cc-121">Logon</span></span>  <br/> |<span data-ttu-id="c92cc-122">处理服务提供程序的事件通知和客户端请求。</span><span class="sxs-lookup"><span data-stu-id="c92cc-122">Handles service provider event notification and client requests.</span></span>  <br/> |
|<span data-ttu-id="c92cc-123">邮件用户</span><span class="sxs-lookup"><span data-stu-id="c92cc-123">Messaging user</span></span>  <br/> |<span data-ttu-id="c92cc-124">描述单个收件人的邮件。</span><span class="sxs-lookup"><span data-stu-id="c92cc-124">Describes an individual recipient of a message.</span></span>  <br/> |
|<span data-ttu-id="c92cc-125">Message</span><span class="sxs-lookup"><span data-stu-id="c92cc-125">Message</span></span>  <br/> |<span data-ttu-id="c92cc-126">包含可被发送到一个或多个收件人的信息。</span><span class="sxs-lookup"><span data-stu-id="c92cc-126">Contains information that can be sent to one or more recipients.</span></span>  <br/> |
|<span data-ttu-id="c92cc-127">消息存储库</span><span class="sxs-lookup"><span data-stu-id="c92cc-127">Message store</span></span>  <br/> |<span data-ttu-id="c92cc-128">用作按层次结构组织的数据库的消息。</span><span class="sxs-lookup"><span data-stu-id="c92cc-128">Acts as a hierarchically organized database of messages.</span></span>  <br/> |
|<span data-ttu-id="c92cc-129">提供程序</span><span class="sxs-lookup"><span data-stu-id="c92cc-129">Provider</span></span>  <br/> |<span data-ttu-id="c92cc-130">处理服务提供程序启动和关机。</span><span class="sxs-lookup"><span data-stu-id="c92cc-130">Handles service provider startup and shutdown.</span></span>  <br/> |
|<span data-ttu-id="c92cc-131">后台处理程序挂接</span><span class="sxs-lookup"><span data-stu-id="c92cc-131">Spooler hook</span></span>  <br/> |<span data-ttu-id="c92cc-132">对入站和出站邮件执行特殊处理。</span><span class="sxs-lookup"><span data-stu-id="c92cc-132">Performs special processing on inbound and outbound messages.</span></span>  <br/> |
|<span data-ttu-id="c92cc-133">Status</span><span class="sxs-lookup"><span data-stu-id="c92cc-133">Status</span></span>  <br/> |<span data-ttu-id="c92cc-134">提供对服务提供商的状态的访问。</span><span class="sxs-lookup"><span data-stu-id="c92cc-134">Provides access to the service provider's state.</span></span>  <br/> |
|<span data-ttu-id="c92cc-135">Table</span><span class="sxs-lookup"><span data-stu-id="c92cc-135">Table</span></span>  <br/> |<span data-ttu-id="c92cc-136">提供对行和列的格式，类似于数据库表中的对象数据的摘要视图访问。</span><span class="sxs-lookup"><span data-stu-id="c92cc-136">Provides access to a summary view of object data in row and column format, similar to a database table.</span></span>  <br/> |
   
<span data-ttu-id="c92cc-137">所有服务提供商都实现提供程序对象和登录对象。</span><span class="sxs-lookup"><span data-stu-id="c92cc-137">All service providers implement a provider object and a logon object.</span></span> <span data-ttu-id="c92cc-138">提供商对象仅限用于记帐;他们使用 MAPI 控制启动和关机进程。</span><span class="sxs-lookup"><span data-stu-id="c92cc-138">Provider objects are strictly for bookkeeping; they are used by MAPI to control the startup and shutdown processes.</span></span> <span data-ttu-id="c92cc-139">登录对象间接某些客户端请求提供服务。</span><span class="sxs-lookup"><span data-stu-id="c92cc-139">Logon objects service some client requests indirectly.</span></span> <span data-ttu-id="c92cc-140">例如，消息存储提供程序的登录对象处理通知注册和请求以打开消息存储对象。</span><span class="sxs-lookup"><span data-stu-id="c92cc-140">For example, the message store provider's logon object handles notification registration and requests to open message store objects.</span></span> 
  
<span data-ttu-id="c92cc-141">提供程序和登录对象实现不同的接口，具体取决于服务提供程序提供实现的类型。</span><span class="sxs-lookup"><span data-stu-id="c92cc-141">Provider and logon objects implement a different interface depending on the type of service provider that supplies the implementation.</span></span> <span data-ttu-id="c92cc-142">消息存储提供程序实现[IMSProvider: IUnknown](imsprovideriunknown.md)和[IMSLogon: IUnknown](imslogoniunknown.md)接口在其提供程序和登录对象中，通讯簿提供程序实现[IABProvider: IUnknown](iabprovideriunknown.md)和[IABLogon: IUnknown](iablogoniunknown.md)接口和传输提供程序实现[IXPProvider: IUnknown](ixpprovideriunknown.md)和[IXPLogon: IUnknown](ixplogoniunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="c92cc-142">A message store provider implements the [IMSProvider : IUnknown](imsprovideriunknown.md) and [IMSLogon : IUnknown](imslogoniunknown.md) interfaces in its provider and logon objects, an address book provider implements the [IABProvider : IUnknown](iabprovideriunknown.md) and [IABLogon : IUnknown](iablogoniunknown.md) interfaces, and a transport provider implements the [IXPProvider : IUnknown](ixpprovideriunknown.md) and [IXPLogon : IUnknown](ixplogoniunknown.md) interfaces.</span></span> 
  
<span data-ttu-id="c92cc-143">消息挂接提供程序实现后台处理程序挂接对象或筛选入站和出站邮件的对象。</span><span class="sxs-lookup"><span data-stu-id="c92cc-143">Message hook providers implement spooler hook objects, or objects that filter inbound and outbound messages.</span></span>
  
<span data-ttu-id="c92cc-144">服务提供商通常使用只有少数对象。</span><span class="sxs-lookup"><span data-stu-id="c92cc-144">Service providers typically use only a few objects.</span></span> <span data-ttu-id="c92cc-145">通常，它们使用 MAPI 提供可帮助实现客户端请求的支持对象。</span><span class="sxs-lookup"><span data-stu-id="c92cc-145">Most frequently, they use a support object that MAPI provides to help implement client requests.</span></span> <span data-ttu-id="c92cc-146">正在使用它的提供程序的类型为自定义的支持对象。</span><span class="sxs-lookup"><span data-stu-id="c92cc-146">The support object is customized for the type of provider that is using it.</span></span> <span data-ttu-id="c92cc-147">对于所有服务提供程序，支持对象包含用于处理事件通知，并显示配置属性、 打开对象和错误处理方法。</span><span class="sxs-lookup"><span data-stu-id="c92cc-147">For all service providers, the support object includes methods for handling event notification, displaying configuration properties, opening objects, and error handling.</span></span> <span data-ttu-id="c92cc-148">其余方法是特定于其使用;有自定义的通讯簿、 消息存储和传输提供程序和配置支持的版本。</span><span class="sxs-lookup"><span data-stu-id="c92cc-148">The rest of the methods are specific to its use; there are customized versions for address book, message store, and transport providers, and for configuration support.</span></span> <span data-ttu-id="c92cc-149">例如，通讯簿支持对象显示详细信息和收件人的自定义对话框。</span><span class="sxs-lookup"><span data-stu-id="c92cc-149">For example, the address book support object displays details and custom recipient dialog boxes.</span></span> <span data-ttu-id="c92cc-150">消息存储库支持对象支持复制和移动的文件夹和邮件的操作。</span><span class="sxs-lookup"><span data-stu-id="c92cc-150">The message store support object supports copy and move operations for folders and messages.</span></span> <span data-ttu-id="c92cc-151">传输提供程序支持对象包含用于简化 MAPI 后台处理程序的交互的方法。</span><span class="sxs-lookup"><span data-stu-id="c92cc-151">The transport provider support object includes methods for facilitating interaction with the MAPI spooler.</span></span> 
  
<span data-ttu-id="c92cc-152">某些服务提供商使用表数据和属性数据对象 — MAPI 实现的实用程序对象。</span><span class="sxs-lookup"><span data-stu-id="c92cc-152">Some service providers use table data and property data objects — utility objects that MAPI implements.</span></span> <span data-ttu-id="c92cc-153">表格数据对象启用服务提供商管理基础表的数据。</span><span class="sxs-lookup"><span data-stu-id="c92cc-153">Table data objects enable service providers to manage the underlying data of a table.</span></span> <span data-ttu-id="c92cc-154">属性数据对象启用服务提供商设置对象和属性的访问。</span><span class="sxs-lookup"><span data-stu-id="c92cc-154">Property data objects enable service providers to set object and property access.</span></span> 
  
<span data-ttu-id="c92cc-155">传输提供程序支持传输中性封装格式 (TNEF) 用于转接属性使用 TNEF 对象 MAPI 实现支持的[ITnef: IUnknown](itnefiunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="c92cc-155">Transport providers that support the Transport Neutral Encapsulation Format (TNEF) for transferring properties use a TNEF object that MAPI implements to support the [ITnef : IUnknown](itnefiunknown.md) interface.</span></span> <span data-ttu-id="c92cc-156">有关详细信息，请参阅[开发 TNEF-Enabled 传输提供程序](developing-a-tnef-enabled-transport-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="c92cc-156">For more information, see [Developing a TNEF-Enabled Transport Provider](developing-a-tnef-enabled-transport-provider.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="c92cc-157">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c92cc-157">See also</span></span>



[<span data-ttu-id="c92cc-158">ITnef : IUnknown</span><span class="sxs-lookup"><span data-stu-id="c92cc-158">ITnef : IUnknown</span></span>](itnefiunknown.md)
  
[<span data-ttu-id="c92cc-159">IMSProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="c92cc-159">IMSProvider : IUnknown</span></span>](imsprovideriunknown.md)
  
[<span data-ttu-id="c92cc-160">IMSLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="c92cc-160">IMSLogon : IUnknown</span></span>](imslogoniunknown.md)
  
[<span data-ttu-id="c92cc-161">IABProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="c92cc-161">IABProvider : IUnknown</span></span>](iabprovideriunknown.md)
  
[<span data-ttu-id="c92cc-162">IABLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="c92cc-162">IABLogon : IUnknown</span></span>](iablogoniunknown.md)
  
[<span data-ttu-id="c92cc-163">IXPProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="c92cc-163">IXPProvider : IUnknown</span></span>](ixpprovideriunknown.md)
  
[<span data-ttu-id="c92cc-164">IXPLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="c92cc-164">IXPLogon : IUnknown</span></span>](ixplogoniunknown.md)


[<span data-ttu-id="c92cc-165">开发已启用 TNEF 的传输提供程序</span><span class="sxs-lookup"><span data-stu-id="c92cc-165">Developing a TNEF-Enabled Transport Provider</span></span>](developing-a-tnef-enabled-transport-provider.md)

