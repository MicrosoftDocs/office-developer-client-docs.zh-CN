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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 53b2733dbf38d680027dc00ecf5513f384e46660
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417306"
---
# <a name="ixpprovidertransportlogon"></a><span data-ttu-id="2f82b-103">IXPProvider::TransportLogon</span><span class="sxs-lookup"><span data-stu-id="2f82b-103">IXPProvider::TransportLogon</span></span>

<span data-ttu-id="2f82b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2f82b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2f82b-105">建立一个会话, 客户端应用程序在该会话中登录到传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="2f82b-105">Establishes a session in which a client application logs on to a transport provider.</span></span> 
  
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

## <a name="parameters"></a><span data-ttu-id="2f82b-106">参数</span><span class="sxs-lookup"><span data-stu-id="2f82b-106">Parameters</span></span>

<span data-ttu-id="2f82b-107">_lpMAPISup_: [in] 指向针对此会话的 MAPI 中的回调函数的传输提供程序的支持对象的指针。</span><span class="sxs-lookup"><span data-stu-id="2f82b-107">_lpMAPISup_: [in] Pointer to the transport provider's support object for callback functions within MAPI for this session.</span></span> <span data-ttu-id="2f82b-108">在传输提供程序释放此对象之前, 此对象一直保持有效。</span><span class="sxs-lookup"><span data-stu-id="2f82b-108">This object remains valid until the transport provider releases it.</span></span>
    
<span data-ttu-id="2f82b-109">_ulUIParam_: [in] 处理此方法显示的任何对话框或窗口的父窗口。</span><span class="sxs-lookup"><span data-stu-id="2f82b-109">_ulUIParam_: [in] Handle to the parent window of any dialog boxes or windows this method displays.</span></span> <span data-ttu-id="2f82b-110">_ulUIParam_参数可以为非 null, 例如, 在_lpulFlags_参数中设置 LOGON_SETUP 标志时。</span><span class="sxs-lookup"><span data-stu-id="2f82b-110">The  _ulUIParam_ parameter can be non-null, for example when the LOGON_SETUP flag is set in the  _lpulFlags_ parameter.</span></span> 
    
<span data-ttu-id="2f82b-111">_lpszProfileName_: [in] 指针指向用户的配置文件名称。</span><span class="sxs-lookup"><span data-stu-id="2f82b-111">_lpszProfileName_: [in] Pointer to the profile name of the user.</span></span> <span data-ttu-id="2f82b-112">_lpszProfileName_参数主要在必须显示对话框时使用。</span><span class="sxs-lookup"><span data-stu-id="2f82b-112">The  _lpszProfileName_ parameter is primarily used when a dialog box must be presented.</span></span> 
    
