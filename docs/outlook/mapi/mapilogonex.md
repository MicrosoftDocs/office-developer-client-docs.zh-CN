---
title: MAPILogonEx
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPILogonEx
api_type:
- HeaderDef
ms.assetid: 98091e5b-1abd-4814-9c7a-583b420ee11d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: db76dfec27100a22785082580da70ecc2c10fc45
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579982"
---
# <a name="mapilogonex"></a><span data-ttu-id="4fddd-103">MAPILogonEx</span><span class="sxs-lookup"><span data-stu-id="4fddd-103">MAPILogonEx</span></span>

  
  
<span data-ttu-id="4fddd-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4fddd-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4fddd-105">记录到会话的客户端应用程序包含在邮件系统。</span><span class="sxs-lookup"><span data-stu-id="4fddd-105">Logs a client application on to a session with the messaging system.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="4fddd-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="4fddd-106">Header file:</span></span>  <br/> |<span data-ttu-id="4fddd-107">Mapix.h</span><span class="sxs-lookup"><span data-stu-id="4fddd-107">Mapix.h</span></span>  <br/> |
|<span data-ttu-id="4fddd-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="4fddd-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="4fddd-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="4fddd-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="4fddd-110">调用：</span><span class="sxs-lookup"><span data-stu-id="4fddd-110">Called by:</span></span>  <br/> |<span data-ttu-id="4fddd-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="4fddd-111">Client applications</span></span>  <br/> |
   
```cpp
HRESULT MAPILogonEx(
  ULONG_PTR ulUIParam,
  LPSTR lpszProfileName,
  LPSTR lpszPassword,
  FLAGS flFlags,
  LPMAPISESSION FAR * lppSession
);
```

## <a name="parameters"></a><span data-ttu-id="4fddd-112">参数</span><span class="sxs-lookup"><span data-stu-id="4fddd-112">Parameters</span></span>

 <span data-ttu-id="4fddd-113">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="4fddd-113">_ulUIParam_</span></span>
  
> <span data-ttu-id="4fddd-114">[in]到登录对话框是模式窗体窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="4fddd-114">[in] Handle to the window to which the logon dialog box is modal.</span></span> <span data-ttu-id="4fddd-115">如果在呼叫期间不出现任何对话框，则忽略_ulUIParam_参数。</span><span class="sxs-lookup"><span data-stu-id="4fddd-115">If no dialog box appears during the call, the  _ulUIParam_ parameter is ignored.</span></span> <span data-ttu-id="4fddd-116">此参数可以是零。</span><span class="sxs-lookup"><span data-stu-id="4fddd-116">This parameter can be zero.</span></span> 
    
 <span data-ttu-id="4fddd-117">_lpszProfileName_</span><span class="sxs-lookup"><span data-stu-id="4fddd-117">_lpszProfileName_</span></span>
  
> <span data-ttu-id="4fddd-118">[in]指向一个字符串，包含要在用户登录时使用的配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="4fddd-118">[in] Pointer to a string that contains the name of the profile to use when the user logs on.</span></span> <span data-ttu-id="4fddd-119">此字符串长度为 64 个字符限制。</span><span class="sxs-lookup"><span data-stu-id="4fddd-119">This string is limited to 64 characters.</span></span>
    
 <span data-ttu-id="4fddd-120">_lpszPassword_</span><span class="sxs-lookup"><span data-stu-id="4fddd-120">_lpszPassword_</span></span>
  
> <span data-ttu-id="4fddd-121">[in]指向一个字符串，包含配置文件的密码。</span><span class="sxs-lookup"><span data-stu-id="4fddd-121">[in] Pointer to a string that contains the password of the profile.</span></span> <span data-ttu-id="4fddd-122">_LpszPassword_参数必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="4fddd-122">The  _lpszPassword_ parameter must be NULL.</span></span> 
    
 <span data-ttu-id="4fddd-123">_flFlags_</span><span class="sxs-lookup"><span data-stu-id="4fddd-123">_flFlags_</span></span>
  
> <span data-ttu-id="4fddd-124">[in]用于控制如何执行登录的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="4fddd-124">[in] Bitmask of flags used to control how logon is performed.</span></span> <span data-ttu-id="4fddd-125">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="4fddd-125">The following flags can be set:</span></span>
    
