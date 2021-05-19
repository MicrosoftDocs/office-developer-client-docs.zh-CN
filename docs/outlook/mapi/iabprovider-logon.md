---
title: IABProviderLogon
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IABProvider.Logon
api_type:
- COM
ms.assetid: f9468715-1674-4d14-81c8-2f24dbaa0453
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 59c6d4a05c91511ad8c481fd4ddbe42396442190
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348781"
---
# <a name="iabproviderlogon"></a><span data-ttu-id="dc1ad-103">IABProvider::Logon</span><span class="sxs-lookup"><span data-stu-id="dc1ad-103">IABProvider::Logon</span></span>

  
  
<span data-ttu-id="dc1ad-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="dc1ad-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="dc1ad-105">建立与活动会话的连接。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-105">Establishes a connection to an active session.</span></span>
  
```cpp
HRESULT Logon(
  LPMAPISUP lpMAPISup,
  ULONG_PTR ulUIParam,
  LPSTR lpszProfileName,
  ULONG ulFlags,
  ULONG FAR * lpulcbSecurity,
  LPBYTE FAR * lppbSecurity,
  LPMAPIERROR FAR * lppMAPIError,
  LPABLOGON FAR * lppABLogon
);
```

## <a name="parameters"></a><span data-ttu-id="dc1ad-106">参数</span><span class="sxs-lookup"><span data-stu-id="dc1ad-106">Parameters</span></span>

 <span data-ttu-id="dc1ad-107">_lpMAPISup_</span><span class="sxs-lookup"><span data-stu-id="dc1ad-107">_lpMAPISup_</span></span>
  
> <span data-ttu-id="dc1ad-108">[in]指向通讯簿提供程序的支持对象的指针。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-108">[in] A pointer to the address book provider's support object.</span></span>
    
 <span data-ttu-id="dc1ad-109">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="dc1ad-109">_ulUIParam_</span></span>
  
> <span data-ttu-id="dc1ad-110">[in]Logon 方法显示的登录对话框的父窗口句柄（如果允许）。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-110">[in] A handle to the parent window for the logon dialog box that the **Logon** method displays, if permitted.</span></span> <span data-ttu-id="dc1ad-111">_ulUIParam_ 参数包含在上一次调用 [MAPILogonEx](mapilogonex.md)函数时传递给 MAPI 的同名参数的值。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-111">The  _ulUIParam_ parameter contains the value of the parameter of the same name passed to MAPI in the previous call to the [MAPILogonEx](mapilogonex.md) function.</span></span> 
    
 <span data-ttu-id="dc1ad-112">_lpszProfileName_</span><span class="sxs-lookup"><span data-stu-id="dc1ad-112">_lpszProfileName_</span></span>
  
> <span data-ttu-id="dc1ad-113">[in]指向会话配置文件名称的指针。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-113">[in] A pointer to the name of the session profile.</span></span>
    
 <span data-ttu-id="dc1ad-114">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="dc1ad-114">_ulFlags_</span></span>
  
> <span data-ttu-id="dc1ad-115">[in]控制如何执行登录的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-115">[in] A bitmask of flags that controls how the logon is performed.</span></span> <span data-ttu-id="dc1ad-116">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="dc1ad-116">The following flags can be set:</span></span>
    
<span data-ttu-id="dc1ad-117">AB_NO_DIALOG</span><span class="sxs-lookup"><span data-stu-id="dc1ad-117">AB_NO_DIALOG</span></span> 
  
> <span data-ttu-id="dc1ad-118">提供程序不应在登录期间显示对话框。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-118">The provider should not display a dialog box during logon.</span></span> <span data-ttu-id="dc1ad-119">如果未设置此标志，提供程序可以显示一个对话框，提示用户输入缺少的配置信息。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-119">If this flag is not set, the provider can display a dialog box to prompt the user for missing configuration information.</span></span>
    
<span data-ttu-id="dc1ad-120">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="dc1ad-120">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="dc1ad-121">使 **登录** 能够成功返回（可能在登录过程完成之前）。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-121">Enables **Logon** to return successfully, possibly before the logon process is finished.</span></span> 
    
