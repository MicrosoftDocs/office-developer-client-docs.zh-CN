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
ms.openlocfilehash: 9f2ec8f0ec00f7314982e9b112415f69901c358c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424117"
---
# <a name="mapilogonex"></a><span data-ttu-id="cadc0-103">MAPILogonEx</span><span class="sxs-lookup"><span data-stu-id="cadc0-103">MAPILogonEx</span></span>

  
  
<span data-ttu-id="cadc0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cadc0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cadc0-105">将客户端应用程序记录到邮件系统的会话中。</span><span class="sxs-lookup"><span data-stu-id="cadc0-105">Logs a client application on to a session with the messaging system.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="cadc0-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="cadc0-106">Header file:</span></span>  <br/> |<span data-ttu-id="cadc0-107">Mapix</span><span class="sxs-lookup"><span data-stu-id="cadc0-107">Mapix.h</span></span>  <br/> |
|<span data-ttu-id="cadc0-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="cadc0-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="cadc0-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="cadc0-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="cadc0-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="cadc0-110">Called by:</span></span>  <br/> |<span data-ttu-id="cadc0-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="cadc0-111">Client applications</span></span>  <br/> |
   
```cpp
HRESULT MAPILogonEx(
  ULONG_PTR ulUIParam,
  LPSTR lpszProfileName,
  LPSTR lpszPassword,
  FLAGS flFlags,
  LPMAPISESSION FAR * lppSession
);
```

## <a name="parameters"></a><span data-ttu-id="cadc0-112">参数</span><span class="sxs-lookup"><span data-stu-id="cadc0-112">Parameters</span></span>

 <span data-ttu-id="cadc0-113">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="cadc0-113">_ulUIParam_</span></span>
  
> <span data-ttu-id="cadc0-114">实时指向登录对话框模式的窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="cadc0-114">[in] Handle to the window to which the logon dialog box is modal.</span></span> <span data-ttu-id="cadc0-115">如果在呼叫过程中不显示任何对话框, 则忽略_ulUIParam_参数。</span><span class="sxs-lookup"><span data-stu-id="cadc0-115">If no dialog box appears during the call, the  _ulUIParam_ parameter is ignored.</span></span> <span data-ttu-id="cadc0-116">此参数可以为零。</span><span class="sxs-lookup"><span data-stu-id="cadc0-116">This parameter can be zero.</span></span> 
    
 <span data-ttu-id="cadc0-117">_lpszProfileName_</span><span class="sxs-lookup"><span data-stu-id="cadc0-117">_lpszProfileName_</span></span>
  
> <span data-ttu-id="cadc0-118">实时指向一个字符串的指针, 该字符串包含要在用户登录时使用的配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="cadc0-118">[in] Pointer to a string that contains the name of the profile to use when the user logs on.</span></span> <span data-ttu-id="cadc0-119">此字符串长度为 64 个字符限制。</span><span class="sxs-lookup"><span data-stu-id="cadc0-119">This string is limited to 64 characters.</span></span>
    
 <span data-ttu-id="cadc0-120">_lpszPassword_</span><span class="sxs-lookup"><span data-stu-id="cadc0-120">_lpszPassword_</span></span>
  
> <span data-ttu-id="cadc0-121">实时指向包含配置文件密码的字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="cadc0-121">[in] Pointer to a string that contains the password of the profile.</span></span> <span data-ttu-id="cadc0-122">_lpszPassword_参数必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="cadc0-122">The  _lpszPassword_ parameter must be NULL.</span></span> 
    
 <span data-ttu-id="cadc0-123">_flFlags_</span><span class="sxs-lookup"><span data-stu-id="cadc0-123">_flFlags_</span></span>
  
> <span data-ttu-id="cadc0-124">实时用于控制登录执行方式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="cadc0-124">[in] Bitmask of flags used to control how logon is performed.</span></span> <span data-ttu-id="cadc0-125">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="cadc0-125">The following flags can be set:</span></span>
    
<span data-ttu-id="cadc0-126">MAPI_ALLOW_OTHERS</span><span class="sxs-lookup"><span data-stu-id="cadc0-126">MAPI_ALLOW_OTHERS</span></span> 
  
