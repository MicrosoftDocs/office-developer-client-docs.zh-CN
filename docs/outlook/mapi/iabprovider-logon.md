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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 8cb7934919722139622b6caf3aac741c9b2e54c5
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22582460"
---
# <a name="iabproviderlogon"></a><span data-ttu-id="86fd6-103">IABProvider::Logon</span><span class="sxs-lookup"><span data-stu-id="86fd6-103">IABProvider::Logon</span></span>

  
  
<span data-ttu-id="86fd6-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="86fd6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="86fd6-105">建立到活动会话的连接。</span><span class="sxs-lookup"><span data-stu-id="86fd6-105">Establishes a connection to an active session.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="86fd6-106">参数</span><span class="sxs-lookup"><span data-stu-id="86fd6-106">Parameters</span></span>

 <span data-ttu-id="86fd6-107">_lpMAPISup_</span><span class="sxs-lookup"><span data-stu-id="86fd6-107">_lpMAPISup_</span></span>
  
> <span data-ttu-id="86fd6-108">[in]指向地址簿提供程序的支持对象的指针。</span><span class="sxs-lookup"><span data-stu-id="86fd6-108">[in] A pointer to the address book provider's support object.</span></span>
    
 <span data-ttu-id="86fd6-109">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="86fd6-109">_ulUIParam_</span></span>
  
> <span data-ttu-id="86fd6-110">[in]**Logon**方法显示，如果允许的登录对话框中的父窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="86fd6-110">[in] A handle to the parent window for the logon dialog box that the **Logon** method displays, if permitted.</span></span> <span data-ttu-id="86fd6-111">_UlUIParam_参数包含在以前的呼叫[MAPILogonEx](mapilogonex.md)函数传递给 MAPI 具有相同名称的参数的值。</span><span class="sxs-lookup"><span data-stu-id="86fd6-111">The  _ulUIParam_ parameter contains the value of the parameter of the same name passed to MAPI in the previous call to the [MAPILogonEx](mapilogonex.md) function.</span></span> 
    
 <span data-ttu-id="86fd6-112">_lpszProfileName_</span><span class="sxs-lookup"><span data-stu-id="86fd6-112">_lpszProfileName_</span></span>
  
> <span data-ttu-id="86fd6-113">[in]一个指向会话配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="86fd6-113">[in] A pointer to the name of the session profile.</span></span>
    
 <span data-ttu-id="86fd6-114">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="86fd6-114">_ulFlags_</span></span>
  
> <span data-ttu-id="86fd6-115">[in]位掩码的标志，控制如何执行登录。</span><span class="sxs-lookup"><span data-stu-id="86fd6-115">[in] A bitmask of flags that controls how the logon is performed.</span></span> <span data-ttu-id="86fd6-116">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="86fd6-116">The following flags can be set:</span></span>
    
<span data-ttu-id="86fd6-117">AB_NO_DIALOG</span><span class="sxs-lookup"><span data-stu-id="86fd6-117">AB_NO_DIALOG</span></span> 
  
> <span data-ttu-id="86fd6-118">提供程序不应在登录过程中显示一个对话框。</span><span class="sxs-lookup"><span data-stu-id="86fd6-118">The provider should not display a dialog box during logon.</span></span> <span data-ttu-id="86fd6-119">如果未设置此标志，提供程序可以显示一个对话框，提示用户缺少的配置信息。</span><span class="sxs-lookup"><span data-stu-id="86fd6-119">If this flag is not set, the provider can display a dialog box to prompt the user for missing configuration information.</span></span>
    
<span data-ttu-id="86fd6-120">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="86fd6-120">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="86fd6-121">允许**登录**成功返回，可能之前完成登录过程。</span><span class="sxs-lookup"><span data-stu-id="86fd6-121">Enables **Logon** to return successfully, possibly before the logon process is finished.</span></span> 
    
<span data-ttu-id="86fd6-122">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="86fd6-122">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="86fd6-123">所有字符串都应为 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="86fd6-123">All strings should be in Unicode format.</span></span> <span data-ttu-id="86fd6-124">如果未设置 MAPI_UNICODE 标志，则字符串应以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="86fd6-124">If the MAPI_UNICODE flag is not set, the strings should be in ANSI format.</span></span>
    
 <span data-ttu-id="86fd6-125">_lpulcbSecurity_</span><span class="sxs-lookup"><span data-stu-id="86fd6-125">_lpulcbSecurity_</span></span>
  
