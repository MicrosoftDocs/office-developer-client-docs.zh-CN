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
ms.openlocfilehash: 3ff29ac7e7f9b7876bb678930390ca556351ecf6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775610"
---
# <a name="imapistatusvalidatestate"></a><span data-ttu-id="af1a8-103">IMAPIStatus::ValidateState</span><span class="sxs-lookup"><span data-stu-id="af1a8-103">IMAPIStatus::ValidateState</span></span>

<span data-ttu-id="af1a8-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="af1a8-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="af1a8-105">确认可供 MAPI 资源或服务提供商的外部状态信息。</span><span class="sxs-lookup"><span data-stu-id="af1a8-105">Confirms the external status information available for the MAPI resource or the service provider.</span></span> <span data-ttu-id="af1a8-106">此方法支持所有状态对象。</span><span class="sxs-lookup"><span data-stu-id="af1a8-106">This method is supported in all status objects.</span></span> 
  
```cpp
HRESULT ValidateState(
  ULONG_PTR ulUIParam,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="af1a8-107">参数</span><span class="sxs-lookup"><span data-stu-id="af1a8-107">Parameters</span></span>

<span data-ttu-id="af1a8-108">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="af1a8-108">_ulUIParam_</span></span>
  
> <span data-ttu-id="af1a8-109">[in]任何对话框的父窗口或该方法显示的窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="af1a8-109">[in] A handle to the parent window of any dialog boxes or windows that this method displays.</span></span>
    
<span data-ttu-id="af1a8-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="af1a8-110">_ulFlags_</span></span>
  
> <span data-ttu-id="af1a8-111">[in]位掩码的标志来控制验证。</span><span class="sxs-lookup"><span data-stu-id="af1a8-111">[in] A bitmask of flags that controls the validation.</span></span> <span data-ttu-id="af1a8-112">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="af1a8-112">The following flags can be set:</span></span>
    
<span data-ttu-id="af1a8-113">ABORT_XP_HEADER_OPERATION</span><span class="sxs-lookup"><span data-stu-id="af1a8-113">ABORT_XP_HEADER_OPERATION</span></span>
  
> <span data-ttu-id="af1a8-114">用户取消操作，通常通过单击相应的对话框中的**取消**按钮。</span><span class="sxs-lookup"><span data-stu-id="af1a8-114">The user canceled the operation, typically by clicking the **Cancel** button in the corresponding dialog box.</span></span> <span data-ttu-id="af1a8-115">状态对象有两个选项：</span><span class="sxs-lookup"><span data-stu-id="af1a8-115">The status object has two options:</span></span> 
    
   - <span data-ttu-id="af1a8-116">继续操作。</span><span class="sxs-lookup"><span data-stu-id="af1a8-116">Continue working on the operation.</span></span>
    
   - <span data-ttu-id="af1a8-117">停止操作并返回 MAPI_E_USER_CANCELED。</span><span class="sxs-lookup"><span data-stu-id="af1a8-117">Stop the operation and return MAPI_E_USER_CANCELED.</span></span>
    
<span data-ttu-id="af1a8-118">CONFIG_CHANGED</span><span class="sxs-lookup"><span data-stu-id="af1a8-118">CONFIG_CHANGED</span></span> 
  
> <span data-ttu-id="af1a8-119">更改一个或多个状态对象的配置属性。</span><span class="sxs-lookup"><span data-stu-id="af1a8-119">One or more of the status object's configuration properties changed.</span></span> <span data-ttu-id="af1a8-120">客户端可以设置此标志以允许 MAPI 后台处理程序动态更正关键传输提供程序失败。</span><span class="sxs-lookup"><span data-stu-id="af1a8-120">Clients can set this flag to allow the MAPI spooler to dynamically correct critical transport provider failures.</span></span> 
    
<span data-ttu-id="af1a8-121">FORCE_XP_CONNECT</span><span class="sxs-lookup"><span data-stu-id="af1a8-121">FORCE_XP_CONNECT</span></span> 
  
> <span data-ttu-id="af1a8-122">状态对象应执行连接。</span><span class="sxs-lookup"><span data-stu-id="af1a8-122">The status object should perform a connection.</span></span> <span data-ttu-id="af1a8-123">此标志用于 REFRESH_XP_HEADER_CACHE 或 PROCESS_XP_HEADER_CACHE 标志，连接时不进行缓存。</span><span class="sxs-lookup"><span data-stu-id="af1a8-123">When this flag is used with the REFRESH_XP_HEADER_CACHE or PROCESS_XP_HEADER_CACHE flag, the connection occurs without caching.</span></span>
    
<span data-ttu-id="af1a8-124">FORCE_XP_DISCONNECT</span><span class="sxs-lookup"><span data-stu-id="af1a8-124">FORCE_XP_DISCONNECT</span></span> 
  
> <span data-ttu-id="af1a8-125">状态对象应执行断开连接操作。</span><span class="sxs-lookup"><span data-stu-id="af1a8-125">The status object should perform a disconnect operation.</span></span> <span data-ttu-id="af1a8-126">此标志用于 REFRESH_XP_HEADER_CACHE 或 PROCESS_XP_HEADER_CACHE 标志，断开连接时不进行缓存。</span><span class="sxs-lookup"><span data-stu-id="af1a8-126">When this flag is used with the REFRESH_XP_HEADER_CACHE or PROCESS_XP_HEADER_CACHE flag, the disconnection occurs without caching.</span></span>
    
<span data-ttu-id="af1a8-127">PROCESS_XP_HEADER_CACHE</span><span class="sxs-lookup"><span data-stu-id="af1a8-127">PROCESS_XP_HEADER_CACHE</span></span> 
  
> <span data-ttu-id="af1a8-128">应处理标题缓存表中的条目，应下载标记有 MSGSTATUS_REMOTE_DOWNLOAD 标志的所有邮件，以及应删除与 MSGSTATUS_REMOTE_DELETE 标志标记的所有邮件。</span><span class="sxs-lookup"><span data-stu-id="af1a8-128">Entries in the header cache table should be processed, all messages marked with the MSGSTATUS_REMOTE_DOWNLOAD flag should be downloaded, and all messages marked with the MSGSTATUS_REMOTE_DELETE flag should be deleted.</span></span> <span data-ttu-id="af1a8-129">应移动 MSGSTATUS_REMOTE_DOWNLOAD 和 MSGSTATUS_REMOTE_DELETE 设置的消息。</span><span class="sxs-lookup"><span data-stu-id="af1a8-129">Messages that have both MSGSTATUS_REMOTE_DOWNLOAD and MSGSTATUS_REMOTE_DELETE set should be moved.</span></span>
    
<span data-ttu-id="af1a8-130">REFRESH_XP_HEADER_CACHE</span><span class="sxs-lookup"><span data-stu-id="af1a8-130">REFRESH_XP_HEADER_CACHE</span></span> 
  
> <span data-ttu-id="af1a8-131">为远程传输提供程序应下载邮件头的新列表，并应清除标记邮件状态的所有标志。</span><span class="sxs-lookup"><span data-stu-id="af1a8-131">For a remote transport provider, a new list of message headers should be downloaded and all flags that mark message status should be cleared.</span></span>
    
<span data-ttu-id="af1a8-132">SUPPRESS_UI</span><span class="sxs-lookup"><span data-stu-id="af1a8-132">SUPPRESS_UI</span></span> 
  
> <span data-ttu-id="af1a8-133">阻止操作的一部分显示用户界面的状态对象。</span><span class="sxs-lookup"><span data-stu-id="af1a8-133">Prevents the status object from displaying a user interface as part of the operation.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="af1a8-134">返回值</span><span class="sxs-lookup"><span data-stu-id="af1a8-134">Return value</span></span>

<span data-ttu-id="af1a8-135">S_OK</span><span class="sxs-lookup"><span data-stu-id="af1a8-135">S_OK</span></span> 
  
> <span data-ttu-id="af1a8-136">验证成功。</span><span class="sxs-lookup"><span data-stu-id="af1a8-136">The validation was successful.</span></span>
    
<span data-ttu-id="af1a8-137">MAPI_E_BUSY</span><span class="sxs-lookup"><span data-stu-id="af1a8-137">MAPI_E_BUSY</span></span> 
  
> <span data-ttu-id="af1a8-138">正在进行; 另一个操作应允许其完成，或者它应停止，开始此操作之前。</span><span class="sxs-lookup"><span data-stu-id="af1a8-138">Another operation is in progress; it should be allowed to complete, or it should be stopped, before this operation is initiated.</span></span>
    
<span data-ttu-id="af1a8-139">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="af1a8-139">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="af1a8-140">状态对象不支持的验证方法，由 STATUS_VALIDATE_STATE 标志**PR_RESOURCE_METHODS** ([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md)) 属性中不存在。</span><span class="sxs-lookup"><span data-stu-id="af1a8-140">The status object does not support the validation method, as indicated by the absence of the STATUS_VALIDATE_STATE flag in the **PR_RESOURCE_METHODS** ([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md)) property.</span></span>
    
<span data-ttu-id="af1a8-141">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="af1a8-141">MAPI_E_USER_CANCEL</span></span> 
  
> <span data-ttu-id="af1a8-142">用户取消验证操作，通常通过单击对话框中的**取消**按钮。</span><span class="sxs-lookup"><span data-stu-id="af1a8-142">The user canceled the validation operation, typically by clicking the **Cancel** button in a dialog box.</span></span> <span data-ttu-id="af1a8-143">只能通过远程传输提供程序，则返回此值。</span><span class="sxs-lookup"><span data-stu-id="af1a8-143">This value is returned only by remote transport providers.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="af1a8-144">说明</span><span class="sxs-lookup"><span data-stu-id="af1a8-144">Remarks</span></span>

<span data-ttu-id="af1a8-145">**IMAPIStatus::ValidateState**方法检查与状态对象相关联的资源的状态。</span><span class="sxs-lookup"><span data-stu-id="af1a8-145">The **IMAPIStatus::ValidateState** method checks the state of a resource that is associated with a status object.</span></span> <span data-ttu-id="af1a8-146">**ValidateState**是[IMAPIStatus](imapistatusimapiprop.md)界面所需的所有状态对象中的唯一方法。</span><span class="sxs-lookup"><span data-stu-id="af1a8-146">**ValidateState** is the only method in the [IMAPIStatus](imapistatusimapiprop.md) interface that is required for all status objects.</span></span> <span data-ttu-id="af1a8-147">完全本方法的行为取决于实现。</span><span class="sxs-lookup"><span data-stu-id="af1a8-147">The exact behavior of this method depends on the implementation.</span></span> <span data-ttu-id="af1a8-148">下表介绍了每种状态对象的不同类型的实现。</span><span class="sxs-lookup"><span data-stu-id="af1a8-148">The following table describes the implementation of each of the different types of status objects.</span></span> 
  
|<span data-ttu-id="af1a8-149">**状态对象**</span><span class="sxs-lookup"><span data-stu-id="af1a8-149">**Status object**</span></span>|<span data-ttu-id="af1a8-150">ValidateState * * 实现 * *</span><span class="sxs-lookup"><span data-stu-id="af1a8-150">****ValidateState** implementation**</span></span>|
|:-----|:-----|
|<span data-ttu-id="af1a8-151">MAPI 子系统</span><span class="sxs-lookup"><span data-stu-id="af1a8-151">MAPI subsystem</span></span>  <br/> |<span data-ttu-id="af1a8-152">验证的当前处于活动状态的服务提供商和子系统本身拥有的所有资源的状态。</span><span class="sxs-lookup"><span data-stu-id="af1a8-152">Validates the state of all the resources that the currently active service providers and the subsystem itself own.</span></span>  <br/> |
|<span data-ttu-id="af1a8-153">MAPI 后台处理程序</span><span class="sxs-lookup"><span data-stu-id="af1a8-153">MAPI spooler</span></span>  <br/> |<span data-ttu-id="af1a8-154">执行所有传输提供程序，无论他们是否已记录在上一个登录的名。</span><span class="sxs-lookup"><span data-stu-id="af1a8-154">Performs a logon of all transport providers, regardless of whether they are already logged on.</span></span>  <br/> |
|<span data-ttu-id="af1a8-155">MAPI 通讯簿</span><span class="sxs-lookup"><span data-stu-id="af1a8-155">MAPI address book</span></span>  <br/> |<span data-ttu-id="af1a8-156">检查其配置文件节中的项。</span><span class="sxs-lookup"><span data-stu-id="af1a8-156">Checks the entries in its profile section.</span></span>  <br/> |
|<span data-ttu-id="af1a8-157">服务提供商</span><span class="sxs-lookup"><span data-stu-id="af1a8-157">Service provider</span></span>  <br/> |<span data-ttu-id="af1a8-158">实现取决于类型提供程序和设置_ulFlags_参数中的标志。</span><span class="sxs-lookup"><span data-stu-id="af1a8-158">Implementation depends on the type of provider and the flags set in the  _ulFlags_ parameter.</span></span>  <br/> |
   
## <a name="notes-to-implementers"></a><span data-ttu-id="af1a8-159">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="af1a8-159">Notes to implementers</span></span>

<span data-ttu-id="af1a8-160">远程客户端应用程序调用**ValidateState**方法以启动远程处理的各种操作。</span><span class="sxs-lookup"><span data-stu-id="af1a8-160">Remote client applications call the **ValidateState** method to start remote processing for various actions.</span></span> <span data-ttu-id="af1a8-161">此方法存在主要是为了设置状态位要与之通信 MAPI 后台处理程序，而不是实际执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="af1a8-161">This method exists primarily to set status bits to communicate with the MAPI spooler, instead of to actually do any work.</span></span> <span data-ttu-id="af1a8-162">通常，传输提供程序设置其 MAPI 后台处理程序向指示需要启动以完成客户端的请求的操作的状态行中的标志。</span><span class="sxs-lookup"><span data-stu-id="af1a8-162">Typically, the transport provider sets flags in its status row that indicate to the MAPI spooler what actions need to be initiated to complete the client's request.</span></span> 

<span data-ttu-id="af1a8-163">该模型中的后台处理传输客户端程序交互，客户端请求的操作是异步的，之前在完成请求的操作,，将返回**ValidateState** 。</span><span class="sxs-lookup"><span data-stu-id="af1a8-163">In this model of client-transport-spooler interaction, the actions requested by the client are asynchronous, in that **ValidateState** returns before the requested actions are complete.</span></span> <span data-ttu-id="af1a8-164">但是，操作时，并不一定涉及基础的消息系统，或者所涉及的特定于传输的界面，可以是同步。</span><span class="sxs-lookup"><span data-stu-id="af1a8-164">However, actions that do not necessarily involve the underlying messaging system, or that involve a transport-specific interface, can be synchronous.</span></span> <span data-ttu-id="af1a8-165">客户端应用程序中的指定远程传输提供程序应采取的操作的以下标志位掩码传递。</span><span class="sxs-lookup"><span data-stu-id="af1a8-165">The client application passes in a bitmask of the following flags to specify which actions the remote transport provider should take.</span></span> 
  
<span data-ttu-id="af1a8-166">ABORT_XP_HEADER_OPERATION</span><span class="sxs-lookup"><span data-stu-id="af1a8-166">ABORT_XP_HEADER_OPERATION</span></span> 
  
> <span data-ttu-id="af1a8-167">如果可能，远程传输提供程序应取消的涉及下载邮件头的任何操作。</span><span class="sxs-lookup"><span data-stu-id="af1a8-167">If possible, the remote transport provider should cancel any operations that involve downloading headers.</span></span> <span data-ttu-id="af1a8-168">若要执行此操作，传输提供程序必须登录对象的状态行中设置以下属性值：</span><span class="sxs-lookup"><span data-stu-id="af1a8-168">To do this, the transport provider must set the following property values in the logon object's status row:</span></span>
    
   - <span data-ttu-id="af1a8-169">清除**PR_STATUS_CODE** ([PidTagStatusCode](pidtagstatuscode-canonical-property.md)) 属性以告知 MAPI 后台处理程序停止此传输提供程序的传入刷新进程中的 STATUS_INBOUND_ENABLED 和 STATUS_INBOUND_ACTIVE 位。</span><span class="sxs-lookup"><span data-stu-id="af1a8-169">Clear the STATUS_INBOUND_ENABLED and STATUS_INBOUND_ACTIVE bits in the **PR_STATUS_CODE** ([PidTagStatusCode](pidtagstatuscode-canonical-property.md)) property to tell the MAPI spooler to halt the incoming flush process for this transport provider.</span></span>
    
   - <span data-ttu-id="af1a8-170">设置 STATUS_OFFLINE 位**PR_STATUS_CODE**属性中。</span><span class="sxs-lookup"><span data-stu-id="af1a8-170">Set the STATUS_OFFLINE bit in the **PR_STATUS_CODE** property.</span></span> 
    
   - <span data-ttu-id="af1a8-171">**PR_REMOTE_VALIDATE_OK** ([PidTagRemoteValidateOk](pidtagremotevalidateok-canonical-property.md)) 属性设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="af1a8-171">Set the **PR_REMOTE_VALIDATE_OK** ([PidTagRemoteValidateOk](pidtagremotevalidateok-canonical-property.md)) property to TRUE.</span></span>
    
   - <span data-ttu-id="af1a8-172">**PR_STATUS_STRING** ([PidTagStatusString](pidtagstatusstring-canonical-property.md)) 属性设置为 string 类型的值，该值指示的传输提供程序向用户的状态。</span><span class="sxs-lookup"><span data-stu-id="af1a8-172">Set the **PR_STATUS_STRING** ([PidTagStatusString](pidtagstatusstring-canonical-property.md)) property to a string that indicates the transport provider's status to the user.</span></span>
    
   - <span data-ttu-id="af1a8-173">返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="af1a8-173">Return S_OK.</span></span> <span data-ttu-id="af1a8-174">但是，如果不能取消正在进行的操作， **ValidateState**应返回 MAPI_E_BUSY。</span><span class="sxs-lookup"><span data-stu-id="af1a8-174">However, if the operation in progress cannot be canceled, **ValidateState** should return MAPI_E_BUSY.</span></span> 
    
<span data-ttu-id="af1a8-175">FORCE_XP_CONNECT</span><span class="sxs-lookup"><span data-stu-id="af1a8-175">FORCE_XP_CONNECT</span></span> 
  
> <span data-ttu-id="af1a8-176">远程传输提供程序应永远不会建立[IXPLogon::FlushQueues](ixplogon-flushqueues.md)方法所涉及的 MAPI 后台处理程序传输交互的与上下文之外的共享资源 （例如，调制解调器或 COM 端口） 的连接。</span><span class="sxs-lookup"><span data-stu-id="af1a8-176">A remote transport provider should never establish a connection to a shared resource (for example, a modem or COM port) outside the context of the MAPI spooler-transport interaction involved in the [IXPLogon::FlushQueues](ixplogon-flushqueues.md) method.</span></span> <span data-ttu-id="af1a8-177">如果使用此标志调用**ValidateState** ，则您传输提供程序应执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="af1a8-177">If **ValidateState** is called with this flag, your transport provider should do the following:</span></span> 
    
   - <span data-ttu-id="af1a8-178">设置内部状态标志，指示调用**IXPLogon::FlushQueues**方法时，必须建立远程连接。</span><span class="sxs-lookup"><span data-stu-id="af1a8-178">Set an internal status flag to indicate that the remote connection must be established when the **IXPLogon::FlushQueues** method is called.</span></span> 
    
   - <span data-ttu-id="af1a8-179">在状态表，以使 MAPI 后台处理程序启动队列刷新过程中设置正确的值。</span><span class="sxs-lookup"><span data-stu-id="af1a8-179">Set the correct values in the status table to cause the MAPI spooler to initiate the queue flushing process.</span></span>
    
   - <span data-ttu-id="af1a8-180">刷新队列的完成后，版本的共享的资源。</span><span class="sxs-lookup"><span data-stu-id="af1a8-180">When flushing of queues is complete, release the shared resource.</span></span>
    
   - <span data-ttu-id="af1a8-181">清除 STATUS_OFFLINE 位**PR_STATUS_CODE**属性中。</span><span class="sxs-lookup"><span data-stu-id="af1a8-181">Clear the STATUS_OFFLINE bit in the **PR_STATUS_CODE** property.</span></span> 
    
   - <span data-ttu-id="af1a8-182">返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="af1a8-182">Return S_OK.</span></span>
    
<span data-ttu-id="af1a8-183">FORCE_XP_DISCONNECT</span><span class="sxs-lookup"><span data-stu-id="af1a8-183">FORCE_XP_DISCONNECT</span></span> 
  
> <span data-ttu-id="af1a8-184">远程传输提供程序应释放其连接到的消息的系统资源。</span><span class="sxs-lookup"><span data-stu-id="af1a8-184">The remote transport provider should release its connection to the messaging system resources.</span></span> <span data-ttu-id="af1a8-185">此操作后，它应**PR_STATUS_CODE**属性中设置 STATUS_OFFLINE 位，并返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="af1a8-185">After doing this, it should set the STATUS_OFFLINE bit in the **PR_STATUS_CODE** property and return S_OK.</span></span> 
    
<span data-ttu-id="af1a8-186">PROCESS_XP_HEADER_CACHE</span><span class="sxs-lookup"><span data-stu-id="af1a8-186">PROCESS_XP_HEADER_CACHE</span></span> 
  
> <span data-ttu-id="af1a8-187">远程传输提供程序应处理远程邮件，并上载已延迟任何消息。</span><span class="sxs-lookup"><span data-stu-id="af1a8-187">The remote transport provider should process remote messages and upload any messages that have been deferred.</span></span> <span data-ttu-id="af1a8-188">若要执行此操作，传输提供程序必须登录对象的状态行中设置以下属性值：</span><span class="sxs-lookup"><span data-stu-id="af1a8-188">To do this, the transport provider must set the following property values in the logon object's status row:</span></span>
    
   - <span data-ttu-id="af1a8-189">**PR_STATUS_STRING**属性设置为 string 类型的值，该值指示的传输提供程序向用户的状态。</span><span class="sxs-lookup"><span data-stu-id="af1a8-189">Set the **PR_STATUS_STRING** property to a string that indicates the transport provider's status to the user.</span></span> 
    
   - <span data-ttu-id="af1a8-190">**PR_STATUS_CODE**属性中设置的 STATUS_OUTBOUND_ENABLED 和 STATUS_OUTBOUND_ACTIVE 位。</span><span class="sxs-lookup"><span data-stu-id="af1a8-190">Set the STATUS_OUTBOUND_ENABLED and STATUS_OUTBOUND_ACTIVE bits in the **PR_STATUS_CODE** property.</span></span> 
    
   - <span data-ttu-id="af1a8-191">将**PR_REMOTE_VALIDATE_OK**属性设置为 FALSE 的传输提供程序的状态行中。</span><span class="sxs-lookup"><span data-stu-id="af1a8-191">Set the **PR_REMOTE_VALIDATE_OK** property in the transport provider's status row to FALSE.</span></span> 
    
   - <span data-ttu-id="af1a8-192">如果 （如下载邮件头） 正在执行其他操作**ValidateState**调用**ValidateState**时，应返回 MAPI_E_BUSY。</span><span class="sxs-lookup"><span data-stu-id="af1a8-192">If another operation is in progress (such as downloading headers) when **ValidateState** is called, **ValidateState** should return MAPI_E_BUSY.</span></span> 
    
   - <span data-ttu-id="af1a8-193">执行用于处理 REFRESH_XP_HEADER_CACHE 标志，同样，以满足要求的 Microsoft Exchange 客户端代码。</span><span class="sxs-lookup"><span data-stu-id="af1a8-193">Execute the code for processing the REFRESH_XP_HEADER_CACHE flag, as well, to satisfy requirements of the Microsoft Exchange client.</span></span>
    
<span data-ttu-id="af1a8-194">REFRESH_XP_HEADER_CACHE</span><span class="sxs-lookup"><span data-stu-id="af1a8-194">REFRESH_XP_HEADER_CACHE</span></span> 
  
> <span data-ttu-id="af1a8-195">远程传输提供程序应从邮件系统中检索任何新的邮件头。</span><span class="sxs-lookup"><span data-stu-id="af1a8-195">The remote transport provider should retrieve any new message headers from the messaging system.</span></span> <span data-ttu-id="af1a8-196">若要执行此操作，传输提供程序必须执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="af1a8-196">To do this, the transport provider must do the following:</span></span>
    
   - <span data-ttu-id="af1a8-197">**PR_STATUS_STRING**属性设置为 string 类型的值，该值指示的传输提供程序向用户的状态。</span><span class="sxs-lookup"><span data-stu-id="af1a8-197">Set the **PR_STATUS_STRING** property to a string that indicates the transport provider's status to the user.</span></span> 
    
   - <span data-ttu-id="af1a8-198">**PR_STATUS_CODE**属性中设置的 STATUS_INBOUND_ENABLED 和 STATUS_INBOUND_ACTIVE 位。</span><span class="sxs-lookup"><span data-stu-id="af1a8-198">Set the STATUS_INBOUND_ENABLED and STATUS_INBOUND_ACTIVE bits in the **PR_STATUS_CODE** property.</span></span> 
    
   - <span data-ttu-id="af1a8-199">清除 STATUS_OFFLINE 位**PR_STATUS_CODE**属性中。</span><span class="sxs-lookup"><span data-stu-id="af1a8-199">Clear the STATUS_OFFLINE bit in the **PR_STATUS_CODE** property.</span></span> 
    
   - <span data-ttu-id="af1a8-200">设置 STATUS_ONLINE 位**PR_STATUS_CODE**属性中。</span><span class="sxs-lookup"><span data-stu-id="af1a8-200">Set the STATUS_ONLINE bit in the **PR_STATUS_CODE** property.</span></span> 
    
   - <span data-ttu-id="af1a8-201">将**PR_REMOTE_VALIDATE_OK**属性设置为 FALSE 的传输提供程序的状态行中。</span><span class="sxs-lookup"><span data-stu-id="af1a8-201">Set the **PR_REMOTE_VALIDATE_OK** property in the transport provider's status row to FALSE.</span></span> 
    
<span data-ttu-id="af1a8-202">SHOW_XP_SESSION_UI</span><span class="sxs-lookup"><span data-stu-id="af1a8-202">SHOW_XP_SESSION_UI</span></span> 
  
> <span data-ttu-id="af1a8-203">如果您传输提供程序具有用于处理邮件头 （如确认消息的下载对话框） 的用户界面的任何部分，应显示的对话框。</span><span class="sxs-lookup"><span data-stu-id="af1a8-203">If your transport provider has any pieces of user interface for processing the message headers (such as a dialog box that confirms the downloading of messages), that dialog box should be displayed.</span></span> <span data-ttu-id="af1a8-204">否则， **ValidateState**可以返回 MAPI_E_NO_SUPPORT。</span><span class="sxs-lookup"><span data-stu-id="af1a8-204">Otherwise, **ValidateState** can return MAPI_E_NO_SUPPORT.</span></span> 
    
<span data-ttu-id="af1a8-205">如果这些之外的任何标志以传递， **ValidateState**应返回 MAPI_E_UNKNOWN_FLAGS。</span><span class="sxs-lookup"><span data-stu-id="af1a8-205">If any flags other than these are passed in, **ValidateState** should return MAPI_E_UNKNOWN_FLAGS.</span></span> 
  
<span data-ttu-id="af1a8-206">到传输提供程序的客户端的呼叫通常会**IMAPIStatus::ValidateState**方法。</span><span class="sxs-lookup"><span data-stu-id="af1a8-206">The client's call to the transport provider will often be to the **IMAPIStatus::ValidateState** method.</span></span> <span data-ttu-id="af1a8-207">处理期间**ValidateState**，传输提供程序不应执行任何操作，分配紧缺系统资源，如调制解调器或 COM 端口。</span><span class="sxs-lookup"><span data-stu-id="af1a8-207">During the processing of **ValidateState**, the transport provider should not perform any actions that allocate scarce system resources, such as a modem or COM port.</span></span> <span data-ttu-id="af1a8-208">这是因为 MAPI 后台处理程序将有时需要刷新多个传输提供程序上的队列。</span><span class="sxs-lookup"><span data-stu-id="af1a8-208">This is because the MAPI spooler will sometimes need to flush queues on more than one transport provider.</span></span> <span data-ttu-id="af1a8-209">但是，客户端可以随时调用任何传输提供程序**ValidateState**方法。</span><span class="sxs-lookup"><span data-stu-id="af1a8-209">However, the client can call any transport provider's **ValidateState** method at any time.</span></span> <span data-ttu-id="af1a8-210">如果您传输提供程序尝试**ValidateState**处理过程中分配紧缺资源，可以由于与 MAPI 后台处理程序指导刷新其队列的另一个传输提供程序冲突而导致错误。</span><span class="sxs-lookup"><span data-stu-id="af1a8-210">If your transport provider attempts to allocate a scarce resource during the processing of **ValidateState**, an error can result due to conflict with another transport provider that the MAPI spooler has instructed to flush its queues.</span></span> <span data-ttu-id="af1a8-211">如果允许 MAPI 后台处理程序的指导下发生的所有紧缺资源分配，则可以避免这样的冲突。</span><span class="sxs-lookup"><span data-stu-id="af1a8-211">If you allow all scarce resource allocations to occur under the direction of the MAPI spooler, you can avoid such conflicts.</span></span> <span data-ttu-id="af1a8-212">传输提供程序应支持**PR_REMOTE_VALIDATE_OK**属性，因此客户端应用程序可以检测到传输提供程序时正忙或等待 MAPI 后台处理程序启动操作。</span><span class="sxs-lookup"><span data-stu-id="af1a8-212">Your transport provider should support the **PR_REMOTE_VALIDATE_OK** property so client applications can detect when your transport provider is busy or waiting for the MAPI spooler to initiate an action.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="af1a8-213">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="af1a8-213">Notes to callers</span></span>

<span data-ttu-id="af1a8-214">由于此方法可能导致其他可能较长的调用进行， **ValidateState**可以返回 MAPI_E_BUSY 来通知您此方法正在等待完成其他操作。</span><span class="sxs-lookup"><span data-stu-id="af1a8-214">Because this method can cause other potentially lengthy calls to be made, **ValidateState** can return MAPI_E_BUSY to inform you that this method is waiting for the completion of another operation.</span></span> <span data-ttu-id="af1a8-215">您应等待，直到在挂起的操作尝试另一个任务之前已完成。</span><span class="sxs-lookup"><span data-stu-id="af1a8-215">You should wait until the pending operation is complete before attempting another task.</span></span> 
  
<span data-ttu-id="af1a8-216">您必须对您的呼叫传输提供程序状态对象的大多数控制。</span><span class="sxs-lookup"><span data-stu-id="af1a8-216">You have the most control over your calls to transport provider status objects.</span></span> <span data-ttu-id="af1a8-217">您可以将一个或多个标志传递到**ValidateState**影响传输提供程序的操作。</span><span class="sxs-lookup"><span data-stu-id="af1a8-217">You can pass one or more flags to **ValidateState** that affect the transport provider's operations.</span></span> <span data-ttu-id="af1a8-218">例如，ABORT_XP_HEADER_OPERATION 标志指示用户已取消验证。</span><span class="sxs-lookup"><span data-stu-id="af1a8-218">For example, the ABORT_XP_HEADER_OPERATION flag indicates that the user canceled the validation.</span></span> <span data-ttu-id="af1a8-219">传输提供程序可以决定要放弃，返回 MAPI_E_USER_CANCELED，也可以继续。</span><span class="sxs-lookup"><span data-stu-id="af1a8-219">Transport providers can decide to abort, returning MAPI_E_USER_CANCELED, or can continue.</span></span> 
  
<span data-ttu-id="af1a8-220">您可以对服务提供商的状态对象或 MAPI 后台处理程序的调用，以指示已更改的配置选项设置 CONFIG_CHANGED 标志。</span><span class="sxs-lookup"><span data-stu-id="af1a8-220">You can set the CONFIG_CHANGED flag on a call to either the status object of a service provider or the MAPI spooler to indicate that a configuration option has been changed.</span></span> <span data-ttu-id="af1a8-221">您可以使用 CONFIG_CHANGED 动态重新配置的传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="af1a8-221">You can use CONFIG_CHANGED to dynamically reconfigure a transport provider.</span></span> <span data-ttu-id="af1a8-222">当在服务提供商的状态对象调用设置 CONFIG_CHANGED 时，提供程序返回[IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md)调用警告更改 MAPI 后台处理程序作为响应。</span><span class="sxs-lookup"><span data-stu-id="af1a8-222">When you set CONFIG_CHANGED on a call to a service provider's status object, the provider responds with a call to [IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md) to alert the MAPI spooler of the change.</span></span> <span data-ttu-id="af1a8-223">当在 MAPI 后台处理程序的状态对象调用设置 CONFIG_CHANGED 时，后台处理程序将为每个活动传输提供程序调用[IXPLogon::AddressTypes](ixplogon-addresstypes.md) 。</span><span class="sxs-lookup"><span data-stu-id="af1a8-223">When you set CONFIG_CHANGED on a call to the MAPI spooler's status object, the spooler calls [IXPLogon::AddressTypes](ixplogon-addresstypes.md) for each active transport provider.</span></span> <span data-ttu-id="af1a8-224">**AddressTypes**通知传输的受支持的地址类型 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="af1a8-224">**AddressTypes** informs the MAPI spooler of a transport's supported address types.</span></span> <span data-ttu-id="af1a8-225">如果预计验证需要很长时间，某些服务提供商还显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="af1a8-225">Some service providers also display a progress indicator if the validation is expected to take a long time.</span></span> <span data-ttu-id="af1a8-226">显示进度指示器很有用，但不是需要。</span><span class="sxs-lookup"><span data-stu-id="af1a8-226">Displaying a progress indicator is helpful, but not required.</span></span> 
  
<span data-ttu-id="af1a8-227">当设置 SUPPRESS_UI 标志时，可以显示的任何配置属性表或进度对话框。</span><span class="sxs-lookup"><span data-stu-id="af1a8-227">When the SUPPRESS_UI flag is set, none of the configuration property sheets or progress dialog boxes can be displayed.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="af1a8-228">另请参阅</span><span class="sxs-lookup"><span data-stu-id="af1a8-228">See also</span></span>

- [<span data-ttu-id="af1a8-229">IMAPISupport::SpoolerNotify</span><span class="sxs-lookup"><span data-stu-id="af1a8-229">IMAPISupport::SpoolerNotify</span></span>](imapisupport-spoolernotify.md)
- [<span data-ttu-id="af1a8-230">IXPLogon::AddressTypes</span><span class="sxs-lookup"><span data-stu-id="af1a8-230">IXPLogon::AddressTypes</span></span>](ixplogon-addresstypes.md)
- [<span data-ttu-id="af1a8-231">IXPLogon::FlushQueues</span><span class="sxs-lookup"><span data-stu-id="af1a8-231">IXPLogon::FlushQueues</span></span>](ixplogon-flushqueues.md)
- [<span data-ttu-id="af1a8-232">PidTagRemoteValidateOk 规范属性</span><span class="sxs-lookup"><span data-stu-id="af1a8-232">PidTagRemoteValidateOk Canonical Property</span></span>](pidtagremotevalidateok-canonical-property.md)
- [<span data-ttu-id="af1a8-233">PidTagResourceMethods 规范属性</span><span class="sxs-lookup"><span data-stu-id="af1a8-233">PidTagResourceMethods Canonical Property</span></span>](pidtagresourcemethods-canonical-property.md)
- [<span data-ttu-id="af1a8-234">PidTagStatusCode 规范属性</span><span class="sxs-lookup"><span data-stu-id="af1a8-234">PidTagStatusCode Canonical Property</span></span>](pidtagstatuscode-canonical-property.md)
- [<span data-ttu-id="af1a8-235">PidTagStatusString 规范属性</span><span class="sxs-lookup"><span data-stu-id="af1a8-235">PidTagStatusString Canonical Property</span></span>](pidtagstatusstring-canonical-property.md)
- [<span data-ttu-id="af1a8-236">IMAPIStatus : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="af1a8-236">IMAPIStatus : IMAPIProp</span></span>](imapistatusimapiprop.md)