<span data-ttu-id="4fddd-126">MAPI_ALLOW_OTHERS</span><span class="sxs-lookup"><span data-stu-id="4fddd-126">MAPI_ALLOW_OTHERS</span></span> 
  
> <span data-ttu-id="4fddd-127">应返回共享的会话，它允许更高版本的客户端可以获得该会话不需提供任何用户凭据。</span><span class="sxs-lookup"><span data-stu-id="4fddd-127">The shared session should be returned, which allows later clients to obtain the session without providing any user credentials.</span></span> 
    
<span data-ttu-id="4fddd-128">MAPI_BG_SESSION</span><span class="sxs-lookup"><span data-stu-id="4fddd-128">MAPI_BG_SESSION</span></span>
  
> <span data-ttu-id="4fddd-129">登录到会话，并在后台运行任何操作。</span><span class="sxs-lookup"><span data-stu-id="4fddd-129">Log on to a session and run any operations in the background.</span></span> <span data-ttu-id="4fddd-130">一般来说，如果打算执行后台线程上或在单独的进程中不到前台线程引人注目的方式处理客户端，它应与 MAPI_BG_SESSION 标志调用。</span><span class="sxs-lookup"><span data-stu-id="4fddd-130">In general, if a client intends to do processing on a background thread or in a separate process in a manner that is unobtrusive to the foreground thread, it should call with the MAPI_BG_SESSION flag.</span></span> <span data-ttu-id="4fddd-131">如索引引擎或打开背景类型访问个人文件夹文件 (PST) 的客户端应用程序是在何处使用 MAPI_BG_SESSION 的一些示例。MAPILogonEx。</span><span class="sxs-lookup"><span data-stu-id="4fddd-131">A client application such as an indexing engine or opening a Personal Folders File (PST) for background type access are some examples of where to use MAPI_BG_SESSION.MAPILogonEx.</span></span>
    
<span data-ttu-id="4fddd-132">MAPI_EXPLICIT_PROFILE</span><span class="sxs-lookup"><span data-stu-id="4fddd-132">MAPI_EXPLICIT_PROFILE</span></span> 
  
> <span data-ttu-id="4fddd-133">不应使用默认配置文件，并应要求用户提供一个配置文件。</span><span class="sxs-lookup"><span data-stu-id="4fddd-133">The default profile should not be used and the user should be required to supply a profile.</span></span> 
    
<span data-ttu-id="4fddd-134">MAPI_EXTENDED</span><span class="sxs-lookup"><span data-stu-id="4fddd-134">MAPI_EXTENDED</span></span> 
  
> <span data-ttu-id="4fddd-135">登录与扩展的功能。</span><span class="sxs-lookup"><span data-stu-id="4fddd-135">Log on with extended capabilities.</span></span> <span data-ttu-id="4fddd-136">此标志应始终设置。</span><span class="sxs-lookup"><span data-stu-id="4fddd-136">This flag should always be set.</span></span>
    
<span data-ttu-id="4fddd-137">MAPI_FORCE_DOWNLOAD</span><span class="sxs-lookup"><span data-stu-id="4fddd-137">MAPI_FORCE_DOWNLOAD</span></span> 
  
> <span data-ttu-id="4fddd-138">尝试应进行返回之前下载的所有用户的邮件。</span><span class="sxs-lookup"><span data-stu-id="4fddd-138">An attempt should be made to download all of the user's messages before returning.</span></span> <span data-ttu-id="4fddd-139">如果未设置 MAPI_FORCE_DOWNLOAD 标志，则后对 MAPILogonEx 的调用返回，在后台可以下载消息。</span><span class="sxs-lookup"><span data-stu-id="4fddd-139">If the MAPI_FORCE_DOWNLOAD flag is not set, messages can be downloaded in the background after the call to MAPILogonEx returns.</span></span> 
    
<span data-ttu-id="4fddd-140">MAPI_LOGON_UI</span><span class="sxs-lookup"><span data-stu-id="4fddd-140">MAPI_LOGON_UI</span></span> 
  
