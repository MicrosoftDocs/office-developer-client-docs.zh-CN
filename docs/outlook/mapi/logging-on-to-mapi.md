---
title: 登录 MAPI
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 05bafe43-a78a-4659-92f0-0b4fe444c64f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: cce43301ac73a5646e263b2ab92700e57804637d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419707"
---
# <a name="logging-on-to-mapi"></a><span data-ttu-id="8fb7c-103">登录 MAPI</span><span class="sxs-lookup"><span data-stu-id="8fb7c-103">Logging on to MAPI</span></span>
 
<span data-ttu-id="8fb7c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8fb7c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8fb7c-105">客户端应用程序通过调用 **MAPILogonEx** 函数登录到 MAPI 子系统。</span><span class="sxs-lookup"><span data-stu-id="8fb7c-105">Client applications log on to the MAPI subsystem by calling the **MAPILogonEx** function.</span></span> <span data-ttu-id="8fb7c-106">有关详细信息，请参阅 [MAPILogonEx](mapilogonex.md)。</span><span class="sxs-lookup"><span data-stu-id="8fb7c-106">For more information, see [MAPILogonEx](mapilogonex.md).</span></span> <span data-ttu-id="8fb7c-107">**MAPILogonEx** 验证配置文件中每个服务提供商的配置文件选择和配置。</span><span class="sxs-lookup"><span data-stu-id="8fb7c-107">**MAPILogonEx** validates the profile selection and the configuration of each service provider in the profile.</span></span> <span data-ttu-id="8fb7c-108">配置后，MAPI 在启动邮件存储提供程序之前启动通讯簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="8fb7c-108">Once configured, MAPI starts the address book providers before starting the message store providers.</span></span> <span data-ttu-id="8fb7c-109">传输提供程序在首次需要其服务时启动。</span><span class="sxs-lookup"><span data-stu-id="8fb7c-109">Transport providers are started when their services are first required.</span></span> 
  
## <a name="choose-a-profile"></a><span data-ttu-id="8fb7c-110">选择配置文件</span><span class="sxs-lookup"><span data-stu-id="8fb7c-110">Choose a profile</span></span>
  
- <span data-ttu-id="8fb7c-111">将表示  _lpszProfileName_ 参数中的配置文件名称的字符串传递到 **MAPILogonEx** 或...</span><span class="sxs-lookup"><span data-stu-id="8fb7c-111">Pass in a character string that represents the name of the profile in the  _lpszProfileName_ parameter to **MAPILogonEx**, or...</span></span>
    
- <span data-ttu-id="8fb7c-112">允许用户指定配置文件，具体方法为在  _lpszProfileName_ 参数中传递 NULL，并设置MAPI_LOGON_UI或...</span><span class="sxs-lookup"><span data-stu-id="8fb7c-112">Allow the user to specify the profile by passing NULL in the  _lpszProfileName_ parameter and setting the MAPI_LOGON_UI flag, or...</span></span> 

- <span data-ttu-id="8fb7c-113">选择默认配置文件，方法为在  _lpszProfileName_ 参数中传递 NULL 并设置MAPI_USE_DEFAULT标记。</span><span class="sxs-lookup"><span data-stu-id="8fb7c-113">Select the default profile by passing NULL in the  _lpszProfileName_ parameter and setting the MAPI_USE_DEFAULT flag.</span></span> 
    
<span data-ttu-id="8fb7c-114">如果需要除默认配置文件外的特定配置文件，则必须将其名称保存在自己的配置数据库中或使用特定的命名约定。</span><span class="sxs-lookup"><span data-stu-id="8fb7c-114">If you require a specific profile other than the default profile, you must save its name in your own configuration database or use a specific naming convention.</span></span> <span data-ttu-id="8fb7c-115">MAPI 不会公开配置文件表中除名称和默认标志外的任何配置文件属性，并且默认配置文件标记保留用于邮件客户端和相关 IPM 应用程序。</span><span class="sxs-lookup"><span data-stu-id="8fb7c-115">MAPI does not expose any profile attributes other than the name and default flag in the profile table, and the default profile flag is reserved for messaging client and related IPM applications.</span></span>
  
