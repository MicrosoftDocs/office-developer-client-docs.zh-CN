---
title: IXPProviderTransportLogon
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IXPProvider.TransportLogon
api_type:
- COM
ms.assetid: 534929f2-36a2-463d-8c4c-d86060cde127
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 96e81442125ae49e0c2856a1cf3a97a16d3453cf
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22583335"
---
# <a name="ixpprovidertransportlogon"></a><span data-ttu-id="b14b6-103">IXPProvider::TransportLogon</span><span class="sxs-lookup"><span data-stu-id="b14b6-103">IXPProvider::TransportLogon</span></span>

<span data-ttu-id="b14b6-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b14b6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b14b6-105">建立一个会话中的客户端应用程序登录到传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="b14b6-105">Establishes a session in which a client application logs on to a transport provider.</span></span> 
  
```cpp
HRESULT TransportLogon(
  LPMAPISUP lpMAPISup,
  ULONG_PTR ulUIParam,
  LPSTR lpszProfileName,
  ULONG FAR * lpulFlags,
  LPMAPIERROR FAR * lppMAPIError,
  LPXPLOGON FAR * lppXPLogon
);
```

## <a name="parameters"></a><span data-ttu-id="b14b6-106">参数</span><span class="sxs-lookup"><span data-stu-id="b14b6-106">Parameters</span></span>

<span data-ttu-id="b14b6-107">_lpMAPISup_: [in] 此指针指向此会话的 MAPI 的回调函数的传输提供程序的支持对象。</span><span class="sxs-lookup"><span data-stu-id="b14b6-107">_lpMAPISup_: [in] Pointer to the transport provider's support object for callback functions within MAPI for this session.</span></span> <span data-ttu-id="b14b6-108">此对象保持有效，直到传输提供程序将其发布。</span><span class="sxs-lookup"><span data-stu-id="b14b6-108">This object remains valid until the transport provider releases it.</span></span>
    
<span data-ttu-id="b14b6-109">_ulUIParam_: [in] 任何对话框的父窗口或该方法显示的窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="b14b6-109">_ulUIParam_: [in] Handle to the parent window of any dialog boxes or windows this method displays.</span></span> <span data-ttu-id="b14b6-110">_UlUIParam_参数可以是非空，例如当 LOGON_SETUP 标记_lpulFlags_参数中设置。</span><span class="sxs-lookup"><span data-stu-id="b14b6-110">The  _ulUIParam_ parameter can be non-null, for example when the LOGON_SETUP flag is set in the  _lpulFlags_ parameter.</span></span> 
    
<span data-ttu-id="b14b6-111">_lpszProfileName_: [in] 此指针指向用户的配置文件名称。</span><span class="sxs-lookup"><span data-stu-id="b14b6-111">_lpszProfileName_: [in] Pointer to the profile name of the user.</span></span> <span data-ttu-id="b14b6-112">主要时必须显示一个对话框，才能使用_lpszProfileName_参数。</span><span class="sxs-lookup"><span data-stu-id="b14b6-112">The  _lpszProfileName_ parameter is primarily used when a dialog box must be presented.</span></span> 
    