<span data-ttu-id="2f82b-113">_lpulFlags_: [in, out] 用于控制如何建立登录会话的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="2f82b-113">_lpulFlags_: [in, out] Bitmask of flags that controls how the logon session is established.</span></span> <span data-ttu-id="2f82b-114">MAPI 后台处理程序可对输入设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="2f82b-114">The following flags can be set on input by the MAPI spooler:</span></span>
    
  - <span data-ttu-id="2f82b-115">LOGON_NO_CONNECT: 用户帐户出于邮件传输和接收之外的目的登录到此传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="2f82b-115">LOGON_NO_CONNECT: The user account is logging on to this transport provider for purposes other than transmission and reception of messages.</span></span> <span data-ttu-id="2f82b-116">传输提供程序不应尝试对其他邮件系统进行任何连接。</span><span class="sxs-lookup"><span data-stu-id="2f82b-116">The transport provider should not attempt to make any connections to other messaging systems.</span></span>
        
  - <span data-ttu-id="2f82b-117">LOGON_NO_DIALOG: 即使当前保存的用户凭据无效或不足以登录, 也不应显示任何对话框。</span><span class="sxs-lookup"><span data-stu-id="2f82b-117">LOGON_NO_DIALOG: No dialog box should be displayed even if the currently saved user credentials are invalid or insufficient for logon.</span></span>
        
  - <span data-ttu-id="2f82b-118">LOGON_NO_INBOUND: 传输提供程序无需为接收邮件进行初始化, 也不应接受传入的邮件。</span><span class="sxs-lookup"><span data-stu-id="2f82b-118">LOGON_NO_INBOUND: The transport provider does not have to initialize for reception of messages and should not accept incoming messages.</span></span> <span data-ttu-id="2f82b-119">MAPI 后台处理程序可以稍后使用[IXPLogon:: TransportNotify](ixplogon-transportnotify.md)方法向传输提供程序发出信号, 以启用传入邮件处理。</span><span class="sxs-lookup"><span data-stu-id="2f82b-119">The MAPI spooler can use the [IXPLogon::TransportNotify](ixplogon-transportnotify.md) method later to signal the transport provider to enable incoming message processing.</span></span> 
        
  - <span data-ttu-id="2f82b-120">LOGON_NO_OUTBOUND: 传输提供程序无需对发送邮件进行初始化, 因为 MAPI 后台处理程序不会提供任何。</span><span class="sxs-lookup"><span data-stu-id="2f82b-120">LOGON_NO_OUTBOUND: The transport provider does not have to initialize for sending messages, as the MAPI spooler does not provide any.</span></span> <span data-ttu-id="2f82b-121">如果客户端应用程序要求在消息的撰写过程中连接到远程提供程序, 以便它可以发出[IXPLogon:: AddressTypes](ixplogon-addresstypes.md)方法调用, 则传输提供程序应进行连接。</span><span class="sxs-lookup"><span data-stu-id="2f82b-121">If a client application requires a connection to a remote provider during the composition of a message so that it can make [IXPLogon::AddressTypes](ixplogon-addresstypes.md) method calls, the transport provider should make the connection.</span></span> <span data-ttu-id="2f82b-122">MAPI 后台处理程序可以使用**TransportNotify**在传出操作开始时向传输提供程序发出信号。</span><span class="sxs-lookup"><span data-stu-id="2f82b-122">The MAPI spooler can use **TransportNotify** to signal the transport provider when outgoing operations can begin.</span></span> 
      
  - <span data-ttu-id="2f82b-123">MAPI_UNICODE: 配置文件名称的传入字符串采用 UNICODE 格式。</span><span class="sxs-lookup"><span data-stu-id="2f82b-123">MAPI_UNICODE: The passed-in string for the profile name is in Unicode format.</span></span> <span data-ttu-id="2f82b-124">如果未设置\_MAPI UNICODE 标志, 则字符串将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="2f82b-124">If the MAPI\_UNICODE flag is not set, the string is in ANSI format.</span></span>
      
    <span data-ttu-id="2f82b-125">传输提供程序可对输出设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="2f82b-125">The following flags can be set on output by the transport provider:</span></span>
      
  - <span data-ttu-id="2f82b-126">LOGON_SP_IDLE: 请求 MAPI 后台处理程序频繁调用传输提供程序的[IXPLogon::](ixplogon-idle.md) idle-time 处理的空闲方法。</span><span class="sxs-lookup"><span data-stu-id="2f82b-126">LOGON_SP_IDLE: Requests that the MAPI spooler frequently call the transport provider's [IXPLogon::Idle](ixplogon-idle.md) method for idle-time processing.</span></span> 
      
  - <span data-ttu-id="2f82b-127">LOGON_SP_POLL: 请求 MAPI 后台处理程序经常对返回的登录对象调用[IXPLogon::P oll](ixplogon-poll.md)方法, 以检查是否有新邮件。</span><span class="sxs-lookup"><span data-stu-id="2f82b-127">LOGON_SP_POLL: Requests that the MAPI spooler frequently call the [IXPLogon::Poll](ixplogon-poll.md) method on the returned logon object to check for new messages.</span></span> <span data-ttu-id="2f82b-128">如果未设置此标志, 则 MAPI 后台处理程序仅在传输提供程序使用[IMAPISupport:: SpoolerNotify](imapisupport-spoolernotify.md)方法时检查新邮件, 以通知后台打印程序有要处理的新邮件。</span><span class="sxs-lookup"><span data-stu-id="2f82b-128">If this flag is not set, the MAPI spooler only checks for new messages when the transport provider uses the [IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md) method to notify the spooler that there are new messages to process.</span></span> <span data-ttu-id="2f82b-129">通过不设置此标志, 传输提供程序将有效地变为仅发送, 而不会通知邮件接收的 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="2f82b-129">A transport provider effectively becomes send-only by not setting this flag and by not notifying the MAPI spooler of message receipt.</span></span> 
      
  - <span data-ttu-id="2f82b-130">LOGON_SP_RESOLVE: 请求 MAPI 后台处理程序解析为完整地址此传输提供程序不支持的所有收件人的邮件地址。</span><span class="sxs-lookup"><span data-stu-id="2f82b-130">LOGON_SP_RESOLVE: Requests that the MAPI spooler resolve to full addresses all message addresses for recipients not supported by this transport provider.</span></span> <span data-ttu-id="2f82b-131">因此, 传输提供程序可以为所有收件人构造答复路径。</span><span class="sxs-lookup"><span data-stu-id="2f82b-131">Therefore that the transport provider can construct a reply path for all recipients.</span></span>
      
  - <span data-ttu-id="2f82b-132">MAPI_UNICODE: [MAPIERROR](mapierror.md)结构中返回的字符串 (如果有) 采用 UNICODE 格式。</span><span class="sxs-lookup"><span data-stu-id="2f82b-132">MAPI_UNICODE: The returned strings in the [MAPIERROR](mapierror.md) structure, if any, are in Unicode format.</span></span> <span data-ttu-id="2f82b-133">如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="2f82b-133">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span> 
    