<span data-ttu-id="dc1ad-122">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="dc1ad-122">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="dc1ad-123">所有字符串都应采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-123">All strings should be in Unicode format.</span></span> <span data-ttu-id="dc1ad-124">如果未MAPI_UNICODE，则字符串应为 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-124">If the MAPI_UNICODE flag is not set, the strings should be in ANSI format.</span></span>
    
 <span data-ttu-id="dc1ad-125">_lpulcbSecurity_</span><span class="sxs-lookup"><span data-stu-id="dc1ad-125">_lpulcbSecurity_</span></span>
  
> <span data-ttu-id="dc1ad-126">[in， out]指向  _lppbSecurity_ 参数指向的安全凭据结构的大小（以字节为单位）的指针。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-126">[in, out] A pointer to the size, in bytes, of the security credentials structure pointed to by the  _lppbSecurity_ parameter.</span></span> <span data-ttu-id="dc1ad-127">在输入时，值必须为非零值;输出时，该值必须为零。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-127">On input, the value must be nonzero; on output, the value must be zero.</span></span> <span data-ttu-id="dc1ad-128">在这两种情况下，指针都必须有效。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-128">In both cases, the pointers must be valid.</span></span> 
    
 <span data-ttu-id="dc1ad-129">_lppbSecurity_</span><span class="sxs-lookup"><span data-stu-id="dc1ad-129">_lppbSecurity_</span></span>
  
> <span data-ttu-id="dc1ad-130">[in， out]指向指向安全凭据的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-130">[in, out] A pointer to a pointer to security credentials.</span></span> <span data-ttu-id="dc1ad-131">在输入时，值必须为非零值;输出时，该值必须为零。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-131">On input, the value must be nonzero; on output, the value must be zero.</span></span> <span data-ttu-id="dc1ad-132">在这两种情况下，指针都必须有效。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-132">In both cases the pointer must be valid.</span></span>
    
 <span data-ttu-id="dc1ad-133">_lppMAPIError_</span><span class="sxs-lookup"><span data-stu-id="dc1ad-133">_lppMAPIError_</span></span>
  
> <span data-ttu-id="dc1ad-134">[out]指向指向 [MAPIERROR 结构的指针的](mapierror.md) 指针。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-134">[out] A pointer to a pointer to a [MAPIERROR](mapierror.md) structure.</span></span> <span data-ttu-id="dc1ad-135">如果没有要返回的 **MAPIERROR** 结构，可以将 _lppMAPIError_ 参数设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-135">The  _lppMAPIError_ parameter can be set to NULL if there is no **MAPIERROR** structure to return.</span></span> 
    
 <span data-ttu-id="dc1ad-136">_lppABLogon_</span><span class="sxs-lookup"><span data-stu-id="dc1ad-136">_lppABLogon_</span></span>
  
> <span data-ttu-id="dc1ad-137">[out]指向指向提供程序登录对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-137">[out] A pointer to a pointer to the provider's logon object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="dc1ad-138">返回值</span><span class="sxs-lookup"><span data-stu-id="dc1ad-138">Return value</span></span>

<span data-ttu-id="dc1ad-139">S_OK</span><span class="sxs-lookup"><span data-stu-id="dc1ad-139">S_OK</span></span> 
  
> <span data-ttu-id="dc1ad-140">已成功建立与活动会话的连接。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-140">A connection to an active session was successfully established.</span></span>
    
<span data-ttu-id="dc1ad-141">MAPI_E_FAILONEPROVIDER</span><span class="sxs-lookup"><span data-stu-id="dc1ad-141">MAPI_E_FAILONEPROVIDER</span></span> 
  
> <span data-ttu-id="dc1ad-142">提供程序无法登录，但 MAPI 可以继续在提供程序所属的邮件服务中登录其他提供程序。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-142">The provider cannot log on, but MAPI can continue to log on the other providers in the message service to which the provider belongs.</span></span> 
    
<span data-ttu-id="dc1ad-143">MAPI_E_UNCONFIGURED</span><span class="sxs-lookup"><span data-stu-id="dc1ad-143">MAPI_E_UNCONFIGURED</span></span> 
  
> <span data-ttu-id="dc1ad-144">提供程序没有足够的信息来完成登录。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-144">The provider has insufficient information to complete the logon.</span></span> <span data-ttu-id="dc1ad-145">MAPI 调用提供程序的邮件服务条目函数。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-145">MAPI calls the provider's message service entry function.</span></span>
    