<span data-ttu-id="b14b6-113">_lpulFlags_: [中，out] 控制如何建立登录会话的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="b14b6-113">_lpulFlags_: [in, out] Bitmask of flags that controls how the logon session is established.</span></span> <span data-ttu-id="b14b6-114">通过 MAPI 后台处理程序，可以输入上设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="b14b6-114">The following flags can be set on input by the MAPI spooler:</span></span>
    
  - <span data-ttu-id="b14b6-115">LOGON_NO_CONNECT： 的用户帐户登录到此传输提供程序之外的传输和接收的消息的目的。</span><span class="sxs-lookup"><span data-stu-id="b14b6-115">LOGON_NO_CONNECT: The user account is logging on to this transport provider for purposes other than transmission and reception of messages.</span></span> <span data-ttu-id="b14b6-116">传输提供程序不应尝试进行任何连接到其他邮件系统。</span><span class="sxs-lookup"><span data-stu-id="b14b6-116">The transport provider should not attempt to make any connections to other messaging systems.</span></span>
        
  - <span data-ttu-id="b14b6-117">LOGON_NO_DIALOG： 应不显示任何对话框，即使当前已保存的用户凭据无效或不足进行登录。</span><span class="sxs-lookup"><span data-stu-id="b14b6-117">LOGON_NO_DIALOG: No dialog box should be displayed even if the currently saved user credentials are invalid or insufficient for logon.</span></span>
        
  - <span data-ttu-id="b14b6-118">LOGON_NO_INBOUND： 传输提供程序没有初始化接收的消息，并且不应接受传入消息。</span><span class="sxs-lookup"><span data-stu-id="b14b6-118">LOGON_NO_INBOUND: The transport provider does not have to initialize for reception of messages and should not accept incoming messages.</span></span> <span data-ttu-id="b14b6-119">MAPI 后台处理程序可用于[IXPLogon::TransportNotify](ixplogon-transportnotify.md)方法更高版本信号传输提供程序来启用传入邮件处理。</span><span class="sxs-lookup"><span data-stu-id="b14b6-119">The MAPI spooler can use the [IXPLogon::TransportNotify](ixplogon-transportnotify.md) method later to signal the transport provider to enable incoming message processing.</span></span> 
        
  - <span data-ttu-id="b14b6-120">LOGON_NO_OUTBOUND： 传输提供程序没有初始化发送邮件，如 MAPI 后台处理程序不提供任何。</span><span class="sxs-lookup"><span data-stu-id="b14b6-120">LOGON_NO_OUTBOUND: The transport provider does not have to initialize for sending messages, as the MAPI spooler does not provide any.</span></span> <span data-ttu-id="b14b6-121">如果客户端应用程序需要期间一条消息构成的连接到远程提供程序，以便它可以进行[IXPLogon::AddressTypes](ixplogon-addresstypes.md)方法调用，传输提供程序应进行连接。</span><span class="sxs-lookup"><span data-stu-id="b14b6-121">If a client application requires a connection to a remote provider during the composition of a message so that it can make [IXPLogon::AddressTypes](ixplogon-addresstypes.md) method calls, the transport provider should make the connection.</span></span> <span data-ttu-id="b14b6-122">MAPI 后台处理程序可以使用**TransportNotify**时传出操作可以开始信号传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="b14b6-122">The MAPI spooler can use **TransportNotify** to signal the transport provider when outgoing operations can begin.</span></span> 
      
  - <span data-ttu-id="b14b6-123">MAPI_UNICODE： 配置文件名称的传入的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="b14b6-123">MAPI_UNICODE: The passed-in string for the profile name is in Unicode format.</span></span> <span data-ttu-id="b14b6-124">如果 MAPI\_未设置 UNICODE 标志、 字符串是 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="b14b6-124">If the MAPI\_UNICODE flag is not set, the string is in ANSI format.</span></span>
      
    <span data-ttu-id="b14b6-125">以下标志可以由传输提供程序设置输出：</span><span class="sxs-lookup"><span data-stu-id="b14b6-125">The following flags can be set on output by the transport provider:</span></span>
      
  - <span data-ttu-id="b14b6-126">LOGON_SP_IDLE: MAPI 后台处理程序经常空闲时间处理的呼叫传输提供程序的[IXPLogon::Idle](ixplogon-idle.md)方法请求。</span><span class="sxs-lookup"><span data-stu-id="b14b6-126">LOGON_SP_IDLE: Requests that the MAPI spooler frequently call the transport provider's [IXPLogon::Idle](ixplogon-idle.md) method for idle-time processing.</span></span> 
      
  - <span data-ttu-id="b14b6-127">MAPI 后台处理程序经常[IXPLogon::Poll](ixplogon-poll.md)对对象调用方法返回的登录检查新邮件的 LOGON_SP_POLL： 请求。</span><span class="sxs-lookup"><span data-stu-id="b14b6-127">LOGON_SP_POLL: Requests that the MAPI spooler frequently call the [IXPLogon::Poll](ixplogon-poll.md) method on the returned logon object to check for new messages.</span></span> <span data-ttu-id="b14b6-128">如果未设置此标志，MAPI 后台处理程序只检查新邮件时传输提供程序将使用[IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md)方法来通知后台处理程序要处理的新邮件。</span><span class="sxs-lookup"><span data-stu-id="b14b6-128">If this flag is not set, the MAPI spooler only checks for new messages when the transport provider uses the [IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md) method to notify the spooler that there are new messages to process.</span></span> <span data-ttu-id="b14b6-129">传输提供程序有效地将成为仅发送通过不设置此标志并不通知邮件回执 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="b14b6-129">A transport provider effectively becomes send-only by not setting this flag and by not notifying the MAPI spooler of message receipt.</span></span> 
      
  - <span data-ttu-id="b14b6-130">LOGON_SP_RESOLVE: MAPI 后台处理程序解析为的请求完全本传输提供程序不支持所有收件人的邮件地址的地址。</span><span class="sxs-lookup"><span data-stu-id="b14b6-130">LOGON_SP_RESOLVE: Requests that the MAPI spooler resolve to full addresses all message addresses for recipients not supported by this transport provider.</span></span> <span data-ttu-id="b14b6-131">因此传输提供程序，可以构造的所有收件人的答复路径。</span><span class="sxs-lookup"><span data-stu-id="b14b6-131">Therefore that the transport provider can construct a reply path for all recipients.</span></span>
      
  - <span data-ttu-id="b14b6-132">MAPI_UNICODE： 返回的字符串在[MAPIERROR](mapierror.md)结构中，如果有，采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="b14b6-132">MAPI_UNICODE: The returned strings in the [MAPIERROR](mapierror.md) structure, if any, are in Unicode format.</span></span> <span data-ttu-id="b14b6-133">如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="b14b6-133">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span> 
    