> <span data-ttu-id="86fd6-126">[传入、 传出]指向的大小，以字节为单位_lppbSecurity_参数指向的安全凭据结构的指针。</span><span class="sxs-lookup"><span data-stu-id="86fd6-126">[in, out] A pointer to the size, in bytes, of the security credentials structure pointed to by the  _lppbSecurity_ parameter.</span></span> <span data-ttu-id="86fd6-127">在输入的值必须是非零值;输出，则必须为零。</span><span class="sxs-lookup"><span data-stu-id="86fd6-127">On input, the value must be nonzero; on output, the value must be zero.</span></span> <span data-ttu-id="86fd6-128">在这两种情况下，必须是有效的指针。</span><span class="sxs-lookup"><span data-stu-id="86fd6-128">In both cases, the pointers must be valid.</span></span> 
    
 <span data-ttu-id="86fd6-129">_lppbSecurity_</span><span class="sxs-lookup"><span data-stu-id="86fd6-129">_lppbSecurity_</span></span>
  
> <span data-ttu-id="86fd6-130">[传入、 传出]指向安全凭据的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="86fd6-130">[in, out] A pointer to a pointer to security credentials.</span></span> <span data-ttu-id="86fd6-131">在输入的值必须是非零值;输出，则必须为零。</span><span class="sxs-lookup"><span data-stu-id="86fd6-131">On input, the value must be nonzero; on output, the value must be zero.</span></span> <span data-ttu-id="86fd6-132">在这两种情况下必须是有效的指针。</span><span class="sxs-lookup"><span data-stu-id="86fd6-132">In both cases the pointer must be valid.</span></span>
    
 <span data-ttu-id="86fd6-133">_lppMAPIError_</span><span class="sxs-lookup"><span data-stu-id="86fd6-133">_lppMAPIError_</span></span>
  
> <span data-ttu-id="86fd6-134">[输出]指向[MAPIERROR](mapierror.md)结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="86fd6-134">[out] A pointer to a pointer to a [MAPIERROR](mapierror.md) structure.</span></span> <span data-ttu-id="86fd6-135">如果不没有返回任何**MAPIERROR**结构， _lppMAPIError_参数可以设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="86fd6-135">The  _lppMAPIError_ parameter can be set to NULL if there is no **MAPIERROR** structure to return.</span></span> 
    
 <span data-ttu-id="86fd6-136">_lppABLogon_</span><span class="sxs-lookup"><span data-stu-id="86fd6-136">_lppABLogon_</span></span>
  
> <span data-ttu-id="86fd6-137">[输出]指向提供程序的登录对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="86fd6-137">[out] A pointer to a pointer to the provider's logon object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="86fd6-138">返回值</span><span class="sxs-lookup"><span data-stu-id="86fd6-138">Return value</span></span>

<span data-ttu-id="86fd6-139">S_OK</span><span class="sxs-lookup"><span data-stu-id="86fd6-139">S_OK</span></span> 
  
> <span data-ttu-id="86fd6-140">已成功建立与活动会话的连接。</span><span class="sxs-lookup"><span data-stu-id="86fd6-140">A connection to an active session was successfully established.</span></span>
    
<span data-ttu-id="86fd6-141">MAPI_E_FAILONEPROVIDER</span><span class="sxs-lookup"><span data-stu-id="86fd6-141">MAPI_E_FAILONEPROVIDER</span></span> 
  
> <span data-ttu-id="86fd6-142">提供程序不能登录，但 MAPI 可以继续登录提供程序所属的消息服务中的其他提供程序。</span><span class="sxs-lookup"><span data-stu-id="86fd6-142">The provider cannot log on, but MAPI can continue to log on the other providers in the message service to which the provider belongs.</span></span> 
    
<span data-ttu-id="86fd6-143">MAPI_E_UNCONFIGURED</span><span class="sxs-lookup"><span data-stu-id="86fd6-143">MAPI_E_UNCONFIGURED</span></span> 
  
> <span data-ttu-id="86fd6-144">提供程序没有足够的信息，完成登录。</span><span class="sxs-lookup"><span data-stu-id="86fd6-144">The provider has insufficient information to complete the logon.</span></span> <span data-ttu-id="86fd6-145">MAPI 调用的提供程序的消息服务条目函数。</span><span class="sxs-lookup"><span data-stu-id="86fd6-145">MAPI calls the provider's message service entry function.</span></span>
    
<span data-ttu-id="86fd6-146">MAPI_E_UNKNOWN_CPID</span><span class="sxs-lookup"><span data-stu-id="86fd6-146">MAPI_E_UNKNOWN_CPID</span></span> 
  
> <span data-ttu-id="86fd6-147">将服务器不配置为支持客户端的代码页。</span><span class="sxs-lookup"><span data-stu-id="86fd6-147">The server is not configured to support the client's code page.</span></span>
    