> <span data-ttu-id="cadc0-127">应返回共享会话, 这样以后客户端无需提供任何用户凭据即可获取会话。</span><span class="sxs-lookup"><span data-stu-id="cadc0-127">The shared session should be returned, which allows later clients to obtain the session without providing any user credentials.</span></span> 
    
<span data-ttu-id="cadc0-128">MAPI_BG_SESSION</span><span class="sxs-lookup"><span data-stu-id="cadc0-128">MAPI_BG_SESSION</span></span>
  
> <span data-ttu-id="cadc0-129">登录到会话并在后台运行任何操作。</span><span class="sxs-lookup"><span data-stu-id="cadc0-129">Log on to a session and run any operations in the background.</span></span> <span data-ttu-id="cadc0-130">通常情况下, 如果客户端打算在后台线程上或在单独的进程中以与前台线程不引人注目的方式进行处理, 则应使用 MAPI_BG_SESSION 标志进行调用。</span><span class="sxs-lookup"><span data-stu-id="cadc0-130">In general, if a client intends to do processing on a background thread or in a separate process in a manner that is unobtrusive to the foreground thread, it should call with the MAPI_BG_SESSION flag.</span></span> <span data-ttu-id="cadc0-131">用于后台类型访问的客户端应用程序 (如索引引擎或打开个人文件夹文件 (PST)) 是使用 MAPI_BG_SESSION 的一些示例。MAPILogonEx。</span><span class="sxs-lookup"><span data-stu-id="cadc0-131">A client application such as an indexing engine or opening a Personal Folders File (PST) for background type access are some examples of where to use MAPI_BG_SESSION.MAPILogonEx.</span></span>
    
<span data-ttu-id="cadc0-132">MAPI_EXPLICIT_PROFILE</span><span class="sxs-lookup"><span data-stu-id="cadc0-132">MAPI_EXPLICIT_PROFILE</span></span> 
  
> <span data-ttu-id="cadc0-133">不应使用默认配置文件, 应要求用户提供配置文件。</span><span class="sxs-lookup"><span data-stu-id="cadc0-133">The default profile should not be used and the user should be required to supply a profile.</span></span> 
    
<span data-ttu-id="cadc0-134">MAPI_EXTENDED</span><span class="sxs-lookup"><span data-stu-id="cadc0-134">MAPI_EXTENDED</span></span> 
  
> <span data-ttu-id="cadc0-135">使用扩展的功能进行登录。</span><span class="sxs-lookup"><span data-stu-id="cadc0-135">Log on with extended capabilities.</span></span> <span data-ttu-id="cadc0-136">应始终设置此标志。</span><span class="sxs-lookup"><span data-stu-id="cadc0-136">This flag should always be set.</span></span>
    
<span data-ttu-id="cadc0-137">MAPI_FORCE_DOWNLOAD</span><span class="sxs-lookup"><span data-stu-id="cadc0-137">MAPI_FORCE_DOWNLOAD</span></span> 
  
> <span data-ttu-id="cadc0-138">应在返回前尝试下载用户的所有邮件。</span><span class="sxs-lookup"><span data-stu-id="cadc0-138">An attempt should be made to download all of the user's messages before returning.</span></span> <span data-ttu-id="cadc0-139">如果未设置 MAPI_FORCE_DOWNLOAD 标志, 则在调用 MAPILogonEx 后, 可以在后台下载邮件。</span><span class="sxs-lookup"><span data-stu-id="cadc0-139">If the MAPI_FORCE_DOWNLOAD flag is not set, messages can be downloaded in the background after the call to MAPILogonEx returns.</span></span> 
    
<span data-ttu-id="cadc0-140">MAPI_LOGON_UI</span><span class="sxs-lookup"><span data-stu-id="cadc0-140">MAPI_LOGON_UI</span></span> 
  
