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
# <a name="ixpprovidertransportlogon"></a><span data-ttu-id="8e6c3-103">IXPProvider::TransportLogon</span><span class="sxs-lookup"><span data-stu-id="8e6c3-103">IXPProvider::TransportLogon</span></span>

<span data-ttu-id="8e6c3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8e6c3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8e6c3-105">建立客户端应用程序登录到传输提供程序的会话。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-105">Establishes a session in which a client application logs on to a transport provider.</span></span> 
  
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

## <a name="parameters"></a><span data-ttu-id="8e6c3-106">参数</span><span class="sxs-lookup"><span data-stu-id="8e6c3-106">Parameters</span></span>

<span data-ttu-id="8e6c3-107">_lpMAPISup_：[in] 指向传输提供程序对此会话的 MAPI 中回调函数的支持对象的指针。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-107">_lpMAPISup_: [in] Pointer to the transport provider's support object for callback functions within MAPI for this session.</span></span> <span data-ttu-id="8e6c3-108">在传输提供程序释放该对象之前，该对象一直有效。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-108">This object remains valid until the transport provider releases it.</span></span>
    
<span data-ttu-id="8e6c3-109">_ulUIParam_：[in] 此方法显示的任何对话框或窗口的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-109">_ulUIParam_: [in] Handle to the parent window of any dialog boxes or windows this method displays.</span></span> <span data-ttu-id="8e6c3-110">_ulUIParam_ 参数可以是非 null 参数，例如，当在 _lpulFlags_ 参数中设置 LOGON_SETUP 标志时。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-110">The  _ulUIParam_ parameter can be non-null, for example when the LOGON_SETUP flag is set in the  _lpulFlags_ parameter.</span></span> 
    
<span data-ttu-id="8e6c3-111">_lpszProfileName_：[in] 指向用户的配置文件名称的指针。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-111">_lpszProfileName_: [in] Pointer to the profile name of the user.</span></span> <span data-ttu-id="8e6c3-112">_lpszProfileName_ 参数主要用于必须显示对话框时。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-112">The  _lpszProfileName_ parameter is primarily used when a dialog box must be presented.</span></span> 
    