<span data-ttu-id="dc1ad-146">MAPI_E_UNKNOWN_CPID</span><span class="sxs-lookup"><span data-stu-id="dc1ad-146">MAPI_E_UNKNOWN_CPID</span></span> 
  
> <span data-ttu-id="dc1ad-147">服务器未配置为支持客户端的代码页。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-147">The server is not configured to support the client's code page.</span></span>
    
<span data-ttu-id="dc1ad-148">MAPI_E_UNKNOWN_LCID</span><span class="sxs-lookup"><span data-stu-id="dc1ad-148">MAPI_E_UNKNOWN_LCID</span></span> 
  
> <span data-ttu-id="dc1ad-149">服务器未配置为支持客户端区域设置信息。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-149">The server is not configured to support the client's locale information.</span></span>
    
<span data-ttu-id="dc1ad-150">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="dc1ad-150">MAPI_E_USER_CANCEL</span></span> 
  
> <span data-ttu-id="dc1ad-151">用户通常通过单击登录对话框中的"取消"按钮来取消操作。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-151">The user canceled the operation, typically by clicking the **Cancel** button in the logon dialog box.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="dc1ad-152">备注</span><span class="sxs-lookup"><span data-stu-id="dc1ad-152">Remarks</span></span>

<span data-ttu-id="dc1ad-153">当客户端调用 [IMAPISession：：OpenAddressBook](imapisession-openaddressbook.md) 方法时，与会话配置文件中的每个通讯簿提供程序建立连接。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-153">Connections are established with each address book provider in the session profile when a client calls the [IMAPISession::OpenAddressBook](imapisession-openaddressbook.md) method.</span></span> <span data-ttu-id="dc1ad-154">**OpenAddressBook** 然后调用每个提供程序的 **Logon** 方法。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-154">**OpenAddressBook** then calls each provider's **Logon** method.</span></span> 
  
<span data-ttu-id="dc1ad-155">_lpszProfileName_ 参数指向的配置文件名称显示在用户客户端的字符集内，如 _ulFlags_ 参数中是否存在 MAPI_UNICODE 标志所指示。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-155">The profile name pointed to by the  _lpszProfileName_ parameter is displayed in the character set of the user's client as indicated by the presence or absence of the MAPI_UNICODE flag in the  _ulFlags_ parameter.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="dc1ad-156">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="dc1ad-156">Notes to implementers</span></span>

<span data-ttu-id="dc1ad-157">在 **Logon** 方法的实现中，调用 [IMAPISupport：：SetProviderUID](imapisupport-setprovideruid.md) 方法来注册唯一标识符或 [MAPIUID](mapiuid.md) 结构。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-157">In your implementation of the **Logon** method, call the [IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md) method to register a unique identifier, or [MAPIUID](mapiuid.md) structure.</span></span> <span data-ttu-id="dc1ad-158">每个对象都有一个包含此 **MAPIUID** 的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-158">Each of your objects will have an entry identifier that includes this **MAPIUID**.</span></span> <span data-ttu-id="dc1ad-159">MAPI 使用 **MAPIUID** 将对象与它的提供程序相匹配。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-159">MAPI uses the **MAPIUID** to match an object with its provider.</span></span> <span data-ttu-id="dc1ad-160">例如，当客户端调用 [IMAPISession：：OpenEntry](imapisession-openentry.md) 方法打开消息用户时 **，OpenEntry** 将检查传入的条目标识符的 **MAPIUID** 部分，并通过通讯簿提供程序注册的 **MAPIUID** 进行匹配。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-160">For example, when a client calls the [IMAPISession::OpenEntry](imapisession-openentry.md) method to open a messaging user, **OpenEntry** examines the **MAPIUID** portion of the entry identifier that was passed in and matches it with a **MAPIUID** registered by an address book provider.</span></span> 
  