> <span data-ttu-id="cadc0-141">应显示一个对话框, 提示用户输入登录信息 (如果需要)。</span><span class="sxs-lookup"><span data-stu-id="cadc0-141">A dialog box should be displayed to prompt the user for logon information if required.</span></span> <span data-ttu-id="cadc0-142">如果未设置 MAPI_LOGON_UI 标志, 则调用客户端不会显示登录对话框, 并会在用户未登录时返回一个错误值。</span><span class="sxs-lookup"><span data-stu-id="cadc0-142">When the MAPI_LOGON_UI flag is not set, the calling client does not display a logon dialog box and returns an error value if the user is not logged on.</span></span>
    
<span data-ttu-id="cadc0-143">MAPI_NEW_SESSION</span><span class="sxs-lookup"><span data-stu-id="cadc0-143">MAPI_NEW_SESSION</span></span> 
  
> <span data-ttu-id="cadc0-144">应尝试创建新的 MAPI 会话, 而不是获取共享会话。</span><span class="sxs-lookup"><span data-stu-id="cadc0-144">An attempt should be made to create a new MAPI session instead of acquiring the shared session.</span></span> <span data-ttu-id="cadc0-145">如果未设置 MAPI_NEW_SESSION 标志, 则 MAPILogonEx 将使用现有共享会话, 即使_lpszprofileName_参数不为 NULL 也是如此。</span><span class="sxs-lookup"><span data-stu-id="cadc0-145">If the MAPI_NEW_SESSION flag is not set, MAPILogonEx uses an existing shared session even if the  _lpszprofileName_ parameter is not NULL.</span></span> 
    
<span data-ttu-id="cadc0-146">MAPI_NO_MAIL</span><span class="sxs-lookup"><span data-stu-id="cadc0-146">MAPI_NO_MAIL</span></span> 
  
> <span data-ttu-id="cadc0-147">mapi 不应通知 mapi 后台处理程序存在该会话。</span><span class="sxs-lookup"><span data-stu-id="cadc0-147">MAPI should not inform the MAPI spooler of the session's existence.</span></span> <span data-ttu-id="cadc0-148">结果是, 不能在会话中发送或接收邮件, 除非通过紧密耦合的存储和传输对。</span><span class="sxs-lookup"><span data-stu-id="cadc0-148">The result is that no messages can be sent or received in the session except through a tightly coupled store and transport pair.</span></span> <span data-ttu-id="cadc0-149">如果呼叫客户端正在充当代理 (如果必须完成配置工作, 或者客户端正在浏览可用的邮件存储), 则呼叫客户端将设置此标志。</span><span class="sxs-lookup"><span data-stu-id="cadc0-149">A calling client sets this flag if it is acting as an agent, if configuration work must be done, or if the client is browsing the available message stores.</span></span> 
    
<span data-ttu-id="cadc0-150">MAPI_NT_SERVICE</span><span class="sxs-lookup"><span data-stu-id="cadc0-150">MAPI_NT_SERVICE</span></span> 
  
> <span data-ttu-id="cadc0-151">调用方以 Windows 服务的形式运行。</span><span class="sxs-lookup"><span data-stu-id="cadc0-151">The caller is running as a Windows service.</span></span> <span data-ttu-id="cadc0-152">未作为 Windows 服务运行的调用方不应设置此标志;作为服务运行的调用方必须设置此标志。</span><span class="sxs-lookup"><span data-stu-id="cadc0-152">Callers that are not running as a Windows service should not set this flag; callers that are running as a service must set this flag.</span></span> 
    
<span data-ttu-id="cadc0-153">MAPI_SERVICE_UI_ALWAYS</span><span class="sxs-lookup"><span data-stu-id="cadc0-153">MAPI_SERVICE_UI_ALWAYS</span></span> 
  
> <span data-ttu-id="cadc0-154">MAPILogonEx 应为配置文件中的每个邮件服务显示一个 "配置" 对话框。</span><span class="sxs-lookup"><span data-stu-id="cadc0-154">MAPILogonEx should display a configuration dialog box for each message service in the profile.</span></span> <span data-ttu-id="cadc0-155">在选择了配置文件之后, 但在任何邮件服务登录之前, 都会显示对话框。</span><span class="sxs-lookup"><span data-stu-id="cadc0-155">The dialog boxes are displayed after the profile has been chosen but before any message service is logged on.</span></span> <span data-ttu-id="cadc0-156">用于登录的 MAPI 通用对话框还包含一个请求同一操作的复选框。</span><span class="sxs-lookup"><span data-stu-id="cadc0-156">The MAPI common dialog box for logon also contains a check box that requests the same operation.</span></span> 
    