> <span data-ttu-id="4fddd-141">应显示一个对话框，提示用户输入登录信息，如果需要。</span><span class="sxs-lookup"><span data-stu-id="4fddd-141">A dialog box should be displayed to prompt the user for logon information if required.</span></span> <span data-ttu-id="4fddd-142">时未设置 MAPI_LOGON_UI 标志，调用客户端不显示登录对话框，并返回一个错误值，如果用户未登录。</span><span class="sxs-lookup"><span data-stu-id="4fddd-142">When the MAPI_LOGON_UI flag is not set, the calling client does not display a logon dialog box and returns an error value if the user is not logged on.</span></span>
    
<span data-ttu-id="4fddd-143">MAPI_NEW_SESSION</span><span class="sxs-lookup"><span data-stu-id="4fddd-143">MAPI_NEW_SESSION</span></span> 
  
> <span data-ttu-id="4fddd-144">尝试应进行创建一个新的 MAPI 会话，而不是获取共享的会话。</span><span class="sxs-lookup"><span data-stu-id="4fddd-144">An attempt should be made to create a new MAPI session instead of acquiring the shared session.</span></span> <span data-ttu-id="4fddd-145">如果未设置 MAPI_NEW_SESSION 标志，MAPILogonEx 使用现有共享的会话，即使_lpszprofileName_参数不是 NULL。</span><span class="sxs-lookup"><span data-stu-id="4fddd-145">If the MAPI_NEW_SESSION flag is not set, MAPILogonEx uses an existing shared session even if the  _lpszprofileName_ parameter is not NULL.</span></span> 
    
<span data-ttu-id="4fddd-146">MAPI_NO_MAIL</span><span class="sxs-lookup"><span data-stu-id="4fddd-146">MAPI_NO_MAIL</span></span> 
  
> <span data-ttu-id="4fddd-147">MAPI 不应告知该会话的存在 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="4fddd-147">MAPI should not inform the MAPI spooler of the session's existence.</span></span> <span data-ttu-id="4fddd-148">结果是可以发送或接收除了通过紧密耦合存储和传输对会话中任何消息。</span><span class="sxs-lookup"><span data-stu-id="4fddd-148">The result is that no messages can be sent or received in the session except through a tightly coupled store and transport pair.</span></span> <span data-ttu-id="4fddd-149">调用客户端设置此标志，如果它充当代理，如果必须完成的配置工作，或者如果客户端浏览可用的邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="4fddd-149">A calling client sets this flag if it is acting as an agent, if configuration work must be done, or if the client is browsing the available message stores.</span></span> 
    
<span data-ttu-id="4fddd-150">MAPI_NT_SERVICE</span><span class="sxs-lookup"><span data-stu-id="4fddd-150">MAPI_NT_SERVICE</span></span> 
  
> <span data-ttu-id="4fddd-151">呼叫者作为 Windows 服务运行。</span><span class="sxs-lookup"><span data-stu-id="4fddd-151">The caller is running as a Windows service.</span></span> <span data-ttu-id="4fddd-152">呼叫者的一项 Windows 服务不应设置此标志; 如未运行作为服务运行的呼叫者必须设置此标志。</span><span class="sxs-lookup"><span data-stu-id="4fddd-152">Callers that are not running as a Windows service should not set this flag; callers that are running as a service must set this flag.</span></span> 
    
<span data-ttu-id="4fddd-153">MAPI_SERVICE_UI_ALWAYS</span><span class="sxs-lookup"><span data-stu-id="4fddd-153">MAPI_SERVICE_UI_ALWAYS</span></span> 
  
> <span data-ttu-id="4fddd-154">MAPILogonEx 应显示配置文件中的每个消息服务的配置对话框。</span><span class="sxs-lookup"><span data-stu-id="4fddd-154">MAPILogonEx should display a configuration dialog box for each message service in the profile.</span></span> <span data-ttu-id="4fddd-155">已选中该配置文件，但任何消息之前服务登录后显示的对话框。</span><span class="sxs-lookup"><span data-stu-id="4fddd-155">The dialog boxes are displayed after the profile has been chosen but before any message service is logged on.</span></span> <span data-ttu-id="4fddd-156">登录的 MAPI 常见对话框还包含一个请求相同的操作的复选框。</span><span class="sxs-lookup"><span data-stu-id="4fddd-156">The MAPI common dialog box for logon also contains a check box that requests the same operation.</span></span> 
    
