---
title: 登录到 MAPI
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 05bafe43-a78a-4659-92f0-0b4fe444c64f
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 1ae3c47964ff238f57e98e0005a966008192f7c7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776165"
---
# <a name="logging-on-to-mapi"></a><span data-ttu-id="c8eb7-103">登录到 MAPI</span><span class="sxs-lookup"><span data-stu-id="c8eb7-103">Logging on to MAPI</span></span>
 
<span data-ttu-id="c8eb7-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="c8eb7-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="c8eb7-105">客户端应用程序登录到 MAPI 子系统调用**MAPILogonEx**函数。</span><span class="sxs-lookup"><span data-stu-id="c8eb7-105">Client applications log on to the MAPI subsystem by calling the **MAPILogonEx** function.</span></span> <span data-ttu-id="c8eb7-106">有关详细信息，请参阅[MAPILogonEx](mapilogonex.md)。</span><span class="sxs-lookup"><span data-stu-id="c8eb7-106">For more information, see [MAPILogonEx](mapilogonex.md).</span></span> <span data-ttu-id="c8eb7-107">**MAPILogonEx**验证所选的模板和配置文件中每个服务提供程序的配置。</span><span class="sxs-lookup"><span data-stu-id="c8eb7-107">**MAPILogonEx** validates the profile selection and the configuration of each service provider in the profile.</span></span> <span data-ttu-id="c8eb7-108">配置后，MAPI 开始消息存储提供程序之前通讯簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="c8eb7-108">Once configured, MAPI starts the address book providers before starting the message store providers.</span></span> <span data-ttu-id="c8eb7-109">首先需要其服务时才会启动传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="c8eb7-109">Transport providers are started when their services are first required.</span></span> 
  
## <a name="choose-a-profile"></a><span data-ttu-id="c8eb7-110">选择一个配置文件</span><span class="sxs-lookup"><span data-stu-id="c8eb7-110">Choose a profile</span></span>
  
- <span data-ttu-id="c8eb7-111">代表**MAPILogonEx**， _lpszProfileName_参数中的配置文件的名称的字符串中传递或...</span><span class="sxs-lookup"><span data-stu-id="c8eb7-111">Pass in a character string that represents the name of the profile in the  _lpszProfileName_ parameter to **MAPILogonEx**, or...</span></span>
    
- <span data-ttu-id="c8eb7-112">允许用户通过_lpszProfileName_参数中传递 NULL 并设置 MAPI_LOGON_UI 标志，指定的配置文件或...</span><span class="sxs-lookup"><span data-stu-id="c8eb7-112">Allow the user to specify the profile by passing NULL in the  _lpszProfileName_ parameter and setting the MAPI_LOGON_UI flag, or...</span></span> 

- <span data-ttu-id="c8eb7-113">选择默认配置文件通过_lpszProfileName_参数中传递 NULL 并设置 MAPI_USE_DEFAULT 标志。</span><span class="sxs-lookup"><span data-stu-id="c8eb7-113">Select the default profile by passing NULL in the  _lpszProfileName_ parameter and setting the MAPI_USE_DEFAULT flag.</span></span> 
    
<span data-ttu-id="c8eb7-114">如果您需要特定配置文件的默认配置文件之外，必须在您自己的配置数据库中保存其名称或使用特定的命名约定。</span><span class="sxs-lookup"><span data-stu-id="c8eb7-114">If you require a specific profile other than the default profile, you must save its name in your own configuration database or use a specific naming convention.</span></span> <span data-ttu-id="c8eb7-115">MAPI 不公开在配置文件表中，名称和默认标记以外的任何配置文件属性和默认配置文件标志供消息客户端和相关的 IPM 应用程序。</span><span class="sxs-lookup"><span data-stu-id="c8eb7-115">MAPI does not expose any profile attributes other than the name and default flag in the profile table, and the default profile flag is reserved for messaging client and related IPM applications.</span></span>
  
<span data-ttu-id="c8eb7-116">提供部分的配置文件或**MAPILogonEx**提供程序配置信息的客户端必须从而将显示一个对话框提示用户输入其他数据。</span><span class="sxs-lookup"><span data-stu-id="c8eb7-116">Clients that supply partial profile or provider configuration information to **MAPILogonEx** must prompt the user for the additional data by allowing a dialog box to be displayed.</span></span> <span data-ttu-id="c8eb7-117">如果缺少信息且**MAPILogonEx**无法提示用户提供其登录失败。</span><span class="sxs-lookup"><span data-stu-id="c8eb7-117">If information is missing and **MAPILogonEx** cannot prompt the user to supply it, the logon fails.</span></span> <span data-ttu-id="c8eb7-118">执行不需要用户输入的客户端可以禁止对话框框显示。</span><span class="sxs-lookup"><span data-stu-id="c8eb7-118">Clients that do not need user input can suppress the dialog box display.</span></span> 
  
