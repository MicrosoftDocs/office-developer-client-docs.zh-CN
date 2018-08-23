---
title: IMAPIStatus IMAPIProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIStatus
api_type:
- COM
ms.assetid: 17b2aa43-0267-45b6-8c57-11b7a5c67333
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 23663cea49c50f3f584d6b06e331545320e8283b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22565380"
---
# <a name="imapistatus--imapiprop"></a><span data-ttu-id="33628-103">IMAPIStatus : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="33628-103">IMAPIStatus : IMAPIProp</span></span>

  
  
<span data-ttu-id="33628-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="33628-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="33628-105">提供有关 MAPI 子系统、 集成的通讯簿中，和 MAPI 后台处理程序的状态信息。</span><span class="sxs-lookup"><span data-stu-id="33628-105">Provides status information about the MAPI subsystem, the integrated address book, and the MAPI spooler.</span></span> <span data-ttu-id="33628-106">服务提供商实现**IMAPIStatus**可提供有关其自身的状态信息。</span><span class="sxs-lookup"><span data-stu-id="33628-106">A service provider implements **IMAPIStatus** to supply information about its own status.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="33628-107">头文件：</span><span class="sxs-lookup"><span data-stu-id="33628-107">Header file:</span></span>  <br/> |<span data-ttu-id="33628-108">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="33628-108">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="33628-109">由公开：</span><span class="sxs-lookup"><span data-stu-id="33628-109">Exposed by:</span></span>  <br/> |<span data-ttu-id="33628-110">状态对象</span><span class="sxs-lookup"><span data-stu-id="33628-110">Status objects</span></span>  <br/> |
|<span data-ttu-id="33628-111">通过实现：</span><span class="sxs-lookup"><span data-stu-id="33628-111">Implemented by:</span></span>  <br/> |<span data-ttu-id="33628-112">服务提供商和 MAPI</span><span class="sxs-lookup"><span data-stu-id="33628-112">Service providers and MAPI</span></span>  <br/> |
|<span data-ttu-id="33628-113">调用：</span><span class="sxs-lookup"><span data-stu-id="33628-113">Called by:</span></span>  <br/> |<span data-ttu-id="33628-114">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="33628-114">Client applications</span></span>  <br/> |
|<span data-ttu-id="33628-115">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="33628-115">Interface identifier:</span></span>  <br/> |<span data-ttu-id="33628-116">IID_IMAPIStatus</span><span class="sxs-lookup"><span data-stu-id="33628-116">IID_IMAPIStatus</span></span>  <br/> |
|<span data-ttu-id="33628-117">指针类型：</span><span class="sxs-lookup"><span data-stu-id="33628-117">Pointer type:</span></span>  <br/> |<span data-ttu-id="33628-118">LPMAPISTATUS</span><span class="sxs-lookup"><span data-stu-id="33628-118">LPMAPISTATUS</span></span>  <br/> |
|<span data-ttu-id="33628-119">事务模型：</span><span class="sxs-lookup"><span data-stu-id="33628-119">Transaction model:</span></span>  <br/> |<span data-ttu-id="33628-120">Nontransacted</span><span class="sxs-lookup"><span data-stu-id="33628-120">Nontransacted</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="33628-121">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="33628-121">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="33628-122">ValidateState</span><span class="sxs-lookup"><span data-stu-id="33628-122">ValidateState</span></span>](imapistatus-validatestate.md) <br/> |<span data-ttu-id="33628-123">确认可供 MAPI 资源或服务提供商的外部状态信息。</span><span class="sxs-lookup"><span data-stu-id="33628-123">Confirms the external status information available for the MAPI resource or the service provider.</span></span>  <br/> |
|[<span data-ttu-id="33628-124">留待</span><span class="sxs-lookup"><span data-stu-id="33628-124">SettingsDialog</span></span>](imapistatus-settingsdialog.md) <br/> |<span data-ttu-id="33628-125">显示使用户能够更改服务提供商的配置的属性表。</span><span class="sxs-lookup"><span data-stu-id="33628-125">Displays a property sheet that enables the user to change a service provider's configuration.</span></span>  <br/> |
|[<span data-ttu-id="33628-126">ChangePassword</span><span class="sxs-lookup"><span data-stu-id="33628-126">ChangePassword</span></span>](imapistatus-changepassword.md) <br/> |<span data-ttu-id="33628-127">不显示用户界面中修改服务提供商的密码。</span><span class="sxs-lookup"><span data-stu-id="33628-127">Modifies a service provider's password without displaying a user interface.</span></span>  <br/> |
|[<span data-ttu-id="33628-128">FlushQueues</span><span class="sxs-lookup"><span data-stu-id="33628-128">FlushQueues</span></span>](imapistatus-flushqueues.md) <br/> |<span data-ttu-id="33628-129">强制等待发送或接收立即上载或下载的所有邮件。</span><span class="sxs-lookup"><span data-stu-id="33628-129">Forces all messages waiting to be sent or received to be immediately uploaded or downloaded.</span></span>  <br/> |
   