<span data-ttu-id="2f82b-134">_lppMAPIError_: [out] 指向指向返回的**MAPIERROR**结构的指针的指针 (如果有), 其中包含错误的版本、组件和上下文信息。</span><span class="sxs-lookup"><span data-stu-id="2f82b-134">_lppMAPIError_: [out] Pointer to a pointer to the returned **MAPIERROR** structure, if any, that contains version, component, and context information for the error.</span></span> <span data-ttu-id="2f82b-135">如果没有要返回的**MAPIERROR**结构, 则可以将_lppMAPIError_参数设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="2f82b-135">The  _lppMAPIError_ parameter can be set to NULL if there is no **MAPIERROR** structure to return.</span></span> 
    
<span data-ttu-id="2f82b-136">_lppXPLogon_: [out] 指向返回的传输提供程序登录对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="2f82b-136">_lppXPLogon_: [out] Pointer to the pointer to the returned transport provider logon object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="2f82b-137">返回值</span><span class="sxs-lookup"><span data-stu-id="2f82b-137">Return value</span></span>

<span data-ttu-id="2f82b-138">S_OK: 调用成功, 并返回了所需的值。</span><span class="sxs-lookup"><span data-stu-id="2f82b-138">S_OK: The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="2f82b-139">MAPI_E_FAILONEPROVIDER: 此提供程序无法登录, 但此错误不应禁用该服务。</span><span class="sxs-lookup"><span data-stu-id="2f82b-139">MAPI_E_FAILONEPROVIDER: This provider cannot log on, but this error should not disable the service.</span></span> 
    
<span data-ttu-id="2f82b-140">MAPI_E_UNCONFIGURED: 配置文件不包含足够的信息, 无法完成登录。</span><span class="sxs-lookup"><span data-stu-id="2f82b-140">MAPI_E_UNCONFIGURED: The profile does not contain enough information for the logon to be completed.</span></span> <span data-ttu-id="2f82b-141">MAPI 调用提供程序的邮件服务入口点函数。</span><span class="sxs-lookup"><span data-stu-id="2f82b-141">MAPI calls the provider's message service entry point function.</span></span>
    
<span data-ttu-id="2f82b-142">MAPI_E_UNKNOWN_CPID: 提供程序无法支持客户端的代码页。</span><span class="sxs-lookup"><span data-stu-id="2f82b-142">MAPI_E_UNKNOWN_CPID: The provider cannot support the client's code page.</span></span>
    
<span data-ttu-id="2f82b-143">MAPI_E_UNKNOWN_LCID: 提供程序无法支持客户端的区域设置信息。</span><span class="sxs-lookup"><span data-stu-id="2f82b-143">MAPI_E_UNKNOWN_LCID: The provider cannot support the client's locale information.</span></span>
    
<span data-ttu-id="2f82b-144">MAPI_E_USER_CANCEL: 用户取消了操作, 通常是单击对话框中的 "**取消**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="2f82b-144">MAPI_E_USER_CANCEL: The user canceled the operation, typically by clicking the **Cancel** button in a dialog box.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="2f82b-145">说明</span><span class="sxs-lookup"><span data-stu-id="2f82b-145">Remarks</span></span>

<span data-ttu-id="2f82b-146">MAPI 后台处理程序调用**IXPProvider:: TransportLogon**方法为用户建立登录会话。</span><span class="sxs-lookup"><span data-stu-id="2f82b-146">The MAPI spooler calls the **IXPProvider::TransportLogon** method to establish a logon session for a user.</span></span> 
  