<span data-ttu-id="dc1ad-161">如果客户端多次登录提供程序，你可能希望针对每次登录注册不同的 **MAPIUID。**</span><span class="sxs-lookup"><span data-stu-id="dc1ad-161">If a client logs on to your provider more than once, you may want to register a different **MAPIUID** for each logon.</span></span> <span data-ttu-id="dc1ad-162">通过注册唯一 **MAPIUID** 结构，MAPI 可以正确地将请求路由到相应的提供程序实例。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-162">Registering unique **MAPIUID** structures enables MAPI to correctly route requests to the appropriate provider instance.</span></span> <span data-ttu-id="dc1ad-163">但是，你可能希望让每个登录对象共享一 **个 MAPIUID**。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-163">However, you may want to have every logon object share one **MAPIUID**.</span></span> <span data-ttu-id="dc1ad-164">在这种情况下，你必须能够自己处理路由，而不是依赖 MAPI。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-164">In this case, you must be able to handle the routing yourself instead of relying on MAPI.</span></span> <span data-ttu-id="dc1ad-165">若要详细了解如何创建 **MAPIUID，** 请参阅注册 [服务提供程序唯一标识符](registering-service-provider-unique-identifiers.md)。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-165">For more information about how to create a **MAPIUID**, see [Registering Service Provider Unique Identifiers](registering-service-provider-unique-identifiers.md).</span></span>
  
<span data-ttu-id="dc1ad-166">MAPI 传递给 _lpMAPISup_ 参数中的 **Logon** 方法的支持对象提供对 [IMAPISupport ： IUnknown](imapisupportiunknown.md)接口中包含的许多方法的访问。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-166">The support object that MAPI passes to your **Logon** method in the  _lpMAPISup_ parameter provides access to many of the methods included in the [IMAPISupport : IUnknown](imapisupportiunknown.md) interface.</span></span> <span data-ttu-id="dc1ad-167">MAPI 创建根据提供程序类型自定义的支持对象。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-167">MAPI creates a support object that is customized to your type of provider.</span></span> <span data-ttu-id="dc1ad-168">例如，如果在建立连接时需要登录到基础消息系统或目录服务，可以调用 [IMAPISupport：：OpenProfileSection](imapisupport-openprofilesection.md) 方法来检索此特定登录会话的安全凭据。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-168">For example, if you need to log on to an underlying messaging system or directory service when you establish your connection, you can call the [IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md) method to retrieve security credentials for this particular logon session.</span></span> 
  