|<span data-ttu-id="33628-130">**必需属性**</span><span class="sxs-lookup"><span data-stu-id="33628-130">**Required properties**</span></span>|<span data-ttu-id="33628-131">**Access**</span><span class="sxs-lookup"><span data-stu-id="33628-131">**Access**</span></span>|
|:-----|:-----|
|<span data-ttu-id="33628-132">**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="33628-132">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="33628-133">读/写</span><span class="sxs-lookup"><span data-stu-id="33628-133">Read/write</span></span>  <br/> |
|<span data-ttu-id="33628-134">**PR_PROVIDER_DISPLAY**([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="33628-134">**PR_PROVIDER_DISPLAY** ([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="33628-135">读/写</span><span class="sxs-lookup"><span data-stu-id="33628-135">Read/write</span></span>  <br/> |
|<span data-ttu-id="33628-136">**PR_PROVIDER_DLL_NAME**([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="33628-136">**PR_PROVIDER_DLL_NAME** ([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="33628-137">只读</span><span class="sxs-lookup"><span data-stu-id="33628-137">Read-only</span></span>  <br/> |
|<span data-ttu-id="33628-138">**PR_RESOURCE_FLAGS**([PidTagResourceFlags](pidtagresourceflags-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="33628-138">**PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="33628-139">只读</span><span class="sxs-lookup"><span data-stu-id="33628-139">Read-only</span></span>  <br/> |
|<span data-ttu-id="33628-140">**PR_RESOURCE_METHODS**([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="33628-140">**PR_RESOURCE_METHODS** ([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="33628-141">只读</span><span class="sxs-lookup"><span data-stu-id="33628-141">Read-only</span></span>  <br/> |
|<span data-ttu-id="33628-142">**PR_RESOURCE_TYPE**([PidTagResourceType](pidtagresourcetype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="33628-142">**PR_RESOURCE_TYPE** ([PidTagResourceType](pidtagresourcetype-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="33628-143">只读</span><span class="sxs-lookup"><span data-stu-id="33628-143">Read-only</span></span>  <br/> |
|<span data-ttu-id="33628-144">**PR_STATUS_CODE**([PidTagStatusCode](pidtagstatuscode-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="33628-144">**PR_STATUS_CODE** ([PidTagStatusCode](pidtagstatuscode-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="33628-145">只读</span><span class="sxs-lookup"><span data-stu-id="33628-145">Read-only</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="33628-146">注解</span><span class="sxs-lookup"><span data-stu-id="33628-146">Remarks</span></span>

<span data-ttu-id="33628-147">MAPI 实现的状态对象支持下列方法：</span><span class="sxs-lookup"><span data-stu-id="33628-147">The status objects that MAPI implements support the following methods:</span></span>
  
|<span data-ttu-id="33628-148">**状态对象**</span><span class="sxs-lookup"><span data-stu-id="33628-148">**Status object**</span></span>|<span data-ttu-id="33628-149">**受支持的方法**</span><span class="sxs-lookup"><span data-stu-id="33628-149">**Supported methods**</span></span>|
|:-----|:-----|
|<span data-ttu-id="33628-150">MAPI 子系统</span><span class="sxs-lookup"><span data-stu-id="33628-150">MAPI subsystem</span></span>  <br/> |<span data-ttu-id="33628-151">仅**ValidateState**</span><span class="sxs-lookup"><span data-stu-id="33628-151">**ValidateState** only</span></span>  <br/> |
|<span data-ttu-id="33628-152">MAPI 通讯簿</span><span class="sxs-lookup"><span data-stu-id="33628-152">MAPI address book</span></span>  <br/> |<span data-ttu-id="33628-153">仅**ValidateState**</span><span class="sxs-lookup"><span data-stu-id="33628-153">**ValidateState** only</span></span>  <br/> |
|<span data-ttu-id="33628-154">MAPI 后台处理程序</span><span class="sxs-lookup"><span data-stu-id="33628-154">MAPI spooler</span></span>  <br/> |<span data-ttu-id="33628-155">**ValidateState**和**FlushQueues**</span><span class="sxs-lookup"><span data-stu-id="33628-155">**ValidateState** and **FlushQueues**</span></span> <br/> |
   
<span data-ttu-id="33628-156">MAPI 实现的状态对象所需具有[IMAPIProp](imapipropiunknown.md)接口的方法的只读版本和以支持**ValidateState**方法。</span><span class="sxs-lookup"><span data-stu-id="33628-156">The status objects that MAPI implements are required to have a read-only version of the methods of the [IMAPIProp](imapipropiunknown.md) interface and to support the **ValidateState** method.</span></span> <span data-ttu-id="33628-157">传输提供程序还应支持**FlushQueues**。</span><span class="sxs-lookup"><span data-stu-id="33628-157">Transport providers should also support **FlushQueues**.</span></span> <span data-ttu-id="33628-158">所有提供程序应支持**留待**;支持**ChangePassword**是可选的。</span><span class="sxs-lookup"><span data-stu-id="33628-158">All providers should support **SettingsDialog**; support for **ChangePassword** is optional.</span></span> 
  
<span data-ttu-id="33628-159">客户端使用状态对象执行配置并了解会话的状态。</span><span class="sxs-lookup"><span data-stu-id="33628-159">Clients use status objects to perform configuration and to learn about the state of the session.</span></span> <span data-ttu-id="33628-160">他们可以通过调用服务提供商登录对象的**OpenStatusEntry**方法或[IMAPISession::GetStatusTable](imapisession-getstatustable.md)方法来检索状态对象访问状态对象。</span><span class="sxs-lookup"><span data-stu-id="33628-160">They access a status object by calling the **OpenStatusEntry** method of a service provider logon object or the [IMAPISession::GetStatusTable](imapisession-getstatustable.md) method to retrieve the status object.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="33628-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="33628-161">See also</span></span>



[<span data-ttu-id="33628-162">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="33628-162">MAPI Interfaces</span></span>](mapi-interfaces.md)