<span data-ttu-id="4fddd-157">MAPI_TIMEOUT_SHORT</span><span class="sxs-lookup"><span data-stu-id="4fddd-157">MAPI_TIMEOUT_SHORT</span></span> 
  
> <span data-ttu-id="4fddd-158">如果多个几秒钟阻止，则应该会失败登录。</span><span class="sxs-lookup"><span data-stu-id="4fddd-158">The logon should fail if blocked for more than a few seconds.</span></span> 
    
<span data-ttu-id="4fddd-159">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="4fddd-159">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="4fddd-160">传入的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="4fddd-160">The passed-in strings are in Unicode format.</span></span> <span data-ttu-id="4fddd-161">如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="4fddd-161">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span> 
    
<span data-ttu-id="4fddd-162">MAPI_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="4fddd-162">MAPI_USE_DEFAULT</span></span> 
  
> <span data-ttu-id="4fddd-163">邮件子系统应替换为_lpszProfileName_参数的默认配置文件的配置文件名称。</span><span class="sxs-lookup"><span data-stu-id="4fddd-163">The messaging subsystem should substitute the profile name of the default profile for the  _lpszProfileName_ parameter.</span></span> <span data-ttu-id="4fddd-164">除非_lpszProfileName_为 NULL 或空，则忽略 MAPI_EXPLICIT_PROFILE 标志。</span><span class="sxs-lookup"><span data-stu-id="4fddd-164">The MAPI_EXPLICIT_PROFILE flag is ignored unless  _lpszProfileName_ is NULL or empty.</span></span> 
    
 <span data-ttu-id="4fddd-165">_lppSession_</span><span class="sxs-lookup"><span data-stu-id="4fddd-165">_lppSession_</span></span>
  
> <span data-ttu-id="4fddd-166">[输出]为指向 MAPI 会话接口的指针。</span><span class="sxs-lookup"><span data-stu-id="4fddd-166">[out] Pointer to a pointer to the MAPI session interface.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="4fddd-167">返回值</span><span class="sxs-lookup"><span data-stu-id="4fddd-167">Return value</span></span>

<span data-ttu-id="4fddd-168">S_OK</span><span class="sxs-lookup"><span data-stu-id="4fddd-168">S_OK</span></span> 
  
> <span data-ttu-id="4fddd-169">登录成功。</span><span class="sxs-lookup"><span data-stu-id="4fddd-169">The logon succeeded.</span></span>
    
<span data-ttu-id="4fddd-170">MAPI_E_LOGON_FAILED</span><span class="sxs-lookup"><span data-stu-id="4fddd-170">MAPI_E_LOGON_FAILED</span></span> 
  
> <span data-ttu-id="4fddd-171">登录成功，因为一个或多个 MAPILogonEx 的参数无效或因太多的会话打开已。</span><span class="sxs-lookup"><span data-stu-id="4fddd-171">The logon was unsuccessful, either because one or more of the parameters to MAPILogonEx were invalid or because there were too many sessions open already.</span></span>
    
<span data-ttu-id="4fddd-172">MAPI_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4fddd-172">MAPI_E_TIMEOUT</span></span> 
  
> <span data-ttu-id="4fddd-173">MAPI 序列化通过互斥体的所有登录。</span><span class="sxs-lookup"><span data-stu-id="4fddd-173">MAPI serializes all logons through a mutex.</span></span> <span data-ttu-id="4fddd-174">如果设置了 MAPI_TIMEOUT_SHORT 标志和另一个线程保留互斥体，这将返回。</span><span class="sxs-lookup"><span data-stu-id="4fddd-174">This is returned if the MAPI_TIMEOUT_SHORT flag was set and another thread held the mutex.</span></span> 
    
<span data-ttu-id="4fddd-175">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="4fddd-175">MAPI_E_USER_CANCEL</span></span> 
  