<span data-ttu-id="c8eb7-119">**MAPILogonEx**使用启用的用户界面的标志相互排斥;可以设置只有一个。</span><span class="sxs-lookup"><span data-stu-id="c8eb7-119">The flags that **MAPILogonEx** uses to enable a user interface are mutually exclusive; only one can be set.</span></span> <span data-ttu-id="c8eb7-120">保留这些标志未设置禁止显示用户界面，导致**MAPILogonEx**失败如果缺少必需的信息。</span><span class="sxs-lookup"><span data-stu-id="c8eb7-120">Leaving these flags unset suppresses the display of a user interface, causing **MAPILogonEx** to fail if necessary information is missing.</span></span> <span data-ttu-id="c8eb7-121">也就是说，如果您禁用用户界面和为_lpszProfileName_参数传递 NULL 并不设置 MAPI_USE_DEFAULT 标志， **MAPILogonEx**将失败，因为它无法检索配置文件名称。</span><span class="sxs-lookup"><span data-stu-id="c8eb7-121">That is, if you disable the user interface and pass NULL for the  _lpszProfileName_ parameter and do not set the MAPI_USE_DEFAULT flag, **MAPILogonEx** will fail because it cannot retrieve a profile name.</span></span> 
  
<span data-ttu-id="c8eb7-122">**MAPILogonEx**建立会话可以是单个消息会话、 共享的邮件会话或非邮件会话。</span><span class="sxs-lookup"><span data-stu-id="c8eb7-122">The session that **MAPILogonEx** establishes can be an individual messaging session, a shared messaging session, or a nonmessaging session.</span></span> <span data-ttu-id="c8eb7-123">单个消息的会话专用您的客户端和 MAPI 子系统之间的连接，可以通过对**MAPILogonEx**的调用中设置 MAPI_NEW_SESSION 标志来建立。</span><span class="sxs-lookup"><span data-stu-id="c8eb7-123">Individual messaging sessions are private connections between your client and the MAPI subsystem and can be established by setting the MAPI_NEW_SESSION flag in the call to **MAPILogonEx**.</span></span>
  
<span data-ttu-id="c8eb7-124">共享的邮件会话是多个邮件客户端可以使用的连接。</span><span class="sxs-lookup"><span data-stu-id="c8eb7-124">Shared messaging sessions are connections that multiple messaging clients can use.</span></span> <span data-ttu-id="c8eb7-125">共享的会话通常建立的客户端使用的同一配置文件。</span><span class="sxs-lookup"><span data-stu-id="c8eb7-125">Shared sessions are typically established for clients use the same profile.</span></span> <span data-ttu-id="c8eb7-126">若要将新的会话为共享会话，请设置 MAPI_ALLOW_OTHERS 标志。</span><span class="sxs-lookup"><span data-stu-id="c8eb7-126">To establish a new session as a shared session, set the MAPI_ALLOW_OTHERS flag.</span></span> 
  
## <a name="use-an-existing-shared-session"></a><span data-ttu-id="c8eb7-127">使用现有共享的会话</span><span class="sxs-lookup"><span data-stu-id="c8eb7-127">Use an existing shared session</span></span>
  
- <span data-ttu-id="c8eb7-128">未设置 MAPI_NEW_SESSION 标志。</span><span class="sxs-lookup"><span data-stu-id="c8eb7-128">Do not set the MAPI_NEW_SESSION flag.</span></span>
    
- <span data-ttu-id="c8eb7-129">未设置 MAPI_ALLOW_OTHERS 标志。</span><span class="sxs-lookup"><span data-stu-id="c8eb7-129">Do not set the MAPI_ALLOW_OTHERS flag.</span></span>
    
- <span data-ttu-id="c8eb7-130">为_lpszProfileName_参数传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="c8eb7-130">Pass NULL for the  _lpszProfileName_ parameter.</span></span> 
    
- <span data-ttu-id="c8eb7-131">为_lpszPassword_参数传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="c8eb7-131">Pass NULL for the  _lpszPassword_ parameter.</span></span> 
    
<span data-ttu-id="c8eb7-132">非邮件会话允许客户端访问 MAPI 子系统，但不是允许发送或接收邮件。</span><span class="sxs-lookup"><span data-stu-id="c8eb7-132">Nonmessaging sessions allow clients to access the MAPI subsystem, but do not allow messages to be sent or received.</span></span> <span data-ttu-id="c8eb7-133">配置或管理应用程序可能需要建立非邮件会话的客户端的示例。</span><span class="sxs-lookup"><span data-stu-id="c8eb7-133">Configuration or administration applications are examples of clients that might need to establish nonmessaging sessions.</span></span> <span data-ttu-id="c8eb7-134">要请求的非邮件会话，请设置 MAPI_NO_MAIL 标志。</span><span class="sxs-lookup"><span data-stu-id="c8eb7-134">To request a nonmessaging session, set the MAPI_NO_MAIL flag.</span></span> <span data-ttu-id="c8eb7-135">设置此标志以在登录您的客户端，但没有告知 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="c8eb7-135">Setting this flag logs your client on without informing the MAPI spooler.</span></span> <span data-ttu-id="c8eb7-136">使用此标志登录到 MAPI 的客户端无法希望以往接收读取的状态报告。</span><span class="sxs-lookup"><span data-stu-id="c8eb7-136">Clients that log on to MAPI with this flag cannot expect to ever receive read status reports.</span></span>
  