<span data-ttu-id="8fb7c-116">向 **MAPILogonEx** 提供部分配置文件或提供程序配置信息的客户端必须通过允许显示对话框来提示用户输入其他数据。</span><span class="sxs-lookup"><span data-stu-id="8fb7c-116">Clients that supply partial profile or provider configuration information to **MAPILogonEx** must prompt the user for the additional data by allowing a dialog box to be displayed.</span></span> <span data-ttu-id="8fb7c-117">如果信息缺失且 **MAPILogonEx** 无法提示用户提供该信息，则登录将失败。</span><span class="sxs-lookup"><span data-stu-id="8fb7c-117">If information is missing and **MAPILogonEx** cannot prompt the user to supply it, the logon fails.</span></span> <span data-ttu-id="8fb7c-118">不需要用户输入的客户端可以禁止对话框显示。</span><span class="sxs-lookup"><span data-stu-id="8fb7c-118">Clients that do not need user input can suppress the dialog box display.</span></span> 
  
<span data-ttu-id="8fb7c-119">**MAPILogonEx** 用于启用用户界面的标志是互斥的;只能设置一个。</span><span class="sxs-lookup"><span data-stu-id="8fb7c-119">The flags that **MAPILogonEx** uses to enable a user interface are mutually exclusive; only one can be set.</span></span> <span data-ttu-id="8fb7c-120">取消设置这些标志将禁止显示用户界面，从而导致 **MAPILogonEx** 在缺少必要信息时失败。</span><span class="sxs-lookup"><span data-stu-id="8fb7c-120">Leaving these flags unset suppresses the display of a user interface, causing **MAPILogonEx** to fail if necessary information is missing.</span></span> <span data-ttu-id="8fb7c-121">也就是说，如果禁用用户界面，并传递  _lpszProfileName_ 参数的 NULL，并且未设置 MAPI_USE_DEFAULT 标志 **，MAPILogonEx** 将失败，因为它无法检索配置文件名称。</span><span class="sxs-lookup"><span data-stu-id="8fb7c-121">That is, if you disable the user interface and pass NULL for the  _lpszProfileName_ parameter and do not set the MAPI_USE_DEFAULT flag, **MAPILogonEx** will fail because it cannot retrieve a profile name.</span></span> 
  
<span data-ttu-id="8fb7c-122">**MAPILogonEx** 建立会话可以是单个消息会话、共享消息会话或非邮件会话。</span><span class="sxs-lookup"><span data-stu-id="8fb7c-122">The session that **MAPILogonEx** establishes can be an individual messaging session, a shared messaging session, or a nonmessaging session.</span></span> <span data-ttu-id="8fb7c-123">单个消息会话是客户端与 MAPI 子系统之间的专用连接，可以通过在 **MAPILogonEx** 调用中设置 MAPI_NEW_SESSION 标志来建立。</span><span class="sxs-lookup"><span data-stu-id="8fb7c-123">Individual messaging sessions are private connections between your client and the MAPI subsystem and can be established by setting the MAPI_NEW_SESSION flag in the call to **MAPILogonEx**.</span></span>
  
<span data-ttu-id="8fb7c-124">共享消息会话是多个邮件客户端可以使用的连接。</span><span class="sxs-lookup"><span data-stu-id="8fb7c-124">Shared messaging sessions are connections that multiple messaging clients can use.</span></span> <span data-ttu-id="8fb7c-125">通常，为使用相同配置文件的客户端建立共享会话。</span><span class="sxs-lookup"><span data-stu-id="8fb7c-125">Shared sessions are typically established for clients use the same profile.</span></span> <span data-ttu-id="8fb7c-126">若要将新会话建立为共享会话，请设置MAPI_ALLOW_OTHERS标记。</span><span class="sxs-lookup"><span data-stu-id="8fb7c-126">To establish a new session as a shared session, set the MAPI_ALLOW_OTHERS flag.</span></span> 
  