<span data-ttu-id="2f82b-147">大多数传输提供程序使用由_lpMAPISup_参数指向的支持对象所提供的[IMAPISupport:: OpenProfileSection](imapisupport-openprofilesection.md)方法, 以保存和检索用户标识信息、服务器地址和凭据。</span><span class="sxs-lookup"><span data-stu-id="2f82b-147">Most transport providers use the [IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md) method provided with the support object pointed to by the  _lpMAPISup_ parameter for saving and retrieving user identity information, server addresses, and credentials.</span></span> <span data-ttu-id="2f82b-148">通过使用**OpenProfileSection**, 传输提供程序可以保存任意信息, 并将其与登录到特定资源相关联。</span><span class="sxs-lookup"><span data-stu-id="2f82b-148">By using **OpenProfileSection**, a transport provider can save arbitrary information and associate it with a logon to a particular resource.</span></span> <span data-ttu-id="2f82b-149">例如, 提供程序可以使用**OpenProfileSection**保存与特定会话相关联的帐户名称和密码, 以及访问该会话的资源所需的任何服务器名称或其他必要信息。</span><span class="sxs-lookup"><span data-stu-id="2f82b-149">For example, a provider can use **OpenProfileSection** to save the account name and password associated with a particular session and any server names or other necessary information that are required to access resources for that session.</span></span> <span data-ttu-id="2f82b-150">MAPI 在外部访问中隐藏与资源相关联的信息。</span><span class="sxs-lookup"><span data-stu-id="2f82b-150">MAPI hides information associated with a resource from outside access.</span></span> <span data-ttu-id="2f82b-151">通过_lpMAPISup_提供的配置文件节由 MAPI 后台处理程序进行管理, 因此与此用户上下文相关的数据与其他上下文的数据分开。</span><span class="sxs-lookup"><span data-stu-id="2f82b-151">The profile section made available through  _lpMAPISup_ is managed by the MAPI spooler so data related to this user context is separated from data for other contexts.</span></span> 
  
<span data-ttu-id="2f82b-152">传输提供程序必须调用支持对象上的**IUnknown:: AddRef**方法, 并将指针的副本作为提供程序登录对象的一部分保留给此对象。</span><span class="sxs-lookup"><span data-stu-id="2f82b-152">The transport provider must call the **IUnknown::AddRef** method on the support object and keep a copy of the pointer to this object as part of the provider logon object.</span></span> 
  
<span data-ttu-id="2f82b-153">提供_lpszProfileName_中的配置文件显示名称, 以便传输提供程序可以在错误消息或登录对话框中使用它。</span><span class="sxs-lookup"><span data-stu-id="2f82b-153">The profile display name in  _lpszProfileName_ is provided so the transport provider can use it in error messages or logon dialog boxes.</span></span> <span data-ttu-id="2f82b-154">如果提供程序保留此名称, 则必须将其复制到提供程序分配的存储中。</span><span class="sxs-lookup"><span data-stu-id="2f82b-154">If the provider retains this name, it must be copied to storage allocated by the provider.</span></span> 
  
<span data-ttu-id="2f82b-155">与其他服务提供程序紧密结合的传输提供程序可能必须在登录时执行额外的工作, 才能建立配套提供程序之间的操作所需的正确凭据。</span><span class="sxs-lookup"><span data-stu-id="2f82b-155">Transport providers that are tightly coupled with other service providers may have to do additional work at logon to establish the good credentials required for operations between companion providers.</span></span>
  
<span data-ttu-id="2f82b-156">通常情况下, 当用户首次登录到配置文件时, 将打开传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="2f82b-156">Usually, transport providers are opened when the user first logs on to a profile.</span></span> <span data-ttu-id="2f82b-157">由于第一次登录到配置文件时通常会登录到任何邮件存储, 因此 MAPI 后台处理程序通常会同时在_lpulFlags_中设置的 LOGON_NO_INBOUND 和 LOGON_NO_OUTBOUND 标志调用**TransportLogon** 。</span><span class="sxs-lookup"><span data-stu-id="2f82b-157">Because the first logon to a profile therefore generally comes before logon to any message store, the MAPI spooler usually calls **TransportLogon** with both the LOGON_NO_INBOUND and LOGON_NO_OUTBOUND flags set in  _lpulFlags_.</span></span> <span data-ttu-id="2f82b-158">之后, 在配置文件会话中提供相应的邮件存储区时, MAPI 后台处理程序将调用**TransportNotify**以启动传输提供程序的传入和传出操作。</span><span class="sxs-lookup"><span data-stu-id="2f82b-158">Later, when the appropriate message stores are available in the profile session, the MAPI spooler calls **TransportNotify** to initiate incoming and outgoing operations for the transport provider.</span></span> 
  