<span data-ttu-id="8e6c3-113">_lpulFlags_：[in， out] 控制如何建立登录会话的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-113">_lpulFlags_: [in, out] Bitmask of flags that controls how the logon session is established.</span></span> <span data-ttu-id="8e6c3-114">MAPI 后台处理程序可以在输入时设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="8e6c3-114">The following flags can be set on input by the MAPI spooler:</span></span>
    
  - <span data-ttu-id="8e6c3-115">LOGON_NO_CONNECT：除了传输和接收邮件外，用户帐户还登录到此传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-115">LOGON_NO_CONNECT: The user account is logging on to this transport provider for purposes other than transmission and reception of messages.</span></span> <span data-ttu-id="8e6c3-116">传输提供程序不应尝试建立与其他邮件系统的任何连接。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-116">The transport provider should not attempt to make any connections to other messaging systems.</span></span>
        
  - <span data-ttu-id="8e6c3-117">LOGON_NO_DIALOG：即使当前保存的用户凭据无效或无法登录，也不应显示任何对话框。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-117">LOGON_NO_DIALOG: No dialog box should be displayed even if the currently saved user credentials are invalid or insufficient for logon.</span></span>
        
  - <span data-ttu-id="8e6c3-118">LOGON_NO_INBOUND：传输提供程序无需初始化以接收邮件，并且不应接受传入的邮件。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-118">LOGON_NO_INBOUND: The transport provider does not have to initialize for reception of messages and should not accept incoming messages.</span></span> <span data-ttu-id="8e6c3-119">MAPI 后台处理程序稍后可以使用 [IXPLogon：：TransportNotify](ixplogon-transportnotify.md) 方法向传输提供程序发出信号，以启用传入邮件处理。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-119">The MAPI spooler can use the [IXPLogon::TransportNotify](ixplogon-transportnotify.md) method later to signal the transport provider to enable incoming message processing.</span></span> 
        
  - <span data-ttu-id="8e6c3-120">LOGON_NO_OUTBOUND：传输提供程序无需初始化以发送邮件，因为 MAPI 后台处理程序不提供任何内容。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-120">LOGON_NO_OUTBOUND: The transport provider does not have to initialize for sending messages, as the MAPI spooler does not provide any.</span></span> <span data-ttu-id="8e6c3-121">如果客户端应用程序需要在消息组合期间连接到远程提供程序，以便它可以进行 [IXPLogon：：AddressTypes](ixplogon-addresstypes.md) 方法调用，则传输提供程序应建立连接。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-121">If a client application requires a connection to a remote provider during the composition of a message so that it can make [IXPLogon::AddressTypes](ixplogon-addresstypes.md) method calls, the transport provider should make the connection.</span></span> <span data-ttu-id="8e6c3-122">MAPI 后台处理程序可以使用 **TransportNotify** 在传出操作开始时向传输提供程序发出信号。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-122">The MAPI spooler can use **TransportNotify** to signal the transport provider when outgoing operations can begin.</span></span> 
      
  - <span data-ttu-id="8e6c3-123">MAPI_UNICODE：配置文件名称的传入字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-123">MAPI_UNICODE: The passed-in string for the profile name is in Unicode format.</span></span> <span data-ttu-id="8e6c3-124">如果未设置 MAPI \_ UNICODE 标志，则字符串采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-124">If the MAPI\_UNICODE flag is not set, the string is in ANSI format.</span></span>
      
    <span data-ttu-id="8e6c3-125">传输提供程序可以在输出上设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="8e6c3-125">The following flags can be set on output by the transport provider:</span></span>
      
  - <span data-ttu-id="8e6c3-126">LOGON_SP_IDLE：请求 MAPI 后台处理程序经常调用传输提供程序的 [IXPLogon：：Idle](ixplogon-idle.md) 方法进行空闲时间处理。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-126">LOGON_SP_IDLE: Requests that the MAPI spooler frequently call the transport provider's [IXPLogon::Idle](ixplogon-idle.md) method for idle-time processing.</span></span> 
      
  - <span data-ttu-id="8e6c3-127">LOGON_SP_POLL：请求 MAPI 后台处理程序经常对返回的登录对象调用 [IXPLogon：:P oll](ixplogon-poll.md) 方法以检查新邮件。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-127">LOGON_SP_POLL: Requests that the MAPI spooler frequently call the [IXPLogon::Poll](ixplogon-poll.md) method on the returned logon object to check for new messages.</span></span> <span data-ttu-id="8e6c3-128">如果未设置此标志，则 MAPI 后台处理程序仅在传输提供程序使用 [IMAPISupport：：SpoolerNotify](imapisupport-spoolernotify.md) 方法通知后台处理程序有要处理的新消息时检查新邮件。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-128">If this flag is not set, the MAPI spooler only checks for new messages when the transport provider uses the [IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md) method to notify the spooler that there are new messages to process.</span></span> <span data-ttu-id="8e6c3-129">通过不设置此标志和未通知 MAPI 后台处理程序的邮件接收，传输提供程序实际上变为仅发送。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-129">A transport provider effectively becomes send-only by not setting this flag and by not notifying the MAPI spooler of message receipt.</span></span> 
      
  - <span data-ttu-id="8e6c3-130">LOGON_SP_RESOLVE：MAPI 后台处理程序解析为完整地址的请求将处理此传输提供程序不支持的收件人的所有邮件地址。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-130">LOGON_SP_RESOLVE: Requests that the MAPI spooler resolve to full addresses all message addresses for recipients not supported by this transport provider.</span></span> <span data-ttu-id="8e6c3-131">因此，传输提供程序可以构造所有收件人的答复路径。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-131">Therefore that the transport provider can construct a reply path for all recipients.</span></span>
      
  - <span data-ttu-id="8e6c3-132">[MAPI_UNICODE：MAPIERROR](mapierror.md)结构中返回的字符串（如果有）采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-132">MAPI_UNICODE: The returned strings in the [MAPIERROR](mapierror.md) structure, if any, are in Unicode format.</span></span> <span data-ttu-id="8e6c3-133">如果未MAPI_UNICODE，则字符串采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-133">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span> 
    
<span data-ttu-id="8e6c3-134">_lppMAPIError_：[out] 指向返回 **的 MAPIERROR** 结构的指针（如果有），其中包含错误的版本、组件和上下文信息。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-134">_lppMAPIError_: [out] Pointer to a pointer to the returned **MAPIERROR** structure, if any, that contains version, component, and context information for the error.</span></span> <span data-ttu-id="8e6c3-135">如果没有要返回的 **MAPIERROR** 结构，可以将 _lppMAPIError_ 参数设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-135">The  _lppMAPIError_ parameter can be set to NULL if there is no **MAPIERROR** structure to return.</span></span> 
    
<span data-ttu-id="8e6c3-136">_lppXPLogon_：[out] 指向返回的传输提供程序登录对象的指针。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-136">_lppXPLogon_: [out] Pointer to the pointer to the returned transport provider logon object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="8e6c3-137">返回值</span><span class="sxs-lookup"><span data-stu-id="8e6c3-137">Return value</span></span>

