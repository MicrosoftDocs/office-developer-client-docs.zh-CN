---
title: IMAPIStatusValidateState
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIStatus.ValidateState
api_type:
- COM
ms.assetid: 036b9b15-86e1-4a37-8e4b-e37b2963d8fb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: adcdf04653f8c9fed2ecc6520648abd3acd36134
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438146"
---
# <a name="imapistatusvalidatestate"></a><span data-ttu-id="d6068-103">IMAPIStatus::ValidateState</span><span class="sxs-lookup"><span data-stu-id="d6068-103">IMAPIStatus::ValidateState</span></span>

<span data-ttu-id="d6068-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d6068-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d6068-105">确认可用于 MAPI 资源或服务提供商的外部状态信息。</span><span class="sxs-lookup"><span data-stu-id="d6068-105">Confirms the external status information available for the MAPI resource or the service provider.</span></span> <span data-ttu-id="d6068-106">在所有 status 对象中都支持此方法。</span><span class="sxs-lookup"><span data-stu-id="d6068-106">This method is supported in all status objects.</span></span> 
  
```cpp
HRESULT ValidateState(
  ULONG_PTR ulUIParam,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="d6068-107">参数</span><span class="sxs-lookup"><span data-stu-id="d6068-107">Parameters</span></span>

<span data-ttu-id="d6068-108">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="d6068-108">_ulUIParam_</span></span>
  
> <span data-ttu-id="d6068-109">实时此方法显示的任何对话框或窗口的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="d6068-109">[in] A handle to the parent window of any dialog boxes or windows that this method displays.</span></span>
    
<span data-ttu-id="d6068-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="d6068-110">_ulFlags_</span></span>
  
> <span data-ttu-id="d6068-111">实时控制验证的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="d6068-111">[in] A bitmask of flags that controls the validation.</span></span> <span data-ttu-id="d6068-112">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="d6068-112">The following flags can be set:</span></span>
    
<span data-ttu-id="d6068-113">ABORT_XP_HEADER_OPERATION</span><span class="sxs-lookup"><span data-stu-id="d6068-113">ABORT_XP_HEADER_OPERATION</span></span>
  
> <span data-ttu-id="d6068-114">用户取消了操作, 通常是在相应的对话框中单击 "**取消**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="d6068-114">The user canceled the operation, typically by clicking the **Cancel** button in the corresponding dialog box.</span></span> <span data-ttu-id="d6068-115">status 对象有两个选项:</span><span class="sxs-lookup"><span data-stu-id="d6068-115">The status object has two options:</span></span> 
    
   - <span data-ttu-id="d6068-116">继续处理该操作。</span><span class="sxs-lookup"><span data-stu-id="d6068-116">Continue working on the operation.</span></span>
    
   - <span data-ttu-id="d6068-117">停止操作并返回 MAPI_E_USER_CANCELED。</span><span class="sxs-lookup"><span data-stu-id="d6068-117">Stop the operation and return MAPI_E_USER_CANCELED.</span></span>
    
<span data-ttu-id="d6068-118">CONFIG_CHANGED</span><span class="sxs-lookup"><span data-stu-id="d6068-118">CONFIG_CHANGED</span></span> 
  
> <span data-ttu-id="d6068-119">一个或多个状态对象的配置属性已更改。</span><span class="sxs-lookup"><span data-stu-id="d6068-119">One or more of the status object's configuration properties changed.</span></span> <span data-ttu-id="d6068-120">客户端可以设置此标志, 以允许 MAPI 后台处理程序动态更正关键传输提供程序失败。</span><span class="sxs-lookup"><span data-stu-id="d6068-120">Clients can set this flag to allow the MAPI spooler to dynamically correct critical transport provider failures.</span></span> 
    
<span data-ttu-id="d6068-121">FORCE_XP_CONNECT</span><span class="sxs-lookup"><span data-stu-id="d6068-121">FORCE_XP_CONNECT</span></span> 
  
> <span data-ttu-id="d6068-122">status 对象应执行连接。</span><span class="sxs-lookup"><span data-stu-id="d6068-122">The status object should perform a connection.</span></span> <span data-ttu-id="d6068-123">将此标志与 REFRESH_XP_HEADER_CACHE 或 PROCESS_XP_HEADER_CACHE 标志一起使用时, 将发生不进行缓存的连接。</span><span class="sxs-lookup"><span data-stu-id="d6068-123">When this flag is used with the REFRESH_XP_HEADER_CACHE or PROCESS_XP_HEADER_CACHE flag, the connection occurs without caching.</span></span>
    
<span data-ttu-id="d6068-124">FORCE_XP_DISCONNECT</span><span class="sxs-lookup"><span data-stu-id="d6068-124">FORCE_XP_DISCONNECT</span></span> 
  
> <span data-ttu-id="d6068-125">status 对象应执行断开连接操作。</span><span class="sxs-lookup"><span data-stu-id="d6068-125">The status object should perform a disconnect operation.</span></span> <span data-ttu-id="d6068-126">将此标志与 REFRESH_XP_HEADER_CACHE 或 PROCESS_XP_HEADER_CACHE 标志一起使用时, 将不进行缓存而进行断开连接。</span><span class="sxs-lookup"><span data-stu-id="d6068-126">When this flag is used with the REFRESH_XP_HEADER_CACHE or PROCESS_XP_HEADER_CACHE flag, the disconnection occurs without caching.</span></span>
    
<span data-ttu-id="d6068-127">PROCESS_XP_HEADER_CACHE</span><span class="sxs-lookup"><span data-stu-id="d6068-127">PROCESS_XP_HEADER_CACHE</span></span> 
  
> <span data-ttu-id="d6068-128">应处理标头缓存表中的条目, 应下载所有标记为 MSGSTATUS_REMOTE_DOWNLOAD 标志的邮件, 并且应删除所有使用 MSGSTATUS_REMOTE_DELETE 标志标记的邮件。</span><span class="sxs-lookup"><span data-stu-id="d6068-128">Entries in the header cache table should be processed, all messages marked with the MSGSTATUS_REMOTE_DOWNLOAD flag should be downloaded, and all messages marked with the MSGSTATUS_REMOTE_DELETE flag should be deleted.</span></span> <span data-ttu-id="d6068-129">应移动同时包含 MSGSTATUS_REMOTE_DOWNLOAD 和 MSGSTATUS_REMOTE_DELETE 集的邮件。</span><span class="sxs-lookup"><span data-stu-id="d6068-129">Messages that have both MSGSTATUS_REMOTE_DOWNLOAD and MSGSTATUS_REMOTE_DELETE set should be moved.</span></span>
    
<span data-ttu-id="d6068-130">REFRESH_XP_HEADER_CACHE</span><span class="sxs-lookup"><span data-stu-id="d6068-130">REFRESH_XP_HEADER_CACHE</span></span> 
  
> <span data-ttu-id="d6068-131">对于远程传输提供程序, 应下载邮件头的新列表, 并且应清除标记邮件状态的所有标志。</span><span class="sxs-lookup"><span data-stu-id="d6068-131">For a remote transport provider, a new list of message headers should be downloaded and all flags that mark message status should be cleared.</span></span>
    
<span data-ttu-id="d6068-132">SUPPRESS_UI</span><span class="sxs-lookup"><span data-stu-id="d6068-132">SUPPRESS_UI</span></span> 
  
> <span data-ttu-id="d6068-133">阻止 status 对象在操作过程中显示用户界面。</span><span class="sxs-lookup"><span data-stu-id="d6068-133">Prevents the status object from displaying a user interface as part of the operation.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="d6068-134">返回值</span><span class="sxs-lookup"><span data-stu-id="d6068-134">Return value</span></span>

<span data-ttu-id="d6068-135">S_OK</span><span class="sxs-lookup"><span data-stu-id="d6068-135">S_OK</span></span> 
  
> <span data-ttu-id="d6068-136">验证成功。</span><span class="sxs-lookup"><span data-stu-id="d6068-136">The validation was successful.</span></span>
    
<span data-ttu-id="d6068-137">MAPI_E_BUSY</span><span class="sxs-lookup"><span data-stu-id="d6068-137">MAPI_E_BUSY</span></span> 
  
> <span data-ttu-id="d6068-138">正在进行另一个操作;在启动此操作之前, 应允许完成该操作, 或者应将其停止。</span><span class="sxs-lookup"><span data-stu-id="d6068-138">Another operation is in progress; it should be allowed to complete, or it should be stopped, before this operation is initiated.</span></span>
    
<span data-ttu-id="d6068-139">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="d6068-139">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="d6068-140">status 对象不支持验证方法, 如**PR_RESOURCE_METHODS** ([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md)) 属性中缺少 STATUS_VALIDATE_STATE 标志所指示的那样。</span><span class="sxs-lookup"><span data-stu-id="d6068-140">The status object does not support the validation method, as indicated by the absence of the STATUS_VALIDATE_STATE flag in the **PR_RESOURCE_METHODS** ([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md)) property.</span></span>
    
<span data-ttu-id="d6068-141">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="d6068-141">MAPI_E_USER_CANCEL</span></span> 
  
> <span data-ttu-id="d6068-142">用户取消了验证操作, 通常是单击对话框中的 "**取消**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="d6068-142">The user canceled the validation operation, typically by clicking the **Cancel** button in a dialog box.</span></span> <span data-ttu-id="d6068-143">此值仅由远程传输提供程序返回。</span><span class="sxs-lookup"><span data-stu-id="d6068-143">This value is returned only by remote transport providers.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="d6068-144">说明</span><span class="sxs-lookup"><span data-stu-id="d6068-144">Remarks</span></span>

<span data-ttu-id="d6068-145">**IMAPIStatus:: ValidateState**方法检查与 status 对象相关联的资源的状态。</span><span class="sxs-lookup"><span data-stu-id="d6068-145">The **IMAPIStatus::ValidateState** method checks the state of a resource that is associated with a status object.</span></span> <span data-ttu-id="d6068-146">**ValidateState**是所有 status 对象所需的[IMAPIStatus](imapistatusimapiprop.md)接口中的唯一方法。</span><span class="sxs-lookup"><span data-stu-id="d6068-146">**ValidateState** is the only method in the [IMAPIStatus](imapistatusimapiprop.md) interface that is required for all status objects.</span></span> <span data-ttu-id="d6068-147">此方法的确切行为取决于实现。</span><span class="sxs-lookup"><span data-stu-id="d6068-147">The exact behavior of this method depends on the implementation.</span></span> <span data-ttu-id="d6068-148">下表介绍了每种不同类型的状态对象的实现。</span><span class="sxs-lookup"><span data-stu-id="d6068-148">The following table describes the implementation of each of the different types of status objects.</span></span> 
  
|<span data-ttu-id="d6068-149">**Status 对象**</span><span class="sxs-lookup"><span data-stu-id="d6068-149">**Status object**</span></span>|<span data-ttu-id="d6068-150">ValidateState \* \* 实现 \* \*</span><span class="sxs-lookup"><span data-stu-id="d6068-150">\*\*\*\*ValidateState\*\* implementation\*\*</span></span>|
|:-----|:-----|
|<span data-ttu-id="d6068-151">MAPI 子系统</span><span class="sxs-lookup"><span data-stu-id="d6068-151">MAPI subsystem</span></span>  <br/> |<span data-ttu-id="d6068-152">验证当前处于活动状态的服务提供程序和子系统本身所拥有的所有资源的状态。</span><span class="sxs-lookup"><span data-stu-id="d6068-152">Validates the state of all the resources that the currently active service providers and the subsystem itself own.</span></span>  <br/> |
|<span data-ttu-id="d6068-153">MAPI 后台处理程序</span><span class="sxs-lookup"><span data-stu-id="d6068-153">MAPI spooler</span></span>  <br/> |<span data-ttu-id="d6068-154">对所有传输提供程序执行登录, 无论它们是否已登录。</span><span class="sxs-lookup"><span data-stu-id="d6068-154">Performs a logon of all transport providers, regardless of whether they are already logged on.</span></span>  <br/> |
|<span data-ttu-id="d6068-155">MAPI 通讯簿</span><span class="sxs-lookup"><span data-stu-id="d6068-155">MAPI address book</span></span>  <br/> |<span data-ttu-id="d6068-156">检查其 "配置文件" 部分中的条目。</span><span class="sxs-lookup"><span data-stu-id="d6068-156">Checks the entries in its profile section.</span></span>  <br/> |
|<span data-ttu-id="d6068-157">服务提供程序</span><span class="sxs-lookup"><span data-stu-id="d6068-157">Service provider</span></span>  <br/> |<span data-ttu-id="d6068-158">实现取决于提供程序的类型和_ulFlags_参数中设置的标志。</span><span class="sxs-lookup"><span data-stu-id="d6068-158">Implementation depends on the type of provider and the flags set in the  _ulFlags_ parameter.</span></span>  <br/> |
   
## <a name="notes-to-implementers"></a><span data-ttu-id="d6068-159">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="d6068-159">Notes to implementers</span></span>

<span data-ttu-id="d6068-160">远程客户端应用程序调用**ValidateState**方法来启动各种操作的远程处理。</span><span class="sxs-lookup"><span data-stu-id="d6068-160">Remote client applications call the **ValidateState** method to start remote processing for various actions.</span></span> <span data-ttu-id="d6068-161">此方法主要用于将状态位设置为与 MAPI 后台处理程序通信, 而不是实际执行任何工作。</span><span class="sxs-lookup"><span data-stu-id="d6068-161">This method exists primarily to set status bits to communicate with the MAPI spooler, instead of to actually do any work.</span></span> <span data-ttu-id="d6068-162">通常情况下, 传输提供程序会在其状态行中设置标记, 以指示 MAPI 后台处理程序需要启动哪些操作才能完成客户端的请求。</span><span class="sxs-lookup"><span data-stu-id="d6068-162">Typically, the transport provider sets flags in its status row that indicate to the MAPI spooler what actions need to be initiated to complete the client's request.</span></span> 

<span data-ttu-id="d6068-163">在此模型的客户端传输-后台处理程序交互中, 客户端请求的操作是异步的, 在请求的操作完成之前, **ValidateState**返回。</span><span class="sxs-lookup"><span data-stu-id="d6068-163">In this model of client-transport-spooler interaction, the actions requested by the client are asynchronous, in that **ValidateState** returns before the requested actions are complete.</span></span> <span data-ttu-id="d6068-164">但是, 不一定会涉及基础邮件系统, 或者涉及传输特定接口的操作可以是同步的。</span><span class="sxs-lookup"><span data-stu-id="d6068-164">However, actions that do not necessarily involve the underlying messaging system, or that involve a transport-specific interface, can be synchronous.</span></span> <span data-ttu-id="d6068-165">客户端应用程序通过以下标志的位掩码传递, 以指定远程传输提供程序应执行的操作。</span><span class="sxs-lookup"><span data-stu-id="d6068-165">The client application passes in a bitmask of the following flags to specify which actions the remote transport provider should take.</span></span> 
  
<span data-ttu-id="d6068-166">ABORT_XP_HEADER_OPERATION</span><span class="sxs-lookup"><span data-stu-id="d6068-166">ABORT_XP_HEADER_OPERATION</span></span> 
  
> <span data-ttu-id="d6068-167">如果可能, 远程传输提供程序应取消任何涉及下载邮件头的操作。</span><span class="sxs-lookup"><span data-stu-id="d6068-167">If possible, the remote transport provider should cancel any operations that involve downloading headers.</span></span> <span data-ttu-id="d6068-168">若要执行此操作, 传输提供程序必须在登录对象的状态行中设置以下属性值:</span><span class="sxs-lookup"><span data-stu-id="d6068-168">To do this, the transport provider must set the following property values in the logon object's status row:</span></span>
    
   - <span data-ttu-id="d6068-169">清除**PR_STATUS_CODE** ([PidTagStatusCode](pidtagstatuscode-canonical-property.md)) 属性中的 STATUS_INBOUND_ENABLED 和 STATUS_INBOUND_ACTIVE 位, 以告知 MAPI 后台处理程序暂停此传输提供程序的传入刷新过程。</span><span class="sxs-lookup"><span data-stu-id="d6068-169">Clear the STATUS_INBOUND_ENABLED and STATUS_INBOUND_ACTIVE bits in the **PR_STATUS_CODE** ([PidTagStatusCode](pidtagstatuscode-canonical-property.md)) property to tell the MAPI spooler to halt the incoming flush process for this transport provider.</span></span>
    
   - <span data-ttu-id="d6068-170">在**PR_STATUS_CODE**属性中设置 STATUS_OFFLINE 位。</span><span class="sxs-lookup"><span data-stu-id="d6068-170">Set the STATUS_OFFLINE bit in the **PR_STATUS_CODE** property.</span></span> 
    
   - <span data-ttu-id="d6068-171">将**PR_REMOTE_VALIDATE_OK** ([PidTagRemoteValidateOk](pidtagremotevalidateok-canonical-property.md)) 属性设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="d6068-171">Set the **PR_REMOTE_VALIDATE_OK** ([PidTagRemoteValidateOk](pidtagremotevalidateok-canonical-property.md)) property to TRUE.</span></span>
    
   - <span data-ttu-id="d6068-172">将**PR_STATUS_STRING** ([PidTagStatusString](pidtagstatusstring-canonical-property.md)) 属性设置为一个字符串, 该字符串指示向用户传输提供程序的状态。</span><span class="sxs-lookup"><span data-stu-id="d6068-172">Set the **PR_STATUS_STRING** ([PidTagStatusString](pidtagstatusstring-canonical-property.md)) property to a string that indicates the transport provider's status to the user.</span></span>
    
   - <span data-ttu-id="d6068-173">返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="d6068-173">Return S_OK.</span></span> <span data-ttu-id="d6068-174">但是, 如果无法取消正在进行的操作, **ValidateState**应返回 MAPI_E_BUSY。</span><span class="sxs-lookup"><span data-stu-id="d6068-174">However, if the operation in progress cannot be canceled, **ValidateState** should return MAPI_E_BUSY.</span></span> 
    
<span data-ttu-id="d6068-175">FORCE_XP_CONNECT</span><span class="sxs-lookup"><span data-stu-id="d6068-175">FORCE_XP_CONNECT</span></span> 
  
> <span data-ttu-id="d6068-176">远程传输提供程序永远不应建立与[IXPLogon:: FlushQueues](ixplogon-flushqueues.md)方法中涉及的 MAPI 后台处理程序的上下文外的共享资源 (例如, 调制解调器或 COM 端口) 的连接。</span><span class="sxs-lookup"><span data-stu-id="d6068-176">A remote transport provider should never establish a connection to a shared resource (for example, a modem or COM port) outside the context of the MAPI spooler-transport interaction involved in the [IXPLogon::FlushQueues](ixplogon-flushqueues.md) method.</span></span> <span data-ttu-id="d6068-177">如果使用此标志调用**ValidateState** , 则您的传输提供程序应执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="d6068-177">If **ValidateState** is called with this flag, your transport provider should do the following:</span></span> 
    
   - <span data-ttu-id="d6068-178">设置内部状态标志, 以指示在调用**IXPLogon:: FlushQueues**方法时必须建立远程连接。</span><span class="sxs-lookup"><span data-stu-id="d6068-178">Set an internal status flag to indicate that the remote connection must be established when the **IXPLogon::FlushQueues** method is called.</span></span> 
    
   - <span data-ttu-id="d6068-179">在状态表中设置正确的值, 以使 MAPI 后台处理程序启动队列刷新过程。</span><span class="sxs-lookup"><span data-stu-id="d6068-179">Set the correct values in the status table to cause the MAPI spooler to initiate the queue flushing process.</span></span>
    
   - <span data-ttu-id="d6068-180">完成队列的刷新后, 释放共享资源。</span><span class="sxs-lookup"><span data-stu-id="d6068-180">When flushing of queues is complete, release the shared resource.</span></span>
    
   - <span data-ttu-id="d6068-181">清除**PR_STATUS_CODE**属性中的 STATUS_OFFLINE 位。</span><span class="sxs-lookup"><span data-stu-id="d6068-181">Clear the STATUS_OFFLINE bit in the **PR_STATUS_CODE** property.</span></span> 
    
   - <span data-ttu-id="d6068-182">返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="d6068-182">Return S_OK.</span></span>
    
<span data-ttu-id="d6068-183">FORCE_XP_DISCONNECT</span><span class="sxs-lookup"><span data-stu-id="d6068-183">FORCE_XP_DISCONNECT</span></span> 
  
> <span data-ttu-id="d6068-184">远程传输提供程序应释放与邮件系统资源的连接。</span><span class="sxs-lookup"><span data-stu-id="d6068-184">The remote transport provider should release its connection to the messaging system resources.</span></span> <span data-ttu-id="d6068-185">执行此操作后, 它应在**PR_STATUS_CODE**属性中设置 STATUS_OFFLINE 位, 并返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="d6068-185">After doing this, it should set the STATUS_OFFLINE bit in the **PR_STATUS_CODE** property and return S_OK.</span></span> 
    
<span data-ttu-id="d6068-186">PROCESS_XP_HEADER_CACHE</span><span class="sxs-lookup"><span data-stu-id="d6068-186">PROCESS_XP_HEADER_CACHE</span></span> 
  
> <span data-ttu-id="d6068-187">远程传输提供程序应处理远程消息, 并上载任何已延迟的邮件。</span><span class="sxs-lookup"><span data-stu-id="d6068-187">The remote transport provider should process remote messages and upload any messages that have been deferred.</span></span> <span data-ttu-id="d6068-188">若要执行此操作, 传输提供程序必须在登录对象的状态行中设置以下属性值:</span><span class="sxs-lookup"><span data-stu-id="d6068-188">To do this, the transport provider must set the following property values in the logon object's status row:</span></span>
    
   - <span data-ttu-id="d6068-189">将**PR_STATUS_STRING**属性设置为一个字符串, 该字符串指示向用户传输提供程序的状态。</span><span class="sxs-lookup"><span data-stu-id="d6068-189">Set the **PR_STATUS_STRING** property to a string that indicates the transport provider's status to the user.</span></span> 
    
   - <span data-ttu-id="d6068-190">在**PR_STATUS_CODE**属性中设置 STATUS_OUTBOUND_ENABLED 和 STATUS_OUTBOUND_ACTIVE 位。</span><span class="sxs-lookup"><span data-stu-id="d6068-190">Set the STATUS_OUTBOUND_ENABLED and STATUS_OUTBOUND_ACTIVE bits in the **PR_STATUS_CODE** property.</span></span> 
    
   - <span data-ttu-id="d6068-191">将传输提供程序的状态行中的**PR_REMOTE_VALIDATE_OK**属性设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="d6068-191">Set the **PR_REMOTE_VALIDATE_OK** property in the transport provider's status row to FALSE.</span></span> 
    
   - <span data-ttu-id="d6068-192">如果调用**ValidateState**时正在进行另一个操作 (如下载标头), 则**ValidateState**应返回 MAPI_E_BUSY。</span><span class="sxs-lookup"><span data-stu-id="d6068-192">If another operation is in progress (such as downloading headers) when **ValidateState** is called, **ValidateState** should return MAPI_E_BUSY.</span></span> 
    
   - <span data-ttu-id="d6068-193">同时执行用于处理 REFRESH_XP_HEADER_CACHE 标志的代码, 以满足 Microsoft Exchange 客户端的要求。</span><span class="sxs-lookup"><span data-stu-id="d6068-193">Execute the code for processing the REFRESH_XP_HEADER_CACHE flag, as well, to satisfy requirements of the Microsoft Exchange client.</span></span>
    
<span data-ttu-id="d6068-194">REFRESH_XP_HEADER_CACHE</span><span class="sxs-lookup"><span data-stu-id="d6068-194">REFRESH_XP_HEADER_CACHE</span></span> 
  
> <span data-ttu-id="d6068-195">远程传输提供程序应从邮件系统中检索任何新的邮件头。</span><span class="sxs-lookup"><span data-stu-id="d6068-195">The remote transport provider should retrieve any new message headers from the messaging system.</span></span> <span data-ttu-id="d6068-196">若要执行此操作, 传输提供程序必须执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="d6068-196">To do this, the transport provider must do the following:</span></span>
    
   - <span data-ttu-id="d6068-197">将**PR_STATUS_STRING**属性设置为一个字符串, 该字符串指示向用户传输提供程序的状态。</span><span class="sxs-lookup"><span data-stu-id="d6068-197">Set the **PR_STATUS_STRING** property to a string that indicates the transport provider's status to the user.</span></span> 
    
   - <span data-ttu-id="d6068-198">在**PR_STATUS_CODE**属性中设置 STATUS_INBOUND_ENABLED 和 STATUS_INBOUND_ACTIVE 位。</span><span class="sxs-lookup"><span data-stu-id="d6068-198">Set the STATUS_INBOUND_ENABLED and STATUS_INBOUND_ACTIVE bits in the **PR_STATUS_CODE** property.</span></span> 
    
   - <span data-ttu-id="d6068-199">清除**PR_STATUS_CODE**属性中的 STATUS_OFFLINE 位。</span><span class="sxs-lookup"><span data-stu-id="d6068-199">Clear the STATUS_OFFLINE bit in the **PR_STATUS_CODE** property.</span></span> 
    
   - <span data-ttu-id="d6068-200">在**PR_STATUS_CODE**属性中设置 STATUS_ONLINE 位。</span><span class="sxs-lookup"><span data-stu-id="d6068-200">Set the STATUS_ONLINE bit in the **PR_STATUS_CODE** property.</span></span> 
    
   - <span data-ttu-id="d6068-201">将传输提供程序的状态行中的**PR_REMOTE_VALIDATE_OK**属性设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="d6068-201">Set the **PR_REMOTE_VALIDATE_OK** property in the transport provider's status row to FALSE.</span></span> 
    
<span data-ttu-id="d6068-202">SHOW_XP_SESSION_UI</span><span class="sxs-lookup"><span data-stu-id="d6068-202">SHOW_XP_SESSION_UI</span></span> 
  
> <span data-ttu-id="d6068-203">如果您的传输提供程序有任何部分用户界面用于处理邮件头 (如确认邮件下载的对话框), 则应显示该对话框。</span><span class="sxs-lookup"><span data-stu-id="d6068-203">If your transport provider has any pieces of user interface for processing the message headers (such as a dialog box that confirms the downloading of messages), that dialog box should be displayed.</span></span> <span data-ttu-id="d6068-204">否则, **ValidateState**可以返回 MAPI_E_NO_SUPPORT。</span><span class="sxs-lookup"><span data-stu-id="d6068-204">Otherwise, **ValidateState** can return MAPI_E_NO_SUPPORT.</span></span> 
    
<span data-ttu-id="d6068-205">如果传入的任何标志除外, **ValidateState**应返回 MAPI_E_UNKNOWN_FLAGS。</span><span class="sxs-lookup"><span data-stu-id="d6068-205">If any flags other than these are passed in, **ValidateState** should return MAPI_E_UNKNOWN_FLAGS.</span></span> 
  
<span data-ttu-id="d6068-206">客户端对传输提供程序的调用通常会是**IMAPIStatus:: ValidateState**方法。</span><span class="sxs-lookup"><span data-stu-id="d6068-206">The client's call to the transport provider will often be to the **IMAPIStatus::ValidateState** method.</span></span> <span data-ttu-id="d6068-207">在处理**ValidateState**的过程中, 传输提供程序不应执行任何分配稀有系统资源 (如调制解调器或 COM 端口) 的操作。</span><span class="sxs-lookup"><span data-stu-id="d6068-207">During the processing of **ValidateState**, the transport provider should not perform any actions that allocate scarce system resources, such as a modem or COM port.</span></span> <span data-ttu-id="d6068-208">这是因为 MAPI 后台处理程序有时需要刷新多个传输提供程序上的队列。</span><span class="sxs-lookup"><span data-stu-id="d6068-208">This is because the MAPI spooler will sometimes need to flush queues on more than one transport provider.</span></span> <span data-ttu-id="d6068-209">但是, 客户端可以随时调用任何传输提供程序的**ValidateState**方法。</span><span class="sxs-lookup"><span data-stu-id="d6068-209">However, the client can call any transport provider's **ValidateState** method at any time.</span></span> <span data-ttu-id="d6068-210">如果您的传输提供程序在处理**ValidateState**的过程中尝试分配稀有资源, 则可能会因为与 MAPI 后台处理程序指示刷新其队列的另一个传输提供程序发生冲突而导致出错。</span><span class="sxs-lookup"><span data-stu-id="d6068-210">If your transport provider attempts to allocate a scarce resource during the processing of **ValidateState**, an error can result due to conflict with another transport provider that the MAPI spooler has instructed to flush its queues.</span></span> <span data-ttu-id="d6068-211">如果您允许 MAPI 后台处理程序的方向发生所有稀有资源分配, 则可以避免此类冲突。</span><span class="sxs-lookup"><span data-stu-id="d6068-211">If you allow all scarce resource allocations to occur under the direction of the MAPI spooler, you can avoid such conflicts.</span></span> <span data-ttu-id="d6068-212">您的传输提供程序应支持**PR_REMOTE_VALIDATE_OK**属性, 以便客户端应用程序可以检测到您的传输提供程序何时繁忙或等待 MAPI 后台处理程序启动操作。</span><span class="sxs-lookup"><span data-stu-id="d6068-212">Your transport provider should support the **PR_REMOTE_VALIDATE_OK** property so client applications can detect when your transport provider is busy or waiting for the MAPI spooler to initiate an action.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="d6068-213">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="d6068-213">Notes to callers</span></span>

<span data-ttu-id="d6068-214">由于此方法可能会导致进行其他可能的较长的调用, **ValidateState**可以返回 MAPI_E_BUSY, 以通知您此方法正在等待其他操作的完成。</span><span class="sxs-lookup"><span data-stu-id="d6068-214">Because this method can cause other potentially lengthy calls to be made, **ValidateState** can return MAPI_E_BUSY to inform you that this method is waiting for the completion of another operation.</span></span> <span data-ttu-id="d6068-215">应等到挂起的操作完成后, 再尝试执行其他任务。</span><span class="sxs-lookup"><span data-stu-id="d6068-215">You should wait until the pending operation is complete before attempting another task.</span></span> 
  
<span data-ttu-id="d6068-216">您可以最大限度地控制对传输提供程序状态对象的调用。</span><span class="sxs-lookup"><span data-stu-id="d6068-216">You have the most control over your calls to transport provider status objects.</span></span> <span data-ttu-id="d6068-217">可以将一个或多个标志传递给**ValidateState** , 这些标志将影响传输提供程序的操作。</span><span class="sxs-lookup"><span data-stu-id="d6068-217">You can pass one or more flags to **ValidateState** that affect the transport provider's operations.</span></span> <span data-ttu-id="d6068-218">例如, ABORT_XP_HEADER_OPERATION 标志指示用户取消了验证。</span><span class="sxs-lookup"><span data-stu-id="d6068-218">For example, the ABORT_XP_HEADER_OPERATION flag indicates that the user canceled the validation.</span></span> <span data-ttu-id="d6068-219">传输提供程序可以决定中止、返回 MAPI_E_USER_CANCELED, 也可以继续。</span><span class="sxs-lookup"><span data-stu-id="d6068-219">Transport providers can decide to abort, returning MAPI_E_USER_CANCELED, or can continue.</span></span> 
  
<span data-ttu-id="d6068-220">您可以在对服务提供程序或 MAPI 后台处理程序的 status 对象的调用上设置 CONFIG_CHANGED 标志, 以指示配置选项已更改。</span><span class="sxs-lookup"><span data-stu-id="d6068-220">You can set the CONFIG_CHANGED flag on a call to either the status object of a service provider or the MAPI spooler to indicate that a configuration option has been changed.</span></span> <span data-ttu-id="d6068-221">您可以使用 CONFIG_CHANGED 动态重新配置传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="d6068-221">You can use CONFIG_CHANGED to dynamically reconfigure a transport provider.</span></span> <span data-ttu-id="d6068-222">当您在对服务提供程序的 status 对象的调用上设置 CONFIG_CHANGED 时, 提供程序将通过调用[IMAPISupport:: SpoolerNotify](imapisupport-spoolernotify.md)来通知 MAPI 后台处理程序的更改。</span><span class="sxs-lookup"><span data-stu-id="d6068-222">When you set CONFIG_CHANGED on a call to a service provider's status object, the provider responds with a call to [IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md) to alert the MAPI spooler of the change.</span></span> <span data-ttu-id="d6068-223">当您在对 MAPI 后台处理程序状态对象的调用上设置 CONFIG_CHANGED 时, 后台打印程序将为每个活动的传输提供程序调用[IXPLogon:: AddressTypes](ixplogon-addresstypes.md) 。</span><span class="sxs-lookup"><span data-stu-id="d6068-223">When you set CONFIG_CHANGED on a call to the MAPI spooler's status object, the spooler calls [IXPLogon::AddressTypes](ixplogon-addresstypes.md) for each active transport provider.</span></span> <span data-ttu-id="d6068-224">**AddressTypes**通知 MAPI 后台处理程序的传输受支持的地址类型。</span><span class="sxs-lookup"><span data-stu-id="d6068-224">**AddressTypes** informs the MAPI spooler of a transport's supported address types.</span></span> <span data-ttu-id="d6068-225">如果验证预计需要很长时间, 一些服务提供商也会显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="d6068-225">Some service providers also display a progress indicator if the validation is expected to take a long time.</span></span> <span data-ttu-id="d6068-226">显示进度指示器很有用, 但不是必需的。</span><span class="sxs-lookup"><span data-stu-id="d6068-226">Displaying a progress indicator is helpful, but not required.</span></span> 
  
<span data-ttu-id="d6068-227">如果设置了 SUPPRESS_UI 标志, 则无法显示任何配置属性表或进度对话框。</span><span class="sxs-lookup"><span data-stu-id="d6068-227">When the SUPPRESS_UI flag is set, none of the configuration property sheets or progress dialog boxes can be displayed.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d6068-228">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d6068-228">See also</span></span>

- [<span data-ttu-id="d6068-229">IMAPISupport::SpoolerNotify</span><span class="sxs-lookup"><span data-stu-id="d6068-229">IMAPISupport::SpoolerNotify</span></span>](imapisupport-spoolernotify.md)
- [<span data-ttu-id="d6068-230">IXPLogon::AddressTypes</span><span class="sxs-lookup"><span data-stu-id="d6068-230">IXPLogon::AddressTypes</span></span>](ixplogon-addresstypes.md)
- [<span data-ttu-id="d6068-231">IXPLogon::FlushQueues</span><span class="sxs-lookup"><span data-stu-id="d6068-231">IXPLogon::FlushQueues</span></span>](ixplogon-flushqueues.md)
- [<span data-ttu-id="d6068-232">PidTagRemoteValidateOk 规范属性</span><span class="sxs-lookup"><span data-stu-id="d6068-232">PidTagRemoteValidateOk Canonical Property</span></span>](pidtagremotevalidateok-canonical-property.md)
- [<span data-ttu-id="d6068-233">PidTagResourceMethods 规范属性</span><span class="sxs-lookup"><span data-stu-id="d6068-233">PidTagResourceMethods Canonical Property</span></span>](pidtagresourcemethods-canonical-property.md)
- [<span data-ttu-id="d6068-234">PidTagStatusCode 规范属性</span><span class="sxs-lookup"><span data-stu-id="d6068-234">PidTagStatusCode Canonical Property</span></span>](pidtagstatuscode-canonical-property.md)
- [<span data-ttu-id="d6068-235">PidTagStatusString 规范属性</span><span class="sxs-lookup"><span data-stu-id="d6068-235">PidTagStatusString Canonical Property</span></span>](pidtagstatusstring-canonical-property.md)
- [<span data-ttu-id="d6068-236">IMAPIStatus : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="d6068-236">IMAPIStatus : IMAPIProp</span></span>](imapistatusimapiprop.md)