<span data-ttu-id="2f82b-159">在_lpulFlags_中传递 LOGON_NO_CONNECT 标志以通知传输提供程序的脱机操作。</span><span class="sxs-lookup"><span data-stu-id="2f82b-159">Passing the LOGON_NO_CONNECT flag in  _lpulFlags_ signals offline operation of the transport provider.</span></span> <span data-ttu-id="2f82b-160">此标志指示不应进行外部连接;如果传输提供程序无法在没有外部连接的情况下建立会话, 它应返回登录的错误值。</span><span class="sxs-lookup"><span data-stu-id="2f82b-160">This flag indicates no external connections should be made; if the transport provider cannot establish a session without an external connection, it should return an error value for the logon.</span></span> 
  
<span data-ttu-id="2f82b-161">如果在_lpulFlags_中, 传输提供程序应在初始化时设置 LOGON_SP_IDLE 标志, 如果它设计为使用系统本来会处于空闲状态的时间。</span><span class="sxs-lookup"><span data-stu-id="2f82b-161">A transport provider should set the LOGON_SP_IDLE flag in  _lpulFlags_ at initialization time if it is designed to use time that the system otherwise spends idle.</span></span> <span data-ttu-id="2f82b-162">此类时间通常用于处理自动操作, 例如自动邮件下载、计时邮件下载或定时邮件提交。</span><span class="sxs-lookup"><span data-stu-id="2f82b-162">Such time is often used to handle automatic operations, such as automatic message downloading, timed message downloading, or timed message submission.</span></span> <span data-ttu-id="2f82b-163">如果设置了此标志, 则 MAPI 后台处理程序会在系统空闲时间启动此类操作时呼叫**空闲**。</span><span class="sxs-lookup"><span data-stu-id="2f82b-163">If this flag is set, the MAPI spooler calls **Idle** when system idle time occurs to initiate such operations.</span></span> <span data-ttu-id="2f82b-164">MAPI 后台处理程序不会在设置的时间间隔内呼叫**空闲**;而只是在真正的空闲时间内调用。</span><span class="sxs-lookup"><span data-stu-id="2f82b-164">The MAPI spooler does not call **Idle** at set intervals; rather, it is called only during true idle time.</span></span> <span data-ttu-id="2f82b-165">因此, 提供程序不应针对其**空闲**方法的调用频率的任何假设进行操作。</span><span class="sxs-lookup"><span data-stu-id="2f82b-165">Therefore, providers should not work on any assumption about how frequently their **Idle** methods will be called.</span></span> <span data-ttu-id="2f82b-166">支持空闲时间操作的提供程序应在其提供程序属性表中为其提供配置用户界面。</span><span class="sxs-lookup"><span data-stu-id="2f82b-166">Providers that support idle-time operations should supply a configuration user interface for it in their provider property sheet.</span></span> 
  
<span data-ttu-id="2f82b-167">如果传输提供程序登录成功, 则提供程序应在_lppXPLogon_参数中返回一个指向登录对象的指针。</span><span class="sxs-lookup"><span data-stu-id="2f82b-167">If the transport provider logon succeeds, the provider should return in the  _lppXPLogon_ parameter a pointer to a logon object.</span></span> <span data-ttu-id="2f82b-168">MAPI 后台处理程序将使用此对象以获取其他提供程序访问权限。</span><span class="sxs-lookup"><span data-stu-id="2f82b-168">The MAPI spooler will use this object for additional provider access.</span></span> <span data-ttu-id="2f82b-169">如果**TransportLogon**显示登录对话框, 并且用户通过单击对话框中的 "取消" 按钮 (该对话框中的 "**取消**" 按钮) 来取消登录, 则提供程序应返回 MAPI_E_USER_CANCEL。</span><span class="sxs-lookup"><span data-stu-id="2f82b-169">If **TransportLogon** displays a logon dialog box and the user cancels logon typically by clicking the **Cancel** button in the dialog box the provider should return MAPI_E_USER_CANCEL.</span></span> 
  