<span data-ttu-id="86fd6-148">MAPI_E_UNKNOWN_LCID</span><span class="sxs-lookup"><span data-stu-id="86fd6-148">MAPI_E_UNKNOWN_LCID</span></span> 
  
> <span data-ttu-id="86fd6-149">将服务器不配置为支持客户端的区域设置信息。</span><span class="sxs-lookup"><span data-stu-id="86fd6-149">The server is not configured to support the client's locale information.</span></span>
    
<span data-ttu-id="86fd6-150">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="86fd6-150">MAPI_E_USER_CANCEL</span></span> 
  
> <span data-ttu-id="86fd6-151">用户取消操作，通常通过单击登录对话框中的**取消**按钮。</span><span class="sxs-lookup"><span data-stu-id="86fd6-151">The user canceled the operation, typically by clicking the **Cancel** button in the logon dialog box.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="86fd6-152">注解</span><span class="sxs-lookup"><span data-stu-id="86fd6-152">Remarks</span></span>

<span data-ttu-id="86fd6-153">连接被建立与每个地址簿提供商会话配置文件中，当客户端调用[IMAPISession::OpenAddressBook](imapisession-openaddressbook.md)方法。</span><span class="sxs-lookup"><span data-stu-id="86fd6-153">Connections are established with each address book provider in the session profile when a client calls the [IMAPISession::OpenAddressBook](imapisession-openaddressbook.md) method.</span></span> <span data-ttu-id="86fd6-154">**OpenAddressBook**然后调用每个提供程序的**登录**方法。</span><span class="sxs-lookup"><span data-stu-id="86fd6-154">**OpenAddressBook** then calls each provider's **Logon** method.</span></span> 
  
<span data-ttu-id="86fd6-155">_LpszProfileName_参数指向的配置文件名称显示在用户的客户端通过状态或缺少 MAPI_UNICODE 标志_ulFlags_参数中所示的字符集。</span><span class="sxs-lookup"><span data-stu-id="86fd6-155">The profile name pointed to by the  _lpszProfileName_ parameter is displayed in the character set of the user's client as indicated by the presence or absence of the MAPI_UNICODE flag in the  _ulFlags_ parameter.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="86fd6-156">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="86fd6-156">Notes to implementers</span></span>

<span data-ttu-id="86fd6-157">在您的**登录**方法的实现，调用注册的唯一标识符或[MAPIUID](mapiuid.md)结构的[IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md)方法。</span><span class="sxs-lookup"><span data-stu-id="86fd6-157">In your implementation of the **Logon** method, call the [IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md) method to register a unique identifier, or [MAPIUID](mapiuid.md) structure.</span></span> <span data-ttu-id="86fd6-158">每个对象都有包含此**MAPIUID**条目标识符。</span><span class="sxs-lookup"><span data-stu-id="86fd6-158">Each of your objects will have an entry identifier that includes this **MAPIUID**.</span></span> <span data-ttu-id="86fd6-159">MAPI 使用**MAPIUID**以匹配具有其提供程序的对象。</span><span class="sxs-lookup"><span data-stu-id="86fd6-159">MAPI uses the **MAPIUID** to match an object with its provider.</span></span> <span data-ttu-id="86fd6-160">例如，当客户端调用[IMAPISession::OpenEntry](imapisession-openentry.md)方法打开邮件用户， **OpenEntry**检查已传递中并与注册的**MAPIUID**相匹配时它的项标识符的**MAPIUID**部分通讯簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="86fd6-160">For example, when a client calls the [IMAPISession::OpenEntry](imapisession-openentry.md) method to open a messaging user, **OpenEntry** examines the **MAPIUID** portion of the entry identifier that was passed in and matches it with a **MAPIUID** registered by an address book provider.</span></span> 
  