<span data-ttu-id="b14b6-134">_lppMAPIError_: [输出] 指向返回**MAPIERROR**结构的指针的指针，如果有，包含用于错误的版本、 组件及上下文信息。</span><span class="sxs-lookup"><span data-stu-id="b14b6-134">_lppMAPIError_: [out] Pointer to a pointer to the returned **MAPIERROR** structure, if any, that contains version, component, and context information for the error.</span></span> <span data-ttu-id="b14b6-135">如果不没有返回任何**MAPIERROR**结构， _lppMAPIError_参数可以设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="b14b6-135">The  _lppMAPIError_ parameter can be set to NULL if there is no **MAPIERROR** structure to return.</span></span> 
    
<span data-ttu-id="b14b6-136">_lppXPLogon_: [输出] 指向返回的传输提供程序登录对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="b14b6-136">_lppXPLogon_: [out] Pointer to the pointer to the returned transport provider logon object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="b14b6-137">返回值</span><span class="sxs-lookup"><span data-stu-id="b14b6-137">Return value</span></span>

<span data-ttu-id="b14b6-138">S_OK： 呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="b14b6-138">S_OK: The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="b14b6-139">MAPI_E_FAILONEPROVIDER： 此提供程序不能登录，但不是服务应禁用此错误。</span><span class="sxs-lookup"><span data-stu-id="b14b6-139">MAPI_E_FAILONEPROVIDER: This provider cannot log on, but this error should not disable the service.</span></span> 
    
<span data-ttu-id="b14b6-140">MAPI_E_UNCONFIGURED: 配置文件不包含为登录完成足够的信息。</span><span class="sxs-lookup"><span data-stu-id="b14b6-140">MAPI_E_UNCONFIGURED: The profile does not contain enough information for the logon to be completed.</span></span> <span data-ttu-id="b14b6-141">MAPI 调用的提供程序的消息服务入口点函数。</span><span class="sxs-lookup"><span data-stu-id="b14b6-141">MAPI calls the provider's message service entry point function.</span></span>
    
<span data-ttu-id="b14b6-142">MAPI_E_UNKNOWN_CPID： 提供程序无法支持客户端的代码页。</span><span class="sxs-lookup"><span data-stu-id="b14b6-142">MAPI_E_UNKNOWN_CPID: The provider cannot support the client's code page.</span></span>
    
<span data-ttu-id="b14b6-143">MAPI_E_UNKNOWN_LCID： 提供程序无法支持客户端的区域设置信息。</span><span class="sxs-lookup"><span data-stu-id="b14b6-143">MAPI_E_UNKNOWN_LCID: The provider cannot support the client's locale information.</span></span>
    
<span data-ttu-id="b14b6-144">MAPI_E_USER_CANCEL: 用户已取消该操作，通常通过单击对话框中的**取消**按钮。</span><span class="sxs-lookup"><span data-stu-id="b14b6-144">MAPI_E_USER_CANCEL: The user canceled the operation, typically by clicking the **Cancel** button in a dialog box.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="b14b6-145">注解</span><span class="sxs-lookup"><span data-stu-id="b14b6-145">Remarks</span></span>

<span data-ttu-id="b14b6-146">MAPI 后台处理程序调用**IXPProvider::TransportLogon**方法建立登录会话的用户。</span><span class="sxs-lookup"><span data-stu-id="b14b6-146">The MAPI spooler calls the **IXPProvider::TransportLogon** method to establish a logon session for a user.</span></span> 
  