## <a name="use-an-existing-shared-session"></a><span data-ttu-id="8fb7c-127">使用现有共享会话</span><span class="sxs-lookup"><span data-stu-id="8fb7c-127">Use an existing shared session</span></span>
  
- <span data-ttu-id="8fb7c-128">不要设置MAPI_NEW_SESSION标志。</span><span class="sxs-lookup"><span data-stu-id="8fb7c-128">Do not set the MAPI_NEW_SESSION flag.</span></span>
    
- <span data-ttu-id="8fb7c-129">不要设置MAPI_ALLOW_OTHERS标志。</span><span class="sxs-lookup"><span data-stu-id="8fb7c-129">Do not set the MAPI_ALLOW_OTHERS flag.</span></span>
    
- <span data-ttu-id="8fb7c-130">为  _lpszProfileName 参数传递_ NULL。</span><span class="sxs-lookup"><span data-stu-id="8fb7c-130">Pass NULL for the  _lpszProfileName_ parameter.</span></span> 
    
- <span data-ttu-id="8fb7c-131">为  _lpszPassword_ 参数传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="8fb7c-131">Pass NULL for the  _lpszPassword_ parameter.</span></span> 
    
<span data-ttu-id="8fb7c-132">非messaging会话允许客户端访问 MAPI 子系统，但不允许发送或接收消息。</span><span class="sxs-lookup"><span data-stu-id="8fb7c-132">Nonmessaging sessions allow clients to access the MAPI subsystem, but do not allow messages to be sent or received.</span></span> <span data-ttu-id="8fb7c-133">配置或管理应用程序是可能需要建立非messaging会话的客户端示例。</span><span class="sxs-lookup"><span data-stu-id="8fb7c-133">Configuration or administration applications are examples of clients that might need to establish nonmessaging sessions.</span></span> <span data-ttu-id="8fb7c-134">若要请求非messaging会话，请设置MAPI_NO_MAIL标记。</span><span class="sxs-lookup"><span data-stu-id="8fb7c-134">To request a nonmessaging session, set the MAPI_NO_MAIL flag.</span></span> <span data-ttu-id="8fb7c-135">设置此标志将客户端登录，而不通知 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="8fb7c-135">Setting this flag logs your client on without informing the MAPI spooler.</span></span> <span data-ttu-id="8fb7c-136">使用此标志登录 MAPI 的客户端无法收到已读状态报告。</span><span class="sxs-lookup"><span data-stu-id="8fb7c-136">Clients that log on to MAPI with this flag cannot expect to ever receive read status reports.</span></span>
  
<span data-ttu-id="8fb7c-137">应MAPI_NO_MAIL设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="8fb7c-137">The MAPI_NO_MAIL flag should only be set:</span></span>
  
- <span data-ttu-id="8fb7c-138">如果客户端在会话期间不会发送或接收消息。</span><span class="sxs-lookup"><span data-stu-id="8fb7c-138">If your client will not send or receive messages during the session.</span></span>
    
- <span data-ttu-id="8fb7c-139">如果客户端可以完全控制配置文件的内容，并且使用紧密耦合的邮件存储和传输提供程序（如 Microsoft 邮件存储提供程序）来Exchange接收邮件。</span><span class="sxs-lookup"><span data-stu-id="8fb7c-139">If your client has complete control over the contents of the profile and messages are sent and received using tightly coupled message store and transport providers, such as the Microsoft Exchange providers.</span></span>
    