<span data-ttu-id="cadc0-157">MAPI_TIMEOUT_SHORT</span><span class="sxs-lookup"><span data-stu-id="cadc0-157">MAPI_TIMEOUT_SHORT</span></span> 
  
> <span data-ttu-id="cadc0-158">如果被阻止了数秒以上, 则登录应该会失败。</span><span class="sxs-lookup"><span data-stu-id="cadc0-158">The logon should fail if blocked for more than a few seconds.</span></span> 
    
<span data-ttu-id="cadc0-159">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="cadc0-159">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="cadc0-160">传入的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="cadc0-160">The passed-in strings are in Unicode format.</span></span> <span data-ttu-id="cadc0-161">如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="cadc0-161">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span> 
    
<span data-ttu-id="cadc0-162">MAPI_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="cadc0-162">MAPI_USE_DEFAULT</span></span> 
  
> <span data-ttu-id="cadc0-163">邮件传递子系统应替换_lpszProfileName_参数的默认配置文件的配置文件名称。</span><span class="sxs-lookup"><span data-stu-id="cadc0-163">The messaging subsystem should substitute the profile name of the default profile for the  _lpszProfileName_ parameter.</span></span> <span data-ttu-id="cadc0-164">除非_lpszProfileName_为 NULL 或为空, 否则将忽略 MAPI_EXPLICIT_PROFILE 标志。</span><span class="sxs-lookup"><span data-stu-id="cadc0-164">The MAPI_EXPLICIT_PROFILE flag is ignored unless  _lpszProfileName_ is NULL or empty.</span></span> 
    
 <span data-ttu-id="cadc0-165">_lppSession_</span><span class="sxs-lookup"><span data-stu-id="cadc0-165">_lppSession_</span></span>
  
> <span data-ttu-id="cadc0-166">排除指向 MAPI 会话接口的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="cadc0-166">[out] Pointer to a pointer to the MAPI session interface.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="cadc0-167">返回值</span><span class="sxs-lookup"><span data-stu-id="cadc0-167">Return value</span></span>

<span data-ttu-id="cadc0-168">S_OK</span><span class="sxs-lookup"><span data-stu-id="cadc0-168">S_OK</span></span> 
  
> <span data-ttu-id="cadc0-169">登录成功。</span><span class="sxs-lookup"><span data-stu-id="cadc0-169">The logon succeeded.</span></span>
    
<span data-ttu-id="cadc0-170">MAPI_E_LOGON_FAILED</span><span class="sxs-lookup"><span data-stu-id="cadc0-170">MAPI_E_LOGON_FAILED</span></span> 
  
> <span data-ttu-id="cadc0-171">登录失败, 可能是因为一个或多个 MAPILogonEx 参数无效, 或者因为已打开的会话过多。</span><span class="sxs-lookup"><span data-stu-id="cadc0-171">The logon was unsuccessful, either because one or more of the parameters to MAPILogonEx were invalid or because there were too many sessions open already.</span></span>
    
<span data-ttu-id="cadc0-172">MAPI_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cadc0-172">MAPI_E_TIMEOUT</span></span> 
  
> <span data-ttu-id="cadc0-173">MAPI 通过 mutex 序列化所有登录。</span><span class="sxs-lookup"><span data-stu-id="cadc0-173">MAPI serializes all logons through a mutex.</span></span> <span data-ttu-id="cadc0-174">如果设置了 MAPI_TIMEOUT_SHORT 标志, 而另一个线程持有互斥体, 则将返回此设置。</span><span class="sxs-lookup"><span data-stu-id="cadc0-174">This is returned if the MAPI_TIMEOUT_SHORT flag was set and another thread held the mutex.</span></span> 
    
<span data-ttu-id="cadc0-175">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="cadc0-175">MAPI_E_USER_CANCEL</span></span> 
  