<span data-ttu-id="8e6c3-138">S_OK：调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-138">S_OK: The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="8e6c3-139">MAPI_E_FAILONEPROVIDER：此提供程序无法登录，但此错误不应禁用该服务。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-139">MAPI_E_FAILONEPROVIDER: This provider cannot log on, but this error should not disable the service.</span></span> 
    
<span data-ttu-id="8e6c3-140">MAPI_E_UNCONFIGURED：配置文件包含的信息不足，无法完成登录。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-140">MAPI_E_UNCONFIGURED: The profile does not contain enough information for the logon to be completed.</span></span> <span data-ttu-id="8e6c3-141">MAPI 调用提供程序的邮件服务入口点函数。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-141">MAPI calls the provider's message service entry point function.</span></span>
    
<span data-ttu-id="8e6c3-142">MAPI_E_UNKNOWN_CPID：提供程序无法支持客户端的代码页。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-142">MAPI_E_UNKNOWN_CPID: The provider cannot support the client's code page.</span></span>
    
<span data-ttu-id="8e6c3-143">MAPI_E_UNKNOWN_LCID：提供程序无法支持客户端区域设置信息。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-143">MAPI_E_UNKNOWN_LCID: The provider cannot support the client's locale information.</span></span>
    
<span data-ttu-id="8e6c3-144">MAPI_E_USER_CANCEL：用户通常通过单击对话框中的"取消"按钮来取消操作。 </span><span class="sxs-lookup"><span data-stu-id="8e6c3-144">MAPI_E_USER_CANCEL: The user canceled the operation, typically by clicking the **Cancel** button in a dialog box.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="8e6c3-145">备注</span><span class="sxs-lookup"><span data-stu-id="8e6c3-145">Remarks</span></span>

<span data-ttu-id="8e6c3-146">MAPI 后台处理程序调用 **IXPProvider：：TransportLogon** 方法为用户建立登录会话。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-146">The MAPI spooler calls the **IXPProvider::TransportLogon** method to establish a logon session for a user.</span></span> 
  
<span data-ttu-id="8e6c3-147">大多数传输提供程序都使用 [IMAPISupport：：OpenProfileSection](imapisupport-openprofilesection.md) 方法，该方法与  _lpMAPISup_ 参数指向的支持对象一起提供，用于保存和检索用户标识信息、服务器地址和凭据。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-147">Most transport providers use the [IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md) method provided with the support object pointed to by the  _lpMAPISup_ parameter for saving and retrieving user identity information, server addresses, and credentials.</span></span> <span data-ttu-id="8e6c3-148">通过使用 **OpenProfileSection，** 传输提供程序可以保存任意信息并将其与特定资源的登录关联。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-148">By using **OpenProfileSection**, a transport provider can save arbitrary information and associate it with a logon to a particular resource.</span></span> <span data-ttu-id="8e6c3-149">例如，提供程序可以使用 **OpenProfileSection** 保存与特定会话关联的帐户名和密码，以及访问该会话的资源所需的任何服务器名称或其他必要信息。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-149">For example, a provider can use **OpenProfileSection** to save the account name and password associated with a particular session and any server names or other necessary information that are required to access resources for that session.</span></span> <span data-ttu-id="8e6c3-150">MAPI 从外部访问隐藏与资源关联的信息。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-150">MAPI hides information associated with a resource from outside access.</span></span> <span data-ttu-id="8e6c3-151">通过  _lpMAPISup_ 提供的配置文件部分由 MAPI 后台处理程序管理，因此与此用户上下文相关的数据与其他上下文的数据分隔开。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-151">The profile section made available through  _lpMAPISup_ is managed by the MAPI spooler so data related to this user context is separated from data for other contexts.</span></span> 
  
<span data-ttu-id="8e6c3-152">传输提供程序必须对支持对象调用 **IUnknown：：AddRef** 方法，并保留指向此对象的指针副本作为提供程序登录对象的一部分。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-152">The transport provider must call the **IUnknown::AddRef** method on the support object and keep a copy of the pointer to this object as part of the provider logon object.</span></span> 
  
<span data-ttu-id="8e6c3-153">提供了显示名称  _lpszProfileName_ 中的配置文件，以便传输提供程序可以在错误消息或登录对话框中使用它。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-153">The profile display name in  _lpszProfileName_ is provided so the transport provider can use it in error messages or logon dialog boxes.</span></span> <span data-ttu-id="8e6c3-154">如果提供程序保留此名称，则必须将名称复制到提供程序分配的存储中。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-154">If the provider retains this name, it must be copied to storage allocated by the provider.</span></span> 
  
