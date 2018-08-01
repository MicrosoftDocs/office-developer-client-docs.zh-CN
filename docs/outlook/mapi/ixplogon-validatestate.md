---
title: IXPLogonValidateState
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IXPLogon.ValidateState
api_type:
- COM
ms.assetid: c3649daa-cba1-48e3-9ffb-069c1bcf8228
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 165fe3a72060e88dc34d8153c13ae58bcbd9ae0b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776152"
---
# <a name="ixplogonvalidatestate"></a><span data-ttu-id="680af-103">IXPLogon::ValidateState</span><span class="sxs-lookup"><span data-stu-id="680af-103">IXPLogon::ValidateState</span></span>

  
  
<span data-ttu-id="680af-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="680af-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="680af-105">检查传输提供程序的外部状态。</span><span class="sxs-lookup"><span data-stu-id="680af-105">Checks the transport provider's external status.</span></span> 
  
```cpp
HRESULT ValidateState(
  ULONG_PTR ulUIParam,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="680af-106">参数</span><span class="sxs-lookup"><span data-stu-id="680af-106">Parameters</span></span>

 <span data-ttu-id="680af-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="680af-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="680af-108">[in]任何对话框的父窗口或该方法显示的窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="680af-108">[in] A handle to the parent window of any dialog boxes or windows that this method displays.</span></span>
    
 <span data-ttu-id="680af-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="680af-109">_ulFlags_</span></span>
  
> <span data-ttu-id="680af-110">[in]控制如何执行状态检查的标志的位掩码和状态检查的结果。</span><span class="sxs-lookup"><span data-stu-id="680af-110">[in] A bitmask of flags that controls how the status check is performed and the results of the status check.</span></span> <span data-ttu-id="680af-111">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="680af-111">The following flags can be set:</span></span>
    
<span data-ttu-id="680af-112">ABORT_XP_HEADER_OPERATION</span><span class="sxs-lookup"><span data-stu-id="680af-112">ABORT_XP_HEADER_OPERATION</span></span> 
  
> <span data-ttu-id="680af-113">用户取消操作，通常通过单击对话框中的**取消**按钮。</span><span class="sxs-lookup"><span data-stu-id="680af-113">The user canceled the operation, typically by clicking the **Cancel** button in a dialog box.</span></span> <span data-ttu-id="680af-114">传输提供程序具有选项后，继续使用上一操作，或者可以中止操作并返回 MAPI_E_USER_CANCELED。</span><span class="sxs-lookup"><span data-stu-id="680af-114">The transport provider has the option to continue working on the operation, or it can abort the operation and return MAPI_E_USER_CANCELED.</span></span> 
    
<span data-ttu-id="680af-115">CONFIG_CHANGED</span><span class="sxs-lookup"><span data-stu-id="680af-115">CONFIG_CHANGED</span></span> 
  
> <span data-ttu-id="680af-116">MAPI 后台处理程序调用其[IXPLogon::AddressTypes](ixplogon-addresstypes.md)方法，从而验证当前加载的传输提供程序的状态。</span><span class="sxs-lookup"><span data-stu-id="680af-116">Validates the state of currently loaded transport providers by causing the MAPI spooler to call their [IXPLogon::AddressTypes](ixplogon-addresstypes.md) method.</span></span> <span data-ttu-id="680af-117">此标志还提供 MAPI 后台处理程序而不强制注销并重新登录的客户端应用程序中更正关键的传输提供程序失败的机会。</span><span class="sxs-lookup"><span data-stu-id="680af-117">This flag also provides the MAPI spooler an opportunity to correct critical transport-provider failures without forcing client applications to log off and then log on again.</span></span> 
    
<span data-ttu-id="680af-118">FORCE_XP_CONNECT</span><span class="sxs-lookup"><span data-stu-id="680af-118">FORCE_XP_CONNECT</span></span> 
  
> <span data-ttu-id="680af-119">用户选择一个连接操作。</span><span class="sxs-lookup"><span data-stu-id="680af-119">The user selected a connect operation.</span></span> <span data-ttu-id="680af-120">此标志用于 REFRESH_XP_HEADER_CACHE 或 PROCESS_XP_HEADER_CACHE 标志，连接操作时不进行缓存。</span><span class="sxs-lookup"><span data-stu-id="680af-120">When this flag is used with the REFRESH_XP_HEADER_CACHE or PROCESS_XP_HEADER_CACHE flag, the connect action occurs without caching.</span></span>
    
<span data-ttu-id="680af-121">FORCE_XP_DISCONNECT</span><span class="sxs-lookup"><span data-stu-id="680af-121">FORCE_XP_DISCONNECT</span></span> 
  
> <span data-ttu-id="680af-122">用户选择断开连接操作。</span><span class="sxs-lookup"><span data-stu-id="680af-122">The user selected a disconnect operation.</span></span> <span data-ttu-id="680af-123">与 REFRESH_XP_HEADER_CACHE 或 PROCESS_XP_HEADER_CACHE 使用此标志，则断开连接操作时不进行缓存。</span><span class="sxs-lookup"><span data-stu-id="680af-123">When this flag is used with REFRESH_XP_HEADER_CACHE or PROCESS_XP_HEADER_CACHE, the disconnect action occurs without caching.</span></span>
    
<span data-ttu-id="680af-124">PROCESS_XP_HEADER_CACHE</span><span class="sxs-lookup"><span data-stu-id="680af-124">PROCESS_XP_HEADER_CACHE</span></span> 
  
> <span data-ttu-id="680af-125">应处理标题缓存表中的条目，应下载标记有 MSGSTATUS_REMOTE_DOWNLOAD 标志的所有邮件，以及应删除与 MSGSTATUS_REMOTE_DELETE 标志标记的所有邮件。</span><span class="sxs-lookup"><span data-stu-id="680af-125">Entries in the header cache table should be processed, all messages marked with the MSGSTATUS_REMOTE_DOWNLOAD flag should be downloaded, and all messages marked with the MSGSTATUS_REMOTE_DELETE flag should be deleted.</span></span> <span data-ttu-id="680af-126">应移动 MSGSTATUS_REMOTE_DOWNLOAD 和 MSGSTATUS_REMOTE_DELETE 设置的消息。</span><span class="sxs-lookup"><span data-stu-id="680af-126">Messages that have both MSGSTATUS_REMOTE_DOWNLOAD and MSGSTATUS_REMOTE_DELETE set should be moved.</span></span>
    
<span data-ttu-id="680af-127">REFRESH_XP_HEADER_CACHE</span><span class="sxs-lookup"><span data-stu-id="680af-127">REFRESH_XP_HEADER_CACHE</span></span> 
  
> <span data-ttu-id="680af-128">应下载邮件头的新列表，并应清除标记标志的所有邮件状态。</span><span class="sxs-lookup"><span data-stu-id="680af-128">A new list of message headers should be downloaded, and all message status marking flags should be cleared.</span></span>
    
<span data-ttu-id="680af-129">SUPPRESS_UI</span><span class="sxs-lookup"><span data-stu-id="680af-129">SUPPRESS_UI</span></span> 
  
> <span data-ttu-id="680af-130">防止传输提供程序显示的用户界面。</span><span class="sxs-lookup"><span data-stu-id="680af-130">Prevents the transport provider from displaying a user interface.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="680af-131">返回值</span><span class="sxs-lookup"><span data-stu-id="680af-131">Return value</span></span>

<span data-ttu-id="680af-132">S_OK</span><span class="sxs-lookup"><span data-stu-id="680af-132">S_OK</span></span> 
  
> <span data-ttu-id="680af-133">呼叫成功，并返回预期的值。</span><span class="sxs-lookup"><span data-stu-id="680af-133">The call succeeded and returned the expected value or values.</span></span>
    
<span data-ttu-id="680af-134">MAPI_E_BUSY</span><span class="sxs-lookup"><span data-stu-id="680af-134">MAPI_E_BUSY</span></span> 
  
> <span data-ttu-id="680af-135">正在进行; 另一个操作应允许其完成，或尝试此操作之前，应停止它。</span><span class="sxs-lookup"><span data-stu-id="680af-135">Another operation is in progress; it should be allowed to complete, or it should be stopped before this operation is attempted.</span></span>
    
<span data-ttu-id="680af-136">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="680af-136">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="680af-137">所涉及的远程传输提供程序不支持用户界面，并在客户端应用程序自身应显示对话框。</span><span class="sxs-lookup"><span data-stu-id="680af-137">The remote transport provider involved does not support a user interface, and the client application itself should display the dialog box.</span></span>
    
<span data-ttu-id="680af-138">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="680af-138">MAPI_E_USER_CANCEL</span></span> 
  
> <span data-ttu-id="680af-139">用户取消操作，通常通过单击对话框中的**取消**按钮。</span><span class="sxs-lookup"><span data-stu-id="680af-139">The user canceled the operation, typically by clicking the **Cancel** button in a dialog box.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="680af-140">说明</span><span class="sxs-lookup"><span data-stu-id="680af-140">Remarks</span></span>

<span data-ttu-id="680af-141">MAPI 后台处理程序调用**IXPLogon::ValidateState**方法以支持的状态对象调用[IMAPIStatus::ValidateState](imapistatus-validatestate.md)方法。</span><span class="sxs-lookup"><span data-stu-id="680af-141">The MAPI spooler calls the **IXPLogon::ValidateState** method to support calls to the [IMAPIStatus::ValidateState](imapistatus-validatestate.md) method for the status object.</span></span> <span data-ttu-id="680af-142">传输提供程序应当给出答复到**IXPLogon::ValidateState**的呼叫就好像 MAPI 后台处理程序已打开了当前登录会话状态对象，然后在该对象上调用**IMAPIStatus::ValidateState** 。</span><span class="sxs-lookup"><span data-stu-id="680af-142">The transport provider should respond to the **IXPLogon::ValidateState** call exactly as if the MAPI spooler had opened a status object for the current logon session and then called **IMAPIStatus::ValidateState** on that object.</span></span> 
  
<span data-ttu-id="680af-143">若要支持**IMAPIStatus::ValidateState**其实现，MAPI 后台处理程序调用**IXPLogon::ValidateState**登录的所有对象上为配置文件会话中运行的所有活动传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="680af-143">To support its implementation of **IMAPIStatus::ValidateState**, the MAPI spooler calls **IXPLogon::ValidateState** on all logon objects for all active transport providers that are running in a profile session.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="680af-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="680af-144">See also</span></span>



[<span data-ttu-id="680af-145">IMAPIStatus::ValidateState</span><span class="sxs-lookup"><span data-stu-id="680af-145">IMAPIStatus::ValidateState</span></span>](imapistatus-validatestate.md)
  
[<span data-ttu-id="680af-146">IXPLogon::AddressTypes</span><span class="sxs-lookup"><span data-stu-id="680af-146">IXPLogon::AddressTypes</span></span>](ixplogon-addresstypes.md)
  
[<span data-ttu-id="680af-147">IXPLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="680af-147">IXPLogon : IUnknown</span></span>](ixplogoniunknown.md)