> <span data-ttu-id="cadc0-176">用户取消了操作, 通常是单击对话框中的 "**取消**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="cadc0-176">The user canceled the operation, typically by clicking the **Cancel** button in a dialog box.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="cadc0-177">说明</span><span class="sxs-lookup"><span data-stu-id="cadc0-177">Remarks</span></span>

<span data-ttu-id="cadc0-178">MAPI 客户端应用程序调用 MAPILogonEx 函数, 以登录到邮件系统的会话。</span><span class="sxs-lookup"><span data-stu-id="cadc0-178">MAPI client applications call the MAPILogonEx function to log on to a session with the messaging system.</span></span> <span data-ttu-id="cadc0-179">传入和返回 MAPI 调用的所有字符串都以空值终止, 并且必须在当前的字符集或调用客户端或提供程序的操作系统的 "代码" 页中指定。</span><span class="sxs-lookup"><span data-stu-id="cadc0-179">All strings that are passed in and returned to and from MAPI calls are null-terminated and must be specified in the current character set or code page of the calling client or provider's operating system.</span></span>
  
<span data-ttu-id="cadc0-180">如果现有的前一个会话已设置 MAPI_ALLOW_OTHERS 标志, 且未设置标志 MAPI_NEW_SESSION, 则将忽略_lpszProfileName_参数。</span><span class="sxs-lookup"><span data-stu-id="cadc0-180">The  _lpszProfileName_ parameter is ignored if there is an existing previous session that called MapiLogonEx with the MAPI_ALLOW_OTHERS flag set and if the flag MAPI_NEW_SESSION is not set.</span></span> <span data-ttu-id="cadc0-181">如果_lpszProfileName_参数为 NULL 或指向一个空字符串, 并且_flFlags_参数包含 MAPI_LOGON_UI 标志, 则 MAPILogonEx 函数将生成一个登录对话框, 其中包含配置文件名称的空字段。</span><span class="sxs-lookup"><span data-stu-id="cadc0-181">If the  _lpszProfileName_ parameter is NULL or points to an empty string, and the  _flFlags_ parameter includes the MAPI_LOGON_UI flag, the MAPILogonEx function generates a logon dialog box that has an empty field for the profile name.</span></span> 
  
<span data-ttu-id="cadc0-182">登录到特定配置文件时, 除了配置文件名称之外, 客户端还应将 MAPI_NEW_SESSION 标志传递给 MAPILogonEx。</span><span class="sxs-lookup"><span data-stu-id="cadc0-182">When logging on to a specific profile, a client should pass the MAPI_NEW_SESSION flag into MAPILogonEx in addition to the profile name.</span></span> <span data-ttu-id="cadc0-183">否则, 如果另一个客户端通过使用 MAPI_ALLOW_OTHERS 登录来建立共享会话, 客户端将登录到共享会话, 而不是所请求的配置文件。</span><span class="sxs-lookup"><span data-stu-id="cadc0-183">Otherwise, if another client has established a shared session by logging on with MAPI_ALLOW_OTHERS, the client will be logged on to the shared session instead of to the profile requested.</span></span> 
  
<span data-ttu-id="cadc0-184">如果_lpszProfileName_为 NULL 或为空, 则 MAPI_EXPLICIT_PROFILE 标志不会导致使用默认配置文件名称, 除非同时也存在 MAPI_USE_DEFAULT 标志。</span><span class="sxs-lookup"><span data-stu-id="cadc0-184">The MAPI_EXPLICIT_PROFILE flag does not cause the default profile name to be used when  _lpszProfileName_ is NULL or empty unless the MAPI_USE_DEFAULT flag is also present.</span></span> 
  
<span data-ttu-id="cadc0-185">在不使用 MAPI 后台处理程序的情况下, MAPI_NO_MAIL 标志有几个导致以下影响的效果:</span><span class="sxs-lookup"><span data-stu-id="cadc0-185">The MAPI_NO_MAIL flag has several effects that cause the following when not using the MAPI spooler:</span></span>
  