<span data-ttu-id="8e6c3-155">与其他服务提供商紧密结合的传输提供程序可能需要在登录时执行其他工作，以建立配套提供程序之间操作所需的良好凭据。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-155">Transport providers that are tightly coupled with other service providers may have to do additional work at logon to establish the good credentials required for operations between companion providers.</span></span>
  
<span data-ttu-id="8e6c3-156">通常，当用户首次登录到配置文件时，将打开传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-156">Usually, transport providers are opened when the user first logs on to a profile.</span></span> <span data-ttu-id="8e6c3-157">由于第一次登录配置文件通常先于登录到任何邮件存储，所以 MAPI 后台处理程序通常使用在 _lpulFlags_ 中设置的 LOGON_NO_INBOUND 和 LOGON_NO_OUTBOUND 标志调用 **TransportLogon。**</span><span class="sxs-lookup"><span data-stu-id="8e6c3-157">Because the first logon to a profile therefore generally comes before logon to any message store, the MAPI spooler usually calls **TransportLogon** with both the LOGON_NO_INBOUND and LOGON_NO_OUTBOUND flags set in  _lpulFlags_.</span></span> <span data-ttu-id="8e6c3-158">稍后，当相应的邮件存储在配置文件会话中可用时，MAPI 后台处理程序将调用 **TransportNotify** 以启动传输提供程序的传入和传出操作。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-158">Later, when the appropriate message stores are available in the profile session, the MAPI spooler calls **TransportNotify** to initiate incoming and outgoing operations for the transport provider.</span></span> 
  
<span data-ttu-id="8e6c3-159">在  _lpulFlags_ LOGON_NO_CONNECT标志表示传输提供程序的脱机操作。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-159">Passing the LOGON_NO_CONNECT flag in  _lpulFlags_ signals offline operation of the transport provider.</span></span> <span data-ttu-id="8e6c3-160">此标志指示不应进行外部连接;如果传输提供程序在没有外部连接的情况下无法建立会话，则应该返回登录的错误值。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-160">This flag indicates no external connections should be made; if the transport provider cannot establish a session without an external connection, it should return an error value for the logon.</span></span> 
  
<span data-ttu-id="8e6c3-161">如果传输提供程序设计为使用系统LOGON_SP_IDLE空闲的时间，则传输提供程序应在初始化时在  _lpulFlags_ 中设置该标志。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-161">A transport provider should set the LOGON_SP_IDLE flag in  _lpulFlags_ at initialization time if it is designed to use time that the system otherwise spends idle.</span></span> <span data-ttu-id="8e6c3-162">此类时间通常用于处理自动操作，如自动邮件下载、已设置时间的邮件下载或已设置时间的邮件提交。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-162">Such time is often used to handle automatic operations, such as automatic message downloading, timed message downloading, or timed message submission.</span></span> <span data-ttu-id="8e6c3-163">如果设置此标志，MAPI 后台处理程序在出现系统空闲时间时调用 **Idle** 以启动此类操作。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-163">If this flag is set, the MAPI spooler calls **Idle** when system idle time occurs to initiate such operations.</span></span> <span data-ttu-id="8e6c3-164">MAPI 后台处理程序不会在设置的时间间隔内调用 **Idle;** 相反，它仅在真正的空闲时间内调用。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-164">The MAPI spooler does not call **Idle** at set intervals; rather, it is called only during true idle time.</span></span> <span data-ttu-id="8e6c3-165">因此，提供程序不应对调用 **Idle** 方法的频率做出任何假设。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-165">Therefore, providers should not work on any assumption about how frequently their **Idle** methods will be called.</span></span> <span data-ttu-id="8e6c3-166">支持空闲时间运算的提供程序应提供其提供程序管理器中的配置属性表。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-166">Providers that support idle-time operations should supply a configuration user interface for it in their provider property sheet.</span></span> 
  
<span data-ttu-id="8e6c3-167">如果传输提供程序登录成功，提供程序应在  _lppXPLogon_ 参数中返回一个指向登录对象的指针。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-167">If the transport provider logon succeeds, the provider should return in the  _lppXPLogon_ parameter a pointer to a logon object.</span></span> <span data-ttu-id="8e6c3-168">MAPI 后台处理程序将使用此对象进行其他提供程序访问。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-168">The MAPI spooler will use this object for additional provider access.</span></span> <span data-ttu-id="8e6c3-169">如果 **TransportLogon** 显示登录对话框，并且用户通常通过单击对话框中的"取消"按钮来取消登录，则提供程序应返回MAPI_E_USER_CANCEL。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-169">If **TransportLogon** displays a logon dialog box and the user cancels logon typically by clicking the **Cancel** button in the dialog box the provider should return MAPI_E_USER_CANCEL.</span></span> 
  