<span data-ttu-id="c8eb7-137">只应设置 MAPI_NO_MAIL 标志：</span><span class="sxs-lookup"><span data-stu-id="c8eb7-137">The MAPI_NO_MAIL flag should only be set:</span></span>
  
- <span data-ttu-id="c8eb7-138">如果您的客户端将不发送或在会话过程中接收邮件。</span><span class="sxs-lookup"><span data-stu-id="c8eb7-138">If your client will not send or receive messages during the session.</span></span>
    
- <span data-ttu-id="c8eb7-139">如果您的客户端具有完全控制配置文件的内容和发送和接收消息使用紧密耦合消息存储，并且传输提供程序，如 Microsoft Exchange 提供商。</span><span class="sxs-lookup"><span data-stu-id="c8eb7-139">If your client has complete control over the contents of the profile and messages are sent and received using tightly coupled message store and transport providers, such as the Microsoft Exchange providers.</span></span>
    
<span data-ttu-id="c8eb7-140">消息客户端可以与非邮件客户端共享会话。</span><span class="sxs-lookup"><span data-stu-id="c8eb7-140">A messaging client can share a session with a nonmessaging client.</span></span> <span data-ttu-id="c8eb7-141">共享会话的一个成员的特征不受影响的其他成员的特征。</span><span class="sxs-lookup"><span data-stu-id="c8eb7-141">The characteristics of one member of a shared session are not affected by the characteristics of other members.</span></span> <span data-ttu-id="c8eb7-142">也就是说，如果 MAPI_NO_MAIL 和 MAPI_ALLOW_OTHERS 设置 flags 登录，登录到您的会话的消息客户端对没有影响操作的客户端，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="c8eb7-142">That is, if you log on with the MAPI_NO_MAIL and MAPI_ALLOW_OTHERS flags set, a messaging client logging on to your session has no affect on the operation of your client and vice versa.</span></span> <span data-ttu-id="c8eb7-143">消息客户端将仍无法发送和接收邮件，并无法与您的客户端。</span><span class="sxs-lookup"><span data-stu-id="c8eb7-143">The messaging client will still be able to send and receive messages and your client will not.</span></span>
  
<span data-ttu-id="c8eb7-144">**MAPILogonEx**定义几个您可以设置其他标志：</span><span class="sxs-lookup"><span data-stu-id="c8eb7-144">**MAPILogonEx** defines a few other flags that you can set:</span></span> 
  
- <span data-ttu-id="c8eb7-145">MAPI_FORCE_DOWNLOAD 指示**MAPILogonEx**返回之前，应下载传入消息。</span><span class="sxs-lookup"><span data-stu-id="c8eb7-145">MAPI_FORCE_DOWNLOAD indicates that incoming messages should be downloaded before **MAPILogonEx** returns.</span></span> <span data-ttu-id="c8eb7-146">不设置此标志会导致在以后在后台下载的邮件。</span><span class="sxs-lookup"><span data-stu-id="c8eb7-146">Not setting this flag causes messages to be downloaded in the background at a later time.</span></span> 
    
- <span data-ttu-id="c8eb7-147">MAPI_SERVICE_UI_ALWAYS 请求配置文件中的每个邮件服务显示的配置对话框。</span><span class="sxs-lookup"><span data-stu-id="c8eb7-147">MAPI_SERVICE_UI_ALWAYS requests that every message service in the profile display a configuration dialog box.</span></span>
    
- <span data-ttu-id="c8eb7-148">MAPI_NT_SERVICE 指示您的客户端实现作为 Windows 服务。</span><span class="sxs-lookup"><span data-stu-id="c8eb7-148">MAPI_NT_SERVICE indicates that your client is implemented as a Windows service.</span></span> <span data-ttu-id="c8eb7-149">如果您的客户端是一项服务，必须设置此标志。</span><span class="sxs-lookup"><span data-stu-id="c8eb7-149">This flag must be set if your client is a service.</span></span>
    
<span data-ttu-id="c8eb7-150">与每个成功登录**MAPILogonEx**返回到 MAPI 会话的指针。</span><span class="sxs-lookup"><span data-stu-id="c8eb7-150">With every successful logon, **MAPILogonEx** returns a pointer to a MAPI session.</span></span> <span data-ttu-id="c8eb7-151">您可以使用此指针调用**IMAPISession**接口的方法。</span><span class="sxs-lookup"><span data-stu-id="c8eb7-151">You can use this pointer to call the methods of the **IMAPISession** interface.</span></span> <span data-ttu-id="c8eb7-152">有关详细信息，请参阅[IMAPISession: IUnknown](imapisessioniunknown.md)。</span><span class="sxs-lookup"><span data-stu-id="c8eb7-152">For more information, see [IMAPISession : IUnknown](imapisessioniunknown.md).</span></span> <span data-ttu-id="c8eb7-153">会话指针，无论，类型是会话的唯一的客户端接收这些且不是会话的有效跨任务。</span><span class="sxs-lookup"><span data-stu-id="c8eb7-153">Session pointers, regardless of the type of session, are unique to the clients that receive them and are not valid across tasks.</span></span>
  