- <span data-ttu-id="cadc0-186">在此会话期间, MAPI 后台处理程序无法发送或传递任何邮件。</span><span class="sxs-lookup"><span data-stu-id="cadc0-186">No messages can be sent or delivered by the MAPI spooler during this session.</span></span> <span data-ttu-id="cadc0-187">仅紧密耦合的存储和传输提供程序可以发送和传递邮件。</span><span class="sxs-lookup"><span data-stu-id="cadc0-187">Only tightly coupled store and transport providers can send and deliver messages.</span></span> 
    
- <span data-ttu-id="cadc0-188">基于服务器的存储可能仍在发送或传递邮件。</span><span class="sxs-lookup"><span data-stu-id="cadc0-188">Server based stores might still send or deliver messages.</span></span> 
    
- <span data-ttu-id="cadc0-189">任何挂钩提供程序都不处理由基于服务器的存储区发送或传递的邮件。</span><span class="sxs-lookup"><span data-stu-id="cadc0-189">Messages sent or delivered by server based stores are not processed by any hook providers.</span></span> 
    
- <span data-ttu-id="cadc0-190">传输的每个邮件和每个收件人的选项都不可用。</span><span class="sxs-lookup"><span data-stu-id="cadc0-190">Per-message and per-recipient options for transports are not available.</span></span> 
    
- <span data-ttu-id="cadc0-191">状态表不包含传输提供程序的条目, 且依赖于状态对象的任何传输功能 (如配置) 不可用。</span><span class="sxs-lookup"><span data-stu-id="cadc0-191">The status table does not contain entries for transport providers, and any transport functionality dependent on status objects (such as configuration) is not available.</span></span> 
    
- <span data-ttu-id="cadc0-192">状态表中的邮件后台打印程序行包含 STATUS_FAILURE 值。</span><span class="sxs-lookup"><span data-stu-id="cadc0-192">The message spooler row in the status table contains the STATUS_FAILURE value.</span></span> 
    
- <span data-ttu-id="cadc0-193">允许 Piggybacked 登录, 但这些登录不会导致以前的登录接收状态对象更新。</span><span class="sxs-lookup"><span data-stu-id="cadc0-193">Piggybacked logons are allowed, but those logons do not cause the previous logon to receive status object updates.</span></span> 
    
<span data-ttu-id="cadc0-194">服务应始终使用 MAPI_NO_MAIL 标志进行登录。</span><span class="sxs-lookup"><span data-stu-id="cadc0-194">A service should always log on using the MAPI_NO_MAIL flag.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="cadc0-195">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="cadc0-195">MFCMAPI reference</span></span>

<span data-ttu-id="cadc0-196">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="cadc0-196">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="cadc0-197">**文件**</span><span class="sxs-lookup"><span data-stu-id="cadc0-197">**File**</span></span>|<span data-ttu-id="cadc0-198">**函数**</span><span class="sxs-lookup"><span data-stu-id="cadc0-198">**Function**</span></span>|<span data-ttu-id="cadc0-199">**备注**</span><span class="sxs-lookup"><span data-stu-id="cadc0-199">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cadc0-200">MAPIObjects</span><span class="sxs-lookup"><span data-stu-id="cadc0-200">MAPIObjects.cpp</span></span>  <br/> |<span data-ttu-id="cadc0-201">CMapiObjects:: MAPILogonEx</span><span class="sxs-lookup"><span data-stu-id="cadc0-201">CMapiObjects::MAPILogonEx</span></span>  <br/> |<span data-ttu-id="cadc0-202">MFCMAPI 使用 MAPILogonEx 方法登录 MAPI。</span><span class="sxs-lookup"><span data-stu-id="cadc0-202">MFCMAPI uses the MAPILogonEx method to log on to MAPI.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="cadc0-203">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cadc0-203">See also</span></span>



[<span data-ttu-id="cadc0-204">IMAPISession::GetMsgStoresTable</span><span class="sxs-lookup"><span data-stu-id="cadc0-204">IMAPISession::GetMsgStoresTable</span></span>](imapisession-getmsgstorestable.md)
  
[<span data-ttu-id="cadc0-205">IMAPISession::OpenMsgStore</span><span class="sxs-lookup"><span data-stu-id="cadc0-205">IMAPISession::OpenMsgStore</span></span>](imapisession-openmsgstore.md)


[<span data-ttu-id="cadc0-206">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="cadc0-206">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