<span data-ttu-id="b14b6-147">大多数传输提供程序使用[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)方法提供指向用于保存和检索用户标识信息、 服务器地址和凭据_lpMAPISup_参数的支持对象。</span><span class="sxs-lookup"><span data-stu-id="b14b6-147">Most transport providers use the [IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md) method provided with the support object pointed to by the  _lpMAPISup_ parameter for saving and retrieving user identity information, server addresses, and credentials.</span></span> <span data-ttu-id="b14b6-148">通过使用**OpenProfileSection**，传输提供程序可以保存任意信息并将其与登录到特定的资源关联。</span><span class="sxs-lookup"><span data-stu-id="b14b6-148">By using **OpenProfileSection**, a transport provider can save arbitrary information and associate it with a logon to a particular resource.</span></span> <span data-ttu-id="b14b6-149">例如，提供程序可以使用**OpenProfileSection**保存的帐户名和密码与特定会话和任何服务器的名称或其他必要的信息，该会话所需访问的资源关联。</span><span class="sxs-lookup"><span data-stu-id="b14b6-149">For example, a provider can use **OpenProfileSection** to save the account name and password associated with a particular session and any server names or other necessary information that are required to access resources for that session.</span></span> <span data-ttu-id="b14b6-150">MAPI 隐藏信息与从外部访问的资源关联。</span><span class="sxs-lookup"><span data-stu-id="b14b6-150">MAPI hides information associated with a resource from outside access.</span></span> <span data-ttu-id="b14b6-151">可通过_lpMAPISup_配置文件部分管理 MAPI 后台打印程序以便与此用户上下文相关的数据分开的其他上下文数据。</span><span class="sxs-lookup"><span data-stu-id="b14b6-151">The profile section made available through  _lpMAPISup_ is managed by the MAPI spooler so data related to this user context is separated from data for other contexts.</span></span> 
  
<span data-ttu-id="b14b6-152">传输提供程序必须支持对象上调用**IUnknown::AddRef**方法，并对该对象保留一份指针，提供登录对象的一部分。</span><span class="sxs-lookup"><span data-stu-id="b14b6-152">The transport provider must call the **IUnknown::AddRef** method on the support object and keep a copy of the pointer to this object as part of the provider logon object.</span></span> 
  
<span data-ttu-id="b14b6-153">以便传输提供程序可以使用它在错误消息或登录对话框提供_lpszProfileName_的配置文件显示名称。</span><span class="sxs-lookup"><span data-stu-id="b14b6-153">The profile display name in  _lpszProfileName_ is provided so the transport provider can use it in error messages or logon dialog boxes.</span></span> <span data-ttu-id="b14b6-154">如果提供程序保留此名称，必须将它复制到存储分配服务提供商。</span><span class="sxs-lookup"><span data-stu-id="b14b6-154">If the provider retains this name, it must be copied to storage allocated by the provider.</span></span> 
  
<span data-ttu-id="b14b6-155">与其他服务提供程序紧密耦合的传输提供程序可能需要执行其他工作登录建立助理提供程序之间的操作所需的良好凭据。</span><span class="sxs-lookup"><span data-stu-id="b14b6-155">Transport providers that are tightly coupled with other service providers may have to do additional work at logon to establish the good credentials required for operations between companion providers.</span></span>
  
<span data-ttu-id="b14b6-156">通常，当用户首次登录到配置文件打开传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="b14b6-156">Usually, transport providers are opened when the user first logs on to a profile.</span></span> <span data-ttu-id="b14b6-157">由于首次登录到配置文件因此通常位于之前登录到任何消息存储库，MAPI 后台处理程序通常与_lpulFlags_中设置的 LOGON_NO_INBOUND 和 LOGON_NO_OUTBOUND 标志调用**TransportLogon** 。</span><span class="sxs-lookup"><span data-stu-id="b14b6-157">Because the first logon to a profile therefore generally comes before logon to any message store, the MAPI spooler usually calls **TransportLogon** with both the LOGON_NO_INBOUND and LOGON_NO_OUTBOUND flags set in  _lpulFlags_.</span></span> <span data-ttu-id="b14b6-158">更高版本，可用于配置文件会话的相应的消息存储后，MAPI 后台处理程序调用**TransportNotify**启动传输提供程序的传入和传出操作。</span><span class="sxs-lookup"><span data-stu-id="b14b6-158">Later, when the appropriate message stores are available in the profile session, the MAPI spooler calls **TransportNotify** to initiate incoming and outgoing operations for the transport provider.</span></span> 
  