<span data-ttu-id="dc1ad-169">如果 **登录** 成功，请确保调用支持对象的 [IUnknown：：AddRef](https://msdn.microsoft.com/library/ms691379%28VS.85%29.aspx) 方法来增加其引用计数。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-169">If **Logon** is successful, be sure that you call the support object's [IUnknown::AddRef](https://msdn.microsoft.com/library/ms691379%28VS.85%29.aspx) method to increment its reference count.</span></span> <span data-ttu-id="dc1ad-170">这样，提供程序可以保留会话其余部分的支持对象指针。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-170">This enables your provider to hold onto the support object pointer for the rest of the session.</span></span> <span data-ttu-id="dc1ad-171">如果不调用此 **AddRef** 方法，MAPI 将卸载您的提供程序。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-171">If you do not call this **AddRef** method, MAPI will unload your provider.</span></span> 
  
<span data-ttu-id="dc1ad-172">您可以在错误对话框、登录屏幕或其他用户界面中包括  _lpszProfileName_ 参数中传递的配置文件名称。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-172">You can include the profile name passed in the  _lpszProfileName_ parameter in error dialog boxes, logon screens, or other user interfaces.</span></span> <span data-ttu-id="dc1ad-173">若要使用配置文件名称，请将其复制到已分配的存储。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-173">To use the profile name, copy it to storage that you have allocated.</span></span> 
  
<span data-ttu-id="dc1ad-174">创建登录对象，在  _lppABLogon_ 参数中返回指向该对象的指针。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-174">Create a logon object and return a pointer to it in the  _lppABLogon_ parameter.</span></span> <span data-ttu-id="dc1ad-175">MAPI 使用此登录对象调用 [IABLogon](iablogoniunknown.md) 实现中的方法。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-175">MAPI uses this logon object to make calls to the methods in your [IABLogon](iablogoniunknown.md) implementation.</span></span> 
  
<span data-ttu-id="dc1ad-176">如果在登录过程中需要密码，则仅在未设置登录AB_NO_DIALOG显示登录对话框。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-176">If you require a password during logon, display a logon dialog box only if the AB_NO_DIALOG flag is not set.</span></span> <span data-ttu-id="dc1ad-177">如果用户取消登录过程，通常通过单击对话框中的"取消"按钮，从 **"MAPI_E_USER_CANCEL"返回" 取消"。**</span><span class="sxs-lookup"><span data-stu-id="dc1ad-177">If the user cancels the logon process, typically by clicking the **Cancel** button in the dialog box, return MAPI_E_USER_CANCEL from **Logon**.</span></span>
  
<span data-ttu-id="dc1ad-178">通常，当通讯簿提供程序无法登录时，MAPI 将禁用出现故障的提供程序所属的邮件服务，即 MAPI 不会尝试在会话生存期的其余部分为属于该服务的其他任何提供程序建立连接。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-178">Typically, when an address book provider cannot log on, MAPI disables the message service to which the failing provider belongs—that is, MAPI will not try to establish connections for any of the other providers that belong to the service for the rest of the session's lifetime.</span></span> <span data-ttu-id="dc1ad-179">但是，如果您的提供程序无法建立连接，并且您不想禁用整个服务，请返回 MAPI_E_FAILONEPROVIDER 或 MAPI_E_UNCONFIGURED。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-179">However, if your provider cannot establish a connection and you want not to disable the entire service, return either MAPI_E_FAILONEPROVIDER or MAPI_E_UNCONFIGURED.</span></span> <span data-ttu-id="dc1ad-180">MAPI 不会禁用提供程序所属的邮件服务。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-180">MAPI will not disable the message service to which the provider belongs.</span></span> 
  
<span data-ttu-id="dc1ad-181">如果MAPI_E_FAILONEPROVIDER严重到足以阻止邮件服务中其他提供程序建立连接的错误，则返回此代码。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-181">Return MAPI_E_FAILONEPROVIDER if an error occurs that is not serious enough to prevent the other providers in the message service from establishing connections.</span></span> <span data-ttu-id="dc1ad-182">如果MAPI_E_UNCONFIGURED缺少必需的配置信息，并且无法显示对话框来提示用户，则返回此参数。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-182">Return MAPI_E_UNCONFIGURED if the necessary configuration information is missing from the profile and you cannot display a dialog box to prompt the user.</span></span> <span data-ttu-id="dc1ad-183">MAPI 将调用提供程序的邮件服务入口点函数（将 MSG_SERVICE_CONFIGURE 设置为  _ulContext_ 参数）来响应，使服务有机会以编程方式或通过使用 属性表 配置自身。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-183">MAPI will respond by calling your provider's message service entry point function with MSG_SERVICE_CONFIGURE set as the  _ulContext_ parameter to give the service a chance to configure itself, either programmatically or using a property sheet.</span></span> <span data-ttu-id="dc1ad-184">邮件服务入口点函数完成后，MAPI 将重试登录。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-184">When the message service entry point function has finished, MAPI retries the logon.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="dc1ad-185">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dc1ad-185">See also</span></span>



[<span data-ttu-id="dc1ad-186">IABLogon::Logoff</span><span class="sxs-lookup"><span data-stu-id="dc1ad-186">IABLogon::Logoff</span></span>](iablogon-logoff.md)
  
[<span data-ttu-id="dc1ad-187">IABLogon::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="dc1ad-187">IABLogon::OpenEntry</span></span>](iablogon-openentry.md)
  
[<span data-ttu-id="dc1ad-188">IMAPISupport::OpenProfileSection</span><span class="sxs-lookup"><span data-stu-id="dc1ad-188">IMAPISupport::OpenProfileSection</span></span>](imapisupport-openprofilesection.md)
  
[<span data-ttu-id="dc1ad-189">IMAPISupport::SetProviderUID</span><span class="sxs-lookup"><span data-stu-id="dc1ad-189">IMAPISupport::SetProviderUID</span></span>](imapisupport-setprovideruid.md)
  
[<span data-ttu-id="dc1ad-190">MSGSERVICEENTRY</span><span class="sxs-lookup"><span data-stu-id="dc1ad-190">MSGSERVICEENTRY</span></span>](msgserviceentry.md)
  
[<span data-ttu-id="dc1ad-191">IABProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="dc1ad-191">IABProvider : IUnknown</span></span>](iabprovideriunknown.md)