<span data-ttu-id="86fd6-161">如果客户端登录到您的提供商多次，可能要注册的每次登录不同**MAPIUID** 。</span><span class="sxs-lookup"><span data-stu-id="86fd6-161">If a client logs on to your provider more than once, you may want to register a different **MAPIUID** for each logon.</span></span> <span data-ttu-id="86fd6-162">注册唯一**MAPIUID**结构启用 MAPI 以正确将请求路由到相应的提供程序实例。</span><span class="sxs-lookup"><span data-stu-id="86fd6-162">Registering unique **MAPIUID** structures enables MAPI to correctly route requests to the appropriate provider instance.</span></span> <span data-ttu-id="86fd6-163">但是，您可能希望共享一个**MAPIUID**每个登录对象。</span><span class="sxs-lookup"><span data-stu-id="86fd6-163">However, you may want to have every logon object share one **MAPIUID**.</span></span> <span data-ttu-id="86fd6-164">在这种情况下，您必须能够处理路由而不是依赖 MAPI 自己。</span><span class="sxs-lookup"><span data-stu-id="86fd6-164">In this case, you must be able to handle the routing yourself instead of relying on MAPI.</span></span> <span data-ttu-id="86fd6-165">有关如何创建**MAPIUID**的详细信息，请参阅[注册服务提供程序唯一标识符](registering-service-provider-unique-identifiers.md)。</span><span class="sxs-lookup"><span data-stu-id="86fd6-165">For more information about how to create a **MAPIUID**, see [Registering Service Provider Unique Identifiers](registering-service-provider-unique-identifiers.md).</span></span>
  