<span data-ttu-id="b14b6-159">传递中_lpulFlags_信号的 LOGON_NO_CONNECT 标志脱机操作的传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="b14b6-159">Passing the LOGON_NO_CONNECT flag in  _lpulFlags_ signals offline operation of the transport provider.</span></span> <span data-ttu-id="b14b6-160">此标志指示应将没有外部连接;如果传输提供程序无法建立一个会话外部连接的情况下，则应返回错误值进行登录。</span><span class="sxs-lookup"><span data-stu-id="b14b6-160">This flag indicates no external connections should be made; if the transport provider cannot establish a session without an external connection, it should return an error value for the logon.</span></span> 
  
<span data-ttu-id="b14b6-161">传输提供程序应中设置了 LOGON_SP_IDLE 标志_lpulFlags_在初始化时如果它旨在使用否则为系统等待的时间空闲。</span><span class="sxs-lookup"><span data-stu-id="b14b6-161">A transport provider should set the LOGON_SP_IDLE flag in  _lpulFlags_ at initialization time if it is designed to use time that the system otherwise spends idle.</span></span> <span data-ttu-id="b14b6-162">此类时常用来处理自动操作，如自动邮件下载，超时消息下载，或超时消息提交。</span><span class="sxs-lookup"><span data-stu-id="b14b6-162">Such time is often used to handle automatic operations, such as automatic message downloading, timed message downloading, or timed message submission.</span></span> <span data-ttu-id="b14b6-163">如果设置此标志，系统空闲时间发生启动这些操作时，MAPI 后台处理程序调用**空闲**。</span><span class="sxs-lookup"><span data-stu-id="b14b6-163">If this flag is set, the MAPI spooler calls **Idle** when system idle time occurs to initiate such operations.</span></span> <span data-ttu-id="b14b6-164">MAPI 后台处理程序以设置的间隔; 不调用**空闲**相反，它仅在过程中调用，则返回 true 的空闲时间。</span><span class="sxs-lookup"><span data-stu-id="b14b6-164">The MAPI spooler does not call **Idle** at set intervals; rather, it is called only during true idle time.</span></span> <span data-ttu-id="b14b6-165">因此，将调用其**空闲**方法的频率任何假设不应处理提供程序。</span><span class="sxs-lookup"><span data-stu-id="b14b6-165">Therefore, providers should not work on any assumption about how frequently their **Idle** methods will be called.</span></span> <span data-ttu-id="b14b6-166">提供程序支持空闲时间操作应为其提供其提供程序的属性表中的配置用户界面。</span><span class="sxs-lookup"><span data-stu-id="b14b6-166">Providers that support idle-time operations should supply a configuration user interface for it in their provider property sheet.</span></span> 
  
<span data-ttu-id="b14b6-167">如果成功传输提供程序登录，提供程序应返回_lppXPLogon_参数中的指针对登录对象。</span><span class="sxs-lookup"><span data-stu-id="b14b6-167">If the transport provider logon succeeds, the provider should return in the  _lppXPLogon_ parameter a pointer to a logon object.</span></span> <span data-ttu-id="b14b6-168">MAPI 后台处理程序将使用其他提供程序访问此对象。</span><span class="sxs-lookup"><span data-stu-id="b14b6-168">The MAPI spooler will use this object for additional provider access.</span></span> <span data-ttu-id="b14b6-169">如果**TransportLogon**显示一个登录对话框，用户取消登录通常通过单击对话框中的**取消**按钮提供程序应返回 MAPI_E_USER_CANCEL。</span><span class="sxs-lookup"><span data-stu-id="b14b6-169">If **TransportLogon** displays a logon dialog box and the user cancels logon typically by clicking the **Cancel** button in the dialog box the provider should return MAPI_E_USER_CANCEL.</span></span> 
  