> <span data-ttu-id="4fddd-176">用户取消操作，通常通过单击对话框中的**取消**按钮。</span><span class="sxs-lookup"><span data-stu-id="4fddd-176">The user canceled the operation, typically by clicking the **Cancel** button in a dialog box.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="4fddd-177">注解</span><span class="sxs-lookup"><span data-stu-id="4fddd-177">Remarks</span></span>

<span data-ttu-id="4fddd-178">MAPI 客户端应用程序调用 MAPILogonEx 函数登录到与邮件系统的会话。</span><span class="sxs-lookup"><span data-stu-id="4fddd-178">MAPI client applications call the MAPILogonEx function to log on to a session with the messaging system.</span></span> <span data-ttu-id="4fddd-179">所有字符串中传递并返回与 MAPI 调用 null 结尾并且必须指定以当前字符集或代码页的呼叫的客户端或提供程序的操作系统。</span><span class="sxs-lookup"><span data-stu-id="4fddd-179">All strings that are passed in and returned to and from MAPI calls are null-terminated and must be specified in the current character set or code page of the calling client or provider's operating system.</span></span>
  
<span data-ttu-id="4fddd-180">如果设置了 MAPI_ALLOW_OTHERS 标志调用 MapiLogonEx 现有以前会话和未设置标志 MAPI_NEW_SESSION 忽略_lpszProfileName_参数。</span><span class="sxs-lookup"><span data-stu-id="4fddd-180">The  _lpszProfileName_ parameter is ignored if there is an existing previous session that called MapiLogonEx with the MAPI_ALLOW_OTHERS flag set and if the flag MAPI_NEW_SESSION is not set.</span></span> <span data-ttu-id="4fddd-181">如果_lpszProfileName_参数为 NULL 或空字符串和_flFlags_参数指向包含 MAPI_LOGON_UI 标志，MAPILogonEx 函数将生成具有的配置文件名称的字段为空登录对话框。</span><span class="sxs-lookup"><span data-stu-id="4fddd-181">If the  _lpszProfileName_ parameter is NULL or points to an empty string, and the  _flFlags_ parameter includes the MAPI_LOGON_UI flag, the MAPILogonEx function generates a logon dialog box that has an empty field for the profile name.</span></span> 
  
<span data-ttu-id="4fddd-182">在登录到特定配置文件时, 客户端应将传递 MAPI_NEW_SESSION 标志到 MAPILogonEx 除了的配置文件名称。</span><span class="sxs-lookup"><span data-stu-id="4fddd-182">When logging on to a specific profile, a client should pass the MAPI_NEW_SESSION flag into MAPILogonEx in addition to the profile name.</span></span> <span data-ttu-id="4fddd-183">否则，如果另一个客户端的登录与 MAPI_ALLOW_OTHERS 建立共享的会话，客户端将登录到请求的配置文件而不是将共享会话。</span><span class="sxs-lookup"><span data-stu-id="4fddd-183">Otherwise, if another client has established a shared session by logging on with MAPI_ALLOW_OTHERS, the client will be logged on to the shared session instead of to the profile requested.</span></span> 
  
<span data-ttu-id="4fddd-184">MAPI_EXPLICIT_PROFILE 标志不会导致_lpszProfileName_为 NULL 时要使用的默认配置文件名称或为空，除非也存在 MAPI_USE_DEFAULT 标志。</span><span class="sxs-lookup"><span data-stu-id="4fddd-184">The MAPI_EXPLICIT_PROFILE flag does not cause the default profile name to be used when  _lpszProfileName_ is NULL or empty unless the MAPI_USE_DEFAULT flag is also present.</span></span> 
  
<span data-ttu-id="4fddd-185">MAPI_NO_MAIL 标志具有不使用 MAPI 后台处理程序时，会导致以下几种效果：</span><span class="sxs-lookup"><span data-stu-id="4fddd-185">The MAPI_NO_MAIL flag has several effects that cause the following when not using the MAPI spooler:</span></span>
  