<span data-ttu-id="2f82b-170">对于从**TransportLogon**返回的大多数错误值, MAPI 将禁用该提供程序所属的邮件服务。</span><span class="sxs-lookup"><span data-stu-id="2f82b-170">For most error values returned from **TransportLogon**, MAPI disables the message services to which the provider belongs.</span></span> <span data-ttu-id="2f82b-171">mapi 将不会为 mapi 会话的其余部分调用任何属于该服务的提供程序。</span><span class="sxs-lookup"><span data-stu-id="2f82b-171">MAPI will not call any providers that belong to that service for the rest of the MAPI session.</span></span> <span data-ttu-id="2f82b-172">相比之下, 当**TransportLogon**从其登录中返回 MAPI_E_FAILONEPROVIDER 错误值时, MAPI 不会禁用该提供程序所属的邮件服务。</span><span class="sxs-lookup"><span data-stu-id="2f82b-172">In contrast, when **TransportLogon** returns the MAPI_E_FAILONEPROVIDER error value from its logon, MAPI does not disable the message service to which the provider belongs.</span></span> <span data-ttu-id="2f82b-173">如果遇到不保证在会话的其余部分禁用服务的错误, **TransportLogon**应返回 MAPI_E_FAILONEPROVIDER。</span><span class="sxs-lookup"><span data-stu-id="2f82b-173">**TransportLogon** should return MAPI_E_FAILONEPROVIDER if it encounters an error that does not warrant disabling the service for the rest of the session.</span></span> 
  
<span data-ttu-id="2f82b-174">如果提供程序从其登录返回 MAPI_E_UNCONFIGURED, 则 MAPI 将调用提供程序的邮件服务条目功能, 然后重试该登录。</span><span class="sxs-lookup"><span data-stu-id="2f82b-174">If a provider returns MAPI_E_UNCONFIGURED from its logon, MAPI will call the provider's message service entry function and then retry the logon.</span></span> <span data-ttu-id="2f82b-175">MAPI 将 MSG_SERVICE_CONFIGURE 作为上下文进行传递, 使服务有机会对自身进行配置。</span><span class="sxs-lookup"><span data-stu-id="2f82b-175">MAPI passes MSG_SERVICE_CONFIGURE as the context, to give the service a chance to configure itself.</span></span> <span data-ttu-id="2f82b-176">如果客户端已选择允许登录时使用用户界面, 则服务可以显示其配置属性表, 以便用户可以输入配置信息。</span><span class="sxs-lookup"><span data-stu-id="2f82b-176">If the client has chosen to allow a user interface on the logon, the service can present its configuration property sheet so that the user can enter configuration information.</span></span> 
  
<span data-ttu-id="2f82b-177">如果提供程序发现所有必需的信息都不在配置文件中, 则应返回 MAPI_E_UNCONFIGURED, 以便 MAPI 调用提供程序的邮件服务入口点函数。</span><span class="sxs-lookup"><span data-stu-id="2f82b-177">If the provider finds that all the required information is not in the profile, it should return MAPI_E_UNCONFIGURED so that MAPI calls the provider's message service entry point function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2f82b-178">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2f82b-178">See also</span></span>

- [<span data-ttu-id="2f82b-179">IXPProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="2f82b-179">IXPProvider : IUnknown</span></span>](ixpprovideriunknown.md)  
- [<span data-ttu-id="2f82b-180">IMAPISupport::OpenProfileSection</span><span class="sxs-lookup"><span data-stu-id="2f82b-180">IMAPISupport::OpenProfileSection</span></span>](imapisupport-openprofilesection.md)  
- [<span data-ttu-id="2f82b-181">IMAPISupport::SpoolerNotify</span><span class="sxs-lookup"><span data-stu-id="2f82b-181">IMAPISupport::SpoolerNotify</span></span>](imapisupport-spoolernotify.md)  
- [<span data-ttu-id="2f82b-182">IXPLogon::AddressTypes</span><span class="sxs-lookup"><span data-stu-id="2f82b-182">IXPLogon::AddressTypes</span></span>](ixplogon-addresstypes.md)  
- [<span data-ttu-id="2f82b-183">IXPLogon::Idle</span><span class="sxs-lookup"><span data-stu-id="2f82b-183">IXPLogon::Idle</span></span>](ixplogon-idle.md)  
- [<span data-ttu-id="2f82b-184">IXPLogon::Poll</span><span class="sxs-lookup"><span data-stu-id="2f82b-184">IXPLogon::Poll</span></span>](ixplogon-poll.md)  
- [<span data-ttu-id="2f82b-185">IXPLogon::TransportNotify</span><span class="sxs-lookup"><span data-stu-id="2f82b-185">IXPLogon::TransportNotify</span></span>](ixplogon-transportnotify.md) 
- [<span data-ttu-id="2f82b-186">MAPIERROR</span><span class="sxs-lookup"><span data-stu-id="2f82b-186">MAPIERROR</span></span>](mapierror.md)