<span data-ttu-id="b14b6-170">对于大多数**TransportLogon**从返回的错误值，MAPI 禁用提供程序所属的消息服务。</span><span class="sxs-lookup"><span data-stu-id="b14b6-170">For most error values returned from **TransportLogon**, MAPI disables the message services to which the provider belongs.</span></span> <span data-ttu-id="b14b6-171">MAPI 将不会调用属于该 MAPI 会话的 rest 服务的任何提供程序。</span><span class="sxs-lookup"><span data-stu-id="b14b6-171">MAPI will not call any providers that belong to that service for the rest of the MAPI session.</span></span> <span data-ttu-id="b14b6-172">相比之下，当**TransportLogon**返回 MAPI_E_FAILONEPROVIDER 错误值从其登录时，MAPI 不禁用邮件服务提供程序所属。</span><span class="sxs-lookup"><span data-stu-id="b14b6-172">In contrast, when **TransportLogon** returns the MAPI_E_FAILONEPROVIDER error value from its logon, MAPI does not disable the message service to which the provider belongs.</span></span> <span data-ttu-id="b14b6-173">如果遇到错误，不保证禁用会话的 rest 服务， **TransportLogon**应返回 MAPI_E_FAILONEPROVIDER。</span><span class="sxs-lookup"><span data-stu-id="b14b6-173">**TransportLogon** should return MAPI_E_FAILONEPROVIDER if it encounters an error that does not warrant disabling the service for the rest of the session.</span></span> 
  
<span data-ttu-id="b14b6-174">如果提供程序返回 MAPI_E_UNCONFIGURED 从其登录，MAPI 将调用提供程序的消息服务条目函数，然后重试登录。</span><span class="sxs-lookup"><span data-stu-id="b14b6-174">If a provider returns MAPI_E_UNCONFIGURED from its logon, MAPI will call the provider's message service entry function and then retry the logon.</span></span> <span data-ttu-id="b14b6-175">MAPI 将作为上下文，以使该服务配置本身有机会传递 MSG_SERVICE_CONFIGURE。</span><span class="sxs-lookup"><span data-stu-id="b14b6-175">MAPI passes MSG_SERVICE_CONFIGURE as the context, to give the service a chance to configure itself.</span></span> <span data-ttu-id="b14b6-176">如果客户端已经选择允许在登录的用户界面，该服务可以将其配置属性表，，以便用户可以输入配置信息。</span><span class="sxs-lookup"><span data-stu-id="b14b6-176">If the client has chosen to allow a user interface on the logon, the service can present its configuration property sheet so that the user can enter configuration information.</span></span> 
  
<span data-ttu-id="b14b6-177">如果提供程序查找所有所需的信息不在配置文件中，则应返回 MAPI_E_UNCONFIGURED，以便 MAPI 调用的提供程序的消息服务入口点函数。</span><span class="sxs-lookup"><span data-stu-id="b14b6-177">If the provider finds that all the required information is not in the profile, it should return MAPI_E_UNCONFIGURED so that MAPI calls the provider's message service entry point function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="b14b6-178">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b14b6-178">See also</span></span>

- [<span data-ttu-id="b14b6-179">IXPProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="b14b6-179">IXPProvider : IUnknown</span></span>](ixpprovideriunknown.md)  
- [<span data-ttu-id="b14b6-180">IMAPISupport::OpenProfileSection</span><span class="sxs-lookup"><span data-stu-id="b14b6-180">IMAPISupport::OpenProfileSection</span></span>](imapisupport-openprofilesection.md)  
- [<span data-ttu-id="b14b6-181">IMAPISupport::SpoolerNotify</span><span class="sxs-lookup"><span data-stu-id="b14b6-181">IMAPISupport::SpoolerNotify</span></span>](imapisupport-spoolernotify.md)  
- [<span data-ttu-id="b14b6-182">IXPLogon::AddressTypes</span><span class="sxs-lookup"><span data-stu-id="b14b6-182">IXPLogon::AddressTypes</span></span>](ixplogon-addresstypes.md)  
- [<span data-ttu-id="b14b6-183">IXPLogon::Idle</span><span class="sxs-lookup"><span data-stu-id="b14b6-183">IXPLogon::Idle</span></span>](ixplogon-idle.md)  
- [<span data-ttu-id="b14b6-184">IXPLogon::Poll</span><span class="sxs-lookup"><span data-stu-id="b14b6-184">IXPLogon::Poll</span></span>](ixplogon-poll.md)  
- [<span data-ttu-id="b14b6-185">IXPLogon::TransportNotify</span><span class="sxs-lookup"><span data-stu-id="b14b6-185">IXPLogon::TransportNotify</span></span>](ixplogon-transportnotify.md) 
- [<span data-ttu-id="b14b6-186">MAPIERROR</span><span class="sxs-lookup"><span data-stu-id="b14b6-186">MAPIERROR</span></span>](mapierror.md)