- <span data-ttu-id="4fddd-186">可以发送或此会话期间发送 MAPI 后台处理程序的任何消息。</span><span class="sxs-lookup"><span data-stu-id="4fddd-186">No messages can be sent or delivered by the MAPI spooler during this session.</span></span> <span data-ttu-id="4fddd-187">仅紧密耦合的存储和传输提供程序可以发送和邮件传递。</span><span class="sxs-lookup"><span data-stu-id="4fddd-187">Only tightly coupled store and transport providers can send and deliver messages.</span></span> 
    
- <span data-ttu-id="4fddd-188">基于服务器存储可能仍发送，或将邮件传递。</span><span class="sxs-lookup"><span data-stu-id="4fddd-188">Server based stores might still send or deliver messages.</span></span> 
    
- <span data-ttu-id="4fddd-189">发送或基于服务器存储的邮件将不会执行任何挂接提供商。</span><span class="sxs-lookup"><span data-stu-id="4fddd-189">Messages sent or delivered by server based stores are not processed by any hook providers.</span></span> 
    
- <span data-ttu-id="4fddd-190">传输的每封邮件和每个收件人选项不可用。</span><span class="sxs-lookup"><span data-stu-id="4fddd-190">Per-message and per-recipient options for transports are not available.</span></span> 
    
- <span data-ttu-id="4fddd-191">状态表中不包含传输提供程序的条目和依赖于状态对象 （如配置） 在任何传输功能不可用。</span><span class="sxs-lookup"><span data-stu-id="4fddd-191">The status table does not contain entries for transport providers, and any transport functionality dependent on status objects (such as configuration) is not available.</span></span> 
    
- <span data-ttu-id="4fddd-192">状态表中的邮件后台处理程序行包含 STATUS_FAILURE 值。</span><span class="sxs-lookup"><span data-stu-id="4fddd-192">The message spooler row in the status table contains the STATUS_FAILURE value.</span></span> 
    
- <span data-ttu-id="4fddd-193">允许随附加的登录，但这些登录不会导致一次登录以接收对象的状态更新。</span><span class="sxs-lookup"><span data-stu-id="4fddd-193">Piggybacked logons are allowed, but those logons do not cause the previous logon to receive status object updates.</span></span> 
    
<span data-ttu-id="4fddd-194">服务应始终使用登录 MAPI_NO_MAIL 标志。</span><span class="sxs-lookup"><span data-stu-id="4fddd-194">A service should always log on using the MAPI_NO_MAIL flag.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="4fddd-195">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="4fddd-195">MFCMAPI reference</span></span>

<span data-ttu-id="4fddd-196">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="4fddd-196">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="4fddd-197">**文件**</span><span class="sxs-lookup"><span data-stu-id="4fddd-197">**File**</span></span>|<span data-ttu-id="4fddd-198">**函数**</span><span class="sxs-lookup"><span data-stu-id="4fddd-198">**Function**</span></span>|<span data-ttu-id="4fddd-199">**Comment**</span><span class="sxs-lookup"><span data-stu-id="4fddd-199">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4fddd-200">MAPIObjects.cpp</span><span class="sxs-lookup"><span data-stu-id="4fddd-200">MAPIObjects.cpp</span></span>  <br/> |<span data-ttu-id="4fddd-201">CMapiObjects::MAPILogonEx</span><span class="sxs-lookup"><span data-stu-id="4fddd-201">CMapiObjects::MAPILogonEx</span></span>  <br/> |<span data-ttu-id="4fddd-202">MFCMAPI 使用 MAPILogonEx 方法登录到 MAPI。</span><span class="sxs-lookup"><span data-stu-id="4fddd-202">MFCMAPI uses the MAPILogonEx method to log on to MAPI.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="4fddd-203">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4fddd-203">See also</span></span>



[<span data-ttu-id="4fddd-204">IMAPISession::GetMsgStoresTable</span><span class="sxs-lookup"><span data-stu-id="4fddd-204">IMAPISession::GetMsgStoresTable</span></span>](imapisession-getmsgstorestable.md)
  
[<span data-ttu-id="4fddd-205">IMAPISession::OpenMsgStore</span><span class="sxs-lookup"><span data-stu-id="4fddd-205">IMAPISession::OpenMsgStore</span></span>](imapisession-openmsgstore.md)


[<span data-ttu-id="4fddd-206">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="4fddd-206">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