<span data-ttu-id="8e6c3-170">对于从 **TransportLogon** 返回的多数错误值，MAPI 将禁用提供程序所属的邮件服务。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-170">For most error values returned from **TransportLogon**, MAPI disables the message services to which the provider belongs.</span></span> <span data-ttu-id="8e6c3-171">MAPI 不会为 MAPI 会话的其余部分调用属于该服务的任何提供程序。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-171">MAPI will not call any providers that belong to that service for the rest of the MAPI session.</span></span> <span data-ttu-id="8e6c3-172">相反，当 **TransportLogon** 从MAPI_E_FAILONEPROVIDER返回错误值时，MAPI 不会禁用提供程序所属的邮件服务。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-172">In contrast, when **TransportLogon** returns the MAPI_E_FAILONEPROVIDER error value from its logon, MAPI does not disable the message service to which the provider belongs.</span></span> <span data-ttu-id="8e6c3-173">**TransportLogon** 应MAPI_E_FAILONEPROVIDER如果遇到错误，而该错误不保证为会话的其余部分禁用该服务。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-173">**TransportLogon** should return MAPI_E_FAILONEPROVIDER if it encounters an error that does not warrant disabling the service for the rest of the session.</span></span> 
  
<span data-ttu-id="8e6c3-174">如果提供程序从MAPI_E_UNCONFIGURED返回消息，MAPI 将调用提供程序的邮件服务条目函数，然后重试登录。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-174">If a provider returns MAPI_E_UNCONFIGURED from its logon, MAPI will call the provider's message service entry function and then retry the logon.</span></span> <span data-ttu-id="8e6c3-175">MAPI 将MSG_SERVICE_CONFIGURE传递为上下文，为服务提供自行配置的机会。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-175">MAPI passes MSG_SERVICE_CONFIGURE as the context, to give the service a chance to configure itself.</span></span> <span data-ttu-id="8e6c3-176">如果客户端已选择允许在登录时使用用户界面，该服务可以显示其配置属性表以便用户输入配置信息。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-176">If the client has chosen to allow a user interface on the logon, the service can present its configuration property sheet so that the user can enter configuration information.</span></span> 
  
<span data-ttu-id="8e6c3-177">如果提供程序发现配置文件中未包含所有必需信息，则它应返回MAPI_E_UNCONFIGURED MAPI 调用提供程序的邮件服务入口点函数。</span><span class="sxs-lookup"><span data-stu-id="8e6c3-177">If the provider finds that all the required information is not in the profile, it should return MAPI_E_UNCONFIGURED so that MAPI calls the provider's message service entry point function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="8e6c3-178">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8e6c3-178">See also</span></span>

- [<span data-ttu-id="8e6c3-179">IXPProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="8e6c3-179">IXPProvider : IUnknown</span></span>](ixpprovideriunknown.md)  
- [<span data-ttu-id="8e6c3-180">IMAPISupport::OpenProfileSection</span><span class="sxs-lookup"><span data-stu-id="8e6c3-180">IMAPISupport::OpenProfileSection</span></span>](imapisupport-openprofilesection.md)  
- [<span data-ttu-id="8e6c3-181">IMAPISupport::SpoolerNotify</span><span class="sxs-lookup"><span data-stu-id="8e6c3-181">IMAPISupport::SpoolerNotify</span></span>](imapisupport-spoolernotify.md)  
- [<span data-ttu-id="8e6c3-182">IXPLogon::AddressTypes</span><span class="sxs-lookup"><span data-stu-id="8e6c3-182">IXPLogon::AddressTypes</span></span>](ixplogon-addresstypes.md)  
- [<span data-ttu-id="8e6c3-183">IXPLogon::Idle</span><span class="sxs-lookup"><span data-stu-id="8e6c3-183">IXPLogon::Idle</span></span>](ixplogon-idle.md)  
- [<span data-ttu-id="8e6c3-184">IXPLogon::Poll</span><span class="sxs-lookup"><span data-stu-id="8e6c3-184">IXPLogon::Poll</span></span>](ixplogon-poll.md)  
- [<span data-ttu-id="8e6c3-185">IXPLogon::TransportNotify</span><span class="sxs-lookup"><span data-stu-id="8e6c3-185">IXPLogon::TransportNotify</span></span>](ixplogon-transportnotify.md) 
- [<span data-ttu-id="8e6c3-186">MAPIERROR</span><span class="sxs-lookup"><span data-stu-id="8e6c3-186">MAPIERROR</span></span>](mapierror.md)