<span data-ttu-id="8fb7c-140">消息客户端可以与非邮件客户端共享会话。</span><span class="sxs-lookup"><span data-stu-id="8fb7c-140">A messaging client can share a session with a nonmessaging client.</span></span> <span data-ttu-id="8fb7c-141">共享会话的一个成员的特征不受其他成员的特征的影响。</span><span class="sxs-lookup"><span data-stu-id="8fb7c-141">The characteristics of one member of a shared session are not affected by the characteristics of other members.</span></span> <span data-ttu-id="8fb7c-142">也就是说，如果登录时设置了 MAPI_NO_MAIL 和 MAPI_ALLOW_OTHERS 标志，则登录到会话的消息客户端不会影响客户端的操作，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="8fb7c-142">That is, if you log on with the MAPI_NO_MAIL and MAPI_ALLOW_OTHERS flags set, a messaging client logging on to your session has no affect on the operation of your client and vice versa.</span></span> <span data-ttu-id="8fb7c-143">邮件客户端仍将能够发送和接收邮件，客户端将无法发送和接收邮件。</span><span class="sxs-lookup"><span data-stu-id="8fb7c-143">The messaging client will still be able to send and receive messages and your client will not.</span></span>
  
<span data-ttu-id="8fb7c-144">**MAPILogonEx** 定义一些可以设置的其他标志：</span><span class="sxs-lookup"><span data-stu-id="8fb7c-144">**MAPILogonEx** defines a few other flags that you can set:</span></span> 
  
- <span data-ttu-id="8fb7c-145">MAPI_FORCE_DOWNLOAD **MAPILogonEx** 返回之前应下载传入的邮件。</span><span class="sxs-lookup"><span data-stu-id="8fb7c-145">MAPI_FORCE_DOWNLOAD indicates that incoming messages should be downloaded before **MAPILogonEx** returns.</span></span> <span data-ttu-id="8fb7c-146">不设置此标志会导致稍后在后台下载邮件。</span><span class="sxs-lookup"><span data-stu-id="8fb7c-146">Not setting this flag causes messages to be downloaded in the background at a later time.</span></span> 
    
- <span data-ttu-id="8fb7c-147">MAPI_SERVICE_UI_ALWAYS请求配置文件中的每个邮件服务显示配置对话框。</span><span class="sxs-lookup"><span data-stu-id="8fb7c-147">MAPI_SERVICE_UI_ALWAYS requests that every message service in the profile display a configuration dialog box.</span></span>
    
- <span data-ttu-id="8fb7c-148">MAPI_NT_SERVICE表示您的客户端已作为 Windows 服务实现。</span><span class="sxs-lookup"><span data-stu-id="8fb7c-148">MAPI_NT_SERVICE indicates that your client is implemented as a Windows service.</span></span> <span data-ttu-id="8fb7c-149">如果客户端是服务，则必须设置此标志。</span><span class="sxs-lookup"><span data-stu-id="8fb7c-149">This flag must be set if your client is a service.</span></span>
    
<span data-ttu-id="8fb7c-150">每次成功登录后 **，MAPILogonEx** 都会返回一个指向 MAPI 会话的指针。</span><span class="sxs-lookup"><span data-stu-id="8fb7c-150">With every successful logon, **MAPILogonEx** returns a pointer to a MAPI session.</span></span> <span data-ttu-id="8fb7c-151">可以使用此指针调用 **IMAPISession 接口** 的方法。</span><span class="sxs-lookup"><span data-stu-id="8fb7c-151">You can use this pointer to call the methods of the **IMAPISession** interface.</span></span> <span data-ttu-id="8fb7c-152">有关详细信息，请参阅 [IMAPISession ： IUnknown](imapisessioniunknown.md)。</span><span class="sxs-lookup"><span data-stu-id="8fb7c-152">For more information, see [IMAPISession : IUnknown](imapisessioniunknown.md).</span></span> <span data-ttu-id="8fb7c-153">会话指针（无论会话类型如何）对于接收它们且跨任务无效是唯一的。</span><span class="sxs-lookup"><span data-stu-id="8fb7c-153">Session pointers, regardless of the type of session, are unique to the clients that receive them and are not valid across tasks.</span></span>
  