<span data-ttu-id="86fd6-166">MAPI 将传递给_lpMAPISup_参数中您**登录**方法支持对象提供许多中包含的方法的访问[IMAPISupport: IUnknown](imapisupportiunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="86fd6-166">The support object that MAPI passes to your **Logon** method in the  _lpMAPISup_ parameter provides access to many of the methods included in the [IMAPISupport : IUnknown](imapisupportiunknown.md) interface.</span></span> <span data-ttu-id="86fd6-167">MAPI 创建支持对象为提供程序类型的自定义。</span><span class="sxs-lookup"><span data-stu-id="86fd6-167">MAPI creates a support object that is customized to your type of provider.</span></span> <span data-ttu-id="86fd6-168">例如，如果您需要登录到基础邮件系统或目录服务建立连接时，您可以调用[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)方法检索该特定登录会话的安全凭据。</span><span class="sxs-lookup"><span data-stu-id="86fd6-168">For example, if you need to log on to an underlying messaging system or directory service when you establish your connection, you can call the [IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md) method to retrieve security credentials for this particular logon session.</span></span> 
  
<span data-ttu-id="86fd6-169">如果成功**登录**，请确保您调用支持对象的[IUnknown::AddRef](http://msdn.microsoft.com/en-us/library/ms691379%28VS.85%29.aspx)方法，以增加引用计数。</span><span class="sxs-lookup"><span data-stu-id="86fd6-169">If **Logon** is successful, be sure that you call the support object's [IUnknown::AddRef](http://msdn.microsoft.com/en-us/library/ms691379%28VS.85%29.aspx) method to increment its reference count.</span></span> <span data-ttu-id="86fd6-170">这使您提供程序留会话的其余部分的支持对象指针。</span><span class="sxs-lookup"><span data-stu-id="86fd6-170">This enables your provider to hold onto the support object pointer for the rest of the session.</span></span> <span data-ttu-id="86fd6-171">如果您不调用此**AddRef**方法，MAPI 将卸载您的提供商。</span><span class="sxs-lookup"><span data-stu-id="86fd6-171">If you do not call this **AddRef** method, MAPI will unload your provider.</span></span> 
  
<span data-ttu-id="86fd6-172">您可以包括在错误对话框、 登录屏幕或其他用户界面中_lpszProfileName_参数中传递的配置文件名称。</span><span class="sxs-lookup"><span data-stu-id="86fd6-172">You can include the profile name passed in the  _lpszProfileName_ parameter in error dialog boxes, logon screens, or other user interfaces.</span></span> <span data-ttu-id="86fd6-173">若要使用的配置文件名称，将其复制到已分配的存储。</span><span class="sxs-lookup"><span data-stu-id="86fd6-173">To use the profile name, copy it to storage that you have allocated.</span></span> 
  
<span data-ttu-id="86fd6-174">创建登录对象并返回到此_lppABLogon_参数中的指针。</span><span class="sxs-lookup"><span data-stu-id="86fd6-174">Create a logon object and return a pointer to it in the  _lppABLogon_ parameter.</span></span> <span data-ttu-id="86fd6-175">MAPI 使用该登录对象以使在[IABLogon](iablogoniunknown.md)实现对方法的调用。</span><span class="sxs-lookup"><span data-stu-id="86fd6-175">MAPI uses this logon object to make calls to the methods in your [IABLogon](iablogoniunknown.md) implementation.</span></span> 
  
<span data-ttu-id="86fd6-176">如果您在登录过程中需要密码，显示登录对话框中，仅当未设置 AB_NO_DIALOG 标志。</span><span class="sxs-lookup"><span data-stu-id="86fd6-176">If you require a password during logon, display a logon dialog box only if the AB_NO_DIALOG flag is not set.</span></span> <span data-ttu-id="86fd6-177">如果用户取消了登录过程，通常通过单击对话框中的**取消**按钮返回 MAPI_E_USER_CANCEL 从**登录**。</span><span class="sxs-lookup"><span data-stu-id="86fd6-177">If the user cancels the logon process, typically by clicking the **Cancel** button in the dialog box, return MAPI_E_USER_CANCEL from **Logon**.</span></span>
  
<span data-ttu-id="86fd6-178">通常，当通讯簿提供程序不能登录，MAPI 禁用邮件服务的失败提供程序所属 — 即，MAPI 不会尝试建立连接的任何所属的会话的 rest 服务的其他提供程序生存期。</span><span class="sxs-lookup"><span data-stu-id="86fd6-178">Typically, when an address book provider cannot log on, MAPI disables the message service to which the failing provider belongs—that is, MAPI will not try to establish connections for any of the other providers that belong to the service for the rest of the session's lifetime.</span></span> <span data-ttu-id="86fd6-179">但是，如果您不希望禁用整个服务提供程序无法建立连接，返回 MAPI_E_FAILONEPROVIDER 或 MAPI_E_UNCONFIGURED。</span><span class="sxs-lookup"><span data-stu-id="86fd6-179">However, if your provider cannot establish a connection and you want not to disable the entire service, return either MAPI_E_FAILONEPROVIDER or MAPI_E_UNCONFIGURED.</span></span> <span data-ttu-id="86fd6-180">MAPI 不会禁用邮件服务提供程序所属。</span><span class="sxs-lookup"><span data-stu-id="86fd6-180">MAPI will not disable the message service to which the provider belongs.</span></span> 
  
<span data-ttu-id="86fd6-181">返回 MAPI_E_FAILONEPROVIDER 如果出现错误，则不严重，阻止邮件服务中的其他提供程序建立连接。</span><span class="sxs-lookup"><span data-stu-id="86fd6-181">Return MAPI_E_FAILONEPROVIDER if an error occurs that is not serious enough to prevent the other providers in the message service from establishing connections.</span></span> <span data-ttu-id="86fd6-182">如果从配置文件缺少必需的配置信息，您无法显示一个对话框，提示用户，则返回 MAPI_E_UNCONFIGURED。</span><span class="sxs-lookup"><span data-stu-id="86fd6-182">Return MAPI_E_UNCONFIGURED if the necessary configuration information is missing from the profile and you cannot display a dialog box to prompt the user.</span></span> <span data-ttu-id="86fd6-183">MAPI 将响应通过 MSG_SERVICE_CONFIGURE 设置提供程序的消息服务入口点函数调用作为_ulContext_参数以使服务本身，或者以编程方式配置有机会或使用属性表中。</span><span class="sxs-lookup"><span data-stu-id="86fd6-183">MAPI will respond by calling your provider's message service entry point function with MSG_SERVICE_CONFIGURE set as the  _ulContext_ parameter to give the service a chance to configure itself, either programmatically or using a property sheet.</span></span> <span data-ttu-id="86fd6-184">当邮件服务入口点函数已完成，MAPI 重试登录。</span><span class="sxs-lookup"><span data-stu-id="86fd6-184">When the message service entry point function has finished, MAPI retries the logon.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="86fd6-185">另请参阅</span><span class="sxs-lookup"><span data-stu-id="86fd6-185">See also</span></span>



[<span data-ttu-id="86fd6-186">IABLogon::Logoff</span><span class="sxs-lookup"><span data-stu-id="86fd6-186">IABLogon::Logoff</span></span>](iablogon-logoff.md)
  
[<span data-ttu-id="86fd6-187">IABLogon::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="86fd6-187">IABLogon::OpenEntry</span></span>](iablogon-openentry.md)
  
[<span data-ttu-id="86fd6-188">IMAPISupport::OpenProfileSection</span><span class="sxs-lookup"><span data-stu-id="86fd6-188">IMAPISupport::OpenProfileSection</span></span>](imapisupport-openprofilesection.md)
  
[<span data-ttu-id="86fd6-189">IMAPISupport::SetProviderUID</span><span class="sxs-lookup"><span data-stu-id="86fd6-189">IMAPISupport::SetProviderUID</span></span>](imapisupport-setprovideruid.md)
  
[<span data-ttu-id="86fd6-190">MSGSERVICEENTRY</span><span class="sxs-lookup"><span data-stu-id="86fd6-190">MSGSERVICEENTRY</span></span>](msgserviceentry.md)
  
[<span data-ttu-id="86fd6-191">IABProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="86fd6-191">IABProvider : IUnknown</span></span>](iabprovideriunknown.md)

