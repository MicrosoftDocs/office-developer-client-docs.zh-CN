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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: a3469e6baacb52938b870ca87d824bf640a8a88f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351567"
---
# <a name="ixplogonvalidatestate"></a><span data-ttu-id="ed258-103">IXPLogon::ValidateState</span><span class="sxs-lookup"><span data-stu-id="ed258-103">IXPLogon::ValidateState</span></span>

  
  
<span data-ttu-id="ed258-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ed258-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ed258-105">检查传输提供程序的外部状态。</span><span class="sxs-lookup"><span data-stu-id="ed258-105">Checks the transport provider's external status.</span></span> 
  
```cpp
HRESULT ValidateState(
  ULONG_PTR ulUIParam,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="ed258-106">参数</span><span class="sxs-lookup"><span data-stu-id="ed258-106">Parameters</span></span>

 <span data-ttu-id="ed258-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="ed258-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="ed258-108">实时此方法显示的任何对话框或窗口的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="ed258-108">[in] A handle to the parent window of any dialog boxes or windows that this method displays.</span></span>
    
 <span data-ttu-id="ed258-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="ed258-109">_ulFlags_</span></span>
  
> <span data-ttu-id="ed258-110">实时用于控制如何执行状态检查和状态检查结果的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="ed258-110">[in] A bitmask of flags that controls how the status check is performed and the results of the status check.</span></span> <span data-ttu-id="ed258-111">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="ed258-111">The following flags can be set:</span></span>
    
<span data-ttu-id="ed258-112">ABORT_XP_HEADER_OPERATION</span><span class="sxs-lookup"><span data-stu-id="ed258-112">ABORT_XP_HEADER_OPERATION</span></span> 
  
> <span data-ttu-id="ed258-113">用户取消了操作, 通常是单击对话框中的 "**取消**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="ed258-113">The user canceled the operation, typically by clicking the **Cancel** button in a dialog box.</span></span> <span data-ttu-id="ed258-114">传输提供程序可以选择继续处理此操作, 也可以中止操作并返回 MAPI_E_USER_CANCELED。</span><span class="sxs-lookup"><span data-stu-id="ed258-114">The transport provider has the option to continue working on the operation, or it can abort the operation and return MAPI_E_USER_CANCELED.</span></span> 
    
<span data-ttu-id="ed258-115">CONFIG_CHANGED</span><span class="sxs-lookup"><span data-stu-id="ed258-115">CONFIG_CHANGED</span></span> 
  
> <span data-ttu-id="ed258-116">通过使 MAPI 后台处理程序调用[IXPLogon:: AddressTypes](ixplogon-addresstypes.md)方法来验证当前加载的传输提供程序的状态。</span><span class="sxs-lookup"><span data-stu-id="ed258-116">Validates the state of currently loaded transport providers by causing the MAPI spooler to call their [IXPLogon::AddressTypes](ixplogon-addresstypes.md) method.</span></span> <span data-ttu-id="ed258-117">此标志还为 MAPI 后台处理程序提供了在不强制客户端应用程序注销和重新登录的情况下纠正关键传输提供程序故障的机会。</span><span class="sxs-lookup"><span data-stu-id="ed258-117">This flag also provides the MAPI spooler an opportunity to correct critical transport-provider failures without forcing client applications to log off and then log on again.</span></span> 
    
<span data-ttu-id="ed258-118">FORCE_XP_CONNECT</span><span class="sxs-lookup"><span data-stu-id="ed258-118">FORCE_XP_CONNECT</span></span> 
  
> <span data-ttu-id="ed258-119">用户选择了一个连接操作。</span><span class="sxs-lookup"><span data-stu-id="ed258-119">The user selected a connect operation.</span></span> <span data-ttu-id="ed258-120">将此标志与 REFRESH_XP_HEADER_CACHE 或 PROCESS_XP_HEADER_CACHE 标志一起使用时, 将发生 connect 操作, 而不进行缓存。</span><span class="sxs-lookup"><span data-stu-id="ed258-120">When this flag is used with the REFRESH_XP_HEADER_CACHE or PROCESS_XP_HEADER_CACHE flag, the connect action occurs without caching.</span></span>
    
<span data-ttu-id="ed258-121">FORCE_XP_DISCONNECT</span><span class="sxs-lookup"><span data-stu-id="ed258-121">FORCE_XP_DISCONNECT</span></span> 
  
> <span data-ttu-id="ed258-122">用户选择了一个断开连接操作。</span><span class="sxs-lookup"><span data-stu-id="ed258-122">The user selected a disconnect operation.</span></span> <span data-ttu-id="ed258-123">将此标志与 REFRESH_XP_HEADER_CACHE 或 PROCESS_XP_HEADER_CACHE 一起使用时, 不进行缓存就会发生断开连接操作。</span><span class="sxs-lookup"><span data-stu-id="ed258-123">When this flag is used with REFRESH_XP_HEADER_CACHE or PROCESS_XP_HEADER_CACHE, the disconnect action occurs without caching.</span></span>
    
<span data-ttu-id="ed258-124">PROCESS_XP_HEADER_CACHE</span><span class="sxs-lookup"><span data-stu-id="ed258-124">PROCESS_XP_HEADER_CACHE</span></span> 
  
> <span data-ttu-id="ed258-125">应处理标头缓存表中的条目, 应下载所有标记为 MSGSTATUS_REMOTE_DOWNLOAD 标志的邮件, 并且应删除所有使用 MSGSTATUS_REMOTE_DELETE 标志标记的邮件。</span><span class="sxs-lookup"><span data-stu-id="ed258-125">Entries in the header cache table should be processed, all messages marked with the MSGSTATUS_REMOTE_DOWNLOAD flag should be downloaded, and all messages marked with the MSGSTATUS_REMOTE_DELETE flag should be deleted.</span></span> <span data-ttu-id="ed258-126">应移动同时包含 MSGSTATUS_REMOTE_DOWNLOAD 和 MSGSTATUS_REMOTE_DELETE 集的邮件。</span><span class="sxs-lookup"><span data-stu-id="ed258-126">Messages that have both MSGSTATUS_REMOTE_DOWNLOAD and MSGSTATUS_REMOTE_DELETE set should be moved.</span></span>
    
<span data-ttu-id="ed258-127">REFRESH_XP_HEADER_CACHE</span><span class="sxs-lookup"><span data-stu-id="ed258-127">REFRESH_XP_HEADER_CACHE</span></span> 
  
> <span data-ttu-id="ed258-128">应下载邮件头的新列表, 并且应清除所有邮件状态标记标志。</span><span class="sxs-lookup"><span data-stu-id="ed258-128">A new list of message headers should be downloaded, and all message status marking flags should be cleared.</span></span>
    
<span data-ttu-id="ed258-129">SUPPRESS_UI</span><span class="sxs-lookup"><span data-stu-id="ed258-129">SUPPRESS_UI</span></span> 
  
> <span data-ttu-id="ed258-130">阻止传输提供程序显示用户界面。</span><span class="sxs-lookup"><span data-stu-id="ed258-130">Prevents the transport provider from displaying a user interface.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="ed258-131">返回值</span><span class="sxs-lookup"><span data-stu-id="ed258-131">Return value</span></span>

<span data-ttu-id="ed258-132">S_OK</span><span class="sxs-lookup"><span data-stu-id="ed258-132">S_OK</span></span> 
  
> <span data-ttu-id="ed258-133">调用成功, 并返回了所需的一个或一些值。</span><span class="sxs-lookup"><span data-stu-id="ed258-133">The call succeeded and returned the expected value or values.</span></span>
    
<span data-ttu-id="ed258-134">MAPI_E_BUSY</span><span class="sxs-lookup"><span data-stu-id="ed258-134">MAPI_E_BUSY</span></span> 
  
> <span data-ttu-id="ed258-135">正在进行另一个操作;应允许完成此操作, 否则应在尝试执行此操作之前将其停止。</span><span class="sxs-lookup"><span data-stu-id="ed258-135">Another operation is in progress; it should be allowed to complete, or it should be stopped before this operation is attempted.</span></span>
    
<span data-ttu-id="ed258-136">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="ed258-136">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="ed258-137">涉及的远程传输提供程序不支持用户界面, 并且客户端应用程序本身应显示对话框。</span><span class="sxs-lookup"><span data-stu-id="ed258-137">The remote transport provider involved does not support a user interface, and the client application itself should display the dialog box.</span></span>
    
<span data-ttu-id="ed258-138">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="ed258-138">MAPI_E_USER_CANCEL</span></span> 
  
> <span data-ttu-id="ed258-139">用户取消了操作, 通常是单击对话框中的 "**取消**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="ed258-139">The user canceled the operation, typically by clicking the **Cancel** button in a dialog box.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="ed258-140">注解</span><span class="sxs-lookup"><span data-stu-id="ed258-140">Remarks</span></span>

<span data-ttu-id="ed258-141">MAPI 后台处理程序调用**IXPLogon:: ValidateState**方法, 以支持对 status 对象的[IMAPIStatus:: ValidateState](imapistatus-validatestate.md)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="ed258-141">The MAPI spooler calls the **IXPLogon::ValidateState** method to support calls to the [IMAPIStatus::ValidateState](imapistatus-validatestate.md) method for the status object.</span></span> <span data-ttu-id="ed258-142">传输提供程序应将**IXPLogon:: ValidateState**调用完全按照 MAPI 后台处理程序打开当前登录会话的状态对象, 然后对该对象调用**IMAPIStatus:: ValidateState** 。</span><span class="sxs-lookup"><span data-stu-id="ed258-142">The transport provider should respond to the **IXPLogon::ValidateState** call exactly as if the MAPI spooler had opened a status object for the current logon session and then called **IMAPIStatus::ValidateState** on that object.</span></span> 
  
<span data-ttu-id="ed258-143">若要支持**IMAPIStatus:: ValidateState**的实现, MAPI 后台处理程序将对在配置文件会话中运行的所有活动传输提供程序的所有登录对象调用**IXPLogon:: ValidateState** 。</span><span class="sxs-lookup"><span data-stu-id="ed258-143">To support its implementation of **IMAPIStatus::ValidateState**, the MAPI spooler calls **IXPLogon::ValidateState** on all logon objects for all active transport providers that are running in a profile session.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ed258-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ed258-144">See also</span></span>



[<span data-ttu-id="ed258-145">IMAPIStatus::ValidateState</span><span class="sxs-lookup"><span data-stu-id="ed258-145">IMAPIStatus::ValidateState</span></span>](imapistatus-validatestate.md)
  
[<span data-ttu-id="ed258-146">IXPLogon::AddressTypes</span><span class="sxs-lookup"><span data-stu-id="ed258-146">IXPLogon::AddressTypes</span></span>](ixplogon-addresstypes.md)
  
[<span data-ttu-id="ed258-147">IXPLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="ed258-147">IXPLogon : IUnknown</span></span>](ixplogoniunknown.md)

