---
title: 管理配置文件和邮件服务
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 89a2ac43-9601-47fc-b736-db48585fe879
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 1e64241008a4adde4431b2c9683199294f21e396
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410558"
---
# <a name="administering-profiles-and-message-services"></a><span data-ttu-id="af667-103">管理配置文件和邮件服务</span><span class="sxs-lookup"><span data-stu-id="af667-103">Administering Profiles and Message Services</span></span>

  
  
<span data-ttu-id="af667-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="af667-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="af667-105">配置文件和邮件服务管理可涉及创建新配置文件、删除旧配置文件，以及通过更改现有配置文件中包含的邮件服务和服务提供程序来修改现有配置文件的内容。</span><span class="sxs-lookup"><span data-stu-id="af667-105">Profile and message service administration can involve creating new profiles, deleting old profiles, and modifying the contents of existing profiles by changing the message services and service providers contained within them.</span></span> <span data-ttu-id="af667-106">并非所有客户端都支持将配置文件和邮件服务管理作为标准功能。</span><span class="sxs-lookup"><span data-stu-id="af667-106">Not all clients support profile and message service administration as standard features.</span></span> <span data-ttu-id="af667-107">有些客户端与配置文件只与允许用户在登录时选择一个配置文件有关。</span><span class="sxs-lookup"><span data-stu-id="af667-107">Some clients have nothing more to do with profiles than allow their users to select one at logon time.</span></span>
  
<span data-ttu-id="af667-108">如果支持配置文件或邮件服务管理，则有可能使用以下 MAPI 实现的接口：</span><span class="sxs-lookup"><span data-stu-id="af667-108">If you support profile or message service administration, chances are you will use the following interfaces that are implemented by MAPI:</span></span>
  
- <span data-ttu-id="af667-109">[IMsgServiceAdmin ：IUnknown](imsgserviceadminiunknown.md) 用于管理配置文件中的消息服务，可通过 [IMAPISession：：AdminServices](imapisession-adminservices.md) 或 [IProfAdmin：：AdminServices 访问](iprofadmin-adminservices.md)。</span><span class="sxs-lookup"><span data-stu-id="af667-109">[IMsgServiceAdmin : IUnknown](imsgserviceadminiunknown.md) to administer a message service in a profile, accessible through either [IMAPISession::AdminServices](imapisession-adminservices.md) or [IProfAdmin::AdminServices](iprofadmin-adminservices.md).</span></span> <span data-ttu-id="af667-110">消息客户端通常调用 **IMAPISession，** 而配置客户端或不发送或接收消息的客户端调用 **IProfAdmin**。</span><span class="sxs-lookup"><span data-stu-id="af667-110">Messaging clients typically call **IMAPISession** while configuration clients, or clients that do not send or receive messages, call **IProfAdmin**.</span></span> <span data-ttu-id="af667-111">尽可能调用 **IProfAdmin** 方法，因为它不会导致邮件服务启动。</span><span class="sxs-lookup"><span data-stu-id="af667-111">Whenever possible, call the **IProfAdmin** method because it does not cause the message service to be started.</span></span> <span data-ttu-id="af667-112">有关使用 **IMsgServiceAdmin** 接口的详细信息，请参阅下列主题 [：Configuring a Message Service、Copying](configuring-a-message-service.md)a Message [Service](copying-a-message-service.md)和 [Deleting a Message Service。](deleting-a-message-service.md)</span><span class="sxs-lookup"><span data-stu-id="af667-112">For more information about using the **IMsgServiceAdmin** interface, see the following topics: [Configuring a Message Service](configuring-a-message-service.md), [Copying a Message Service](copying-a-message-service.md), and [Deleting a Message Service](deleting-a-message-service.md).</span></span>
    
- <span data-ttu-id="af667-113">[IProfAdmin ：IUnknown](iprofadminiunknown.md) 用于管理可通过 [MAPIAdminProfiles](mapiadminprofiles.md) 函数访问的配置文件。</span><span class="sxs-lookup"><span data-stu-id="af667-113">[IProfAdmin : IUnknown](iprofadminiunknown.md) to administer a profile, accessible through the [MAPIAdminProfiles](mapiadminprofiles.md) function.</span></span> <span data-ttu-id="af667-114">有关使用 **IProfAdmin** 接口的信息，请参阅下列主题：使用自定义 [](creating-a-profile-by-using-custom-code.md)代码创建配置文件、复制配置文件、删除配置文件、查找配置文件 [](deleting-a-profile.md)名称以及设置默认 [配置文件](setting-a-default-profile.md)。 [](copying-a-profile.md) [](finding-a-profile-name.md)</span><span class="sxs-lookup"><span data-stu-id="af667-114">For more information about using the **IProfAdmin** interface, see the following topics: [Creating a Profile by Using Custom Code](creating-a-profile-by-using-custom-code.md), [Copying a Profile](copying-a-profile.md), [Deleting a Profile](deleting-a-profile.md), [Finding a Profile Name](finding-a-profile-name.md), and [Setting a Default Profile](setting-a-default-profile.md).</span></span>
    
- <span data-ttu-id="af667-115">[IProfSect ：IMAPIProp，](iprofsectimapiprop.md) 用于维护配置文件节中的属性，可通过 [IMAPISession：：OpenProfileSection](imapisession-openprofilesection.md) 或 [IProviderAdmin：：OpenProfileSection](iprovideradmin-openprofilesection.md) 方法访问。</span><span class="sxs-lookup"><span data-stu-id="af667-115">[IProfSect : IMAPIProp](iprofsectimapiprop.md) to maintain the properties in a profile section, accessible through the [IMAPISession::OpenProfileSection](imapisession-openprofilesection.md) or [IProviderAdmin::OpenProfileSection](iprovideradmin-openprofilesection.md) method.</span></span> <span data-ttu-id="af667-116">有关配置文件部分详细信息，请参阅 [MAPI Profiles](mapi-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="af667-116">For more information about profile sections, see [MAPI Profiles](mapi-profiles.md).</span></span>
    
- <span data-ttu-id="af667-117">[IProviderAdmin ： IUnknown](iprovideradminiunknown.md) 用于管理邮件服务中的服务提供程序，可通过 [IMsgServiceAdmin：：AdminProviders 访问](imsgserviceadmin-adminproviders.md)。</span><span class="sxs-lookup"><span data-stu-id="af667-117">[IProviderAdmin : IUnknown](iprovideradminiunknown.md) to administer the service providers in a message service, accessible through [IMsgServiceAdmin::AdminProviders](imsgserviceadmin-adminproviders.md).</span></span> <span data-ttu-id="af667-118">有关使用 **IProviderAdmin** 接口的信息，请参阅 [Adsing or Deleting Providers in a Message Service。](adding-or-deleting-providers-in-a-message-service.md)</span><span class="sxs-lookup"><span data-stu-id="af667-118">For more information about using the **IProviderAdmin** interface, see [Adding or Deleting Providers in a Message Service](adding-or-deleting-providers-in-a-message-service.md).</span></span>
    
<span data-ttu-id="af667-119">请谨慎支持配置文件和邮件服务管理。</span><span class="sxs-lookup"><span data-stu-id="af667-119">Be careful in your support of profile and message service administration.</span></span> <span data-ttu-id="af667-120">没有防止对使用中的配置文件进行不良修改的安全措施。</span><span class="sxs-lookup"><span data-stu-id="af667-120">There are no safeguards to protect against adversely modifying a profile that is in use.</span></span> <span data-ttu-id="af667-121">MAPI 可以阻止您删除使用中的配置文件，但无法阻止您删除它内每个邮件服务。</span><span class="sxs-lookup"><span data-stu-id="af667-121">MAPI can prevent you from deleting a profile in use, but cannot prevent you from deleting every message service in it.</span></span> <span data-ttu-id="af667-122">如果删除配置文件中的每个邮件服务，则这些服务的所有服务提供程序将停止，从而导致出现不可预知的结果。</span><span class="sxs-lookup"><span data-stu-id="af667-122">If you delete every message service in a profile, all of the service providers in these services will stop thereby causing unpredictable results to occur.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="af667-123">本节内容</span><span class="sxs-lookup"><span data-stu-id="af667-123">In this section</span></span>

[<span data-ttu-id="af667-124">创建配置文件</span><span class="sxs-lookup"><span data-stu-id="af667-124">Creating a Profile</span></span>](creating-a-profile.md)
  
> <span data-ttu-id="af667-125">介绍如何创建配置文件。</span><span class="sxs-lookup"><span data-stu-id="af667-125">Describes how to create a profile.</span></span>
    
[<span data-ttu-id="af667-126">复制配置文件</span><span class="sxs-lookup"><span data-stu-id="af667-126">Copying a Profile</span></span>](copying-a-profile.md)
  
> <span data-ttu-id="af667-127">介绍如何复制配置文件。</span><span class="sxs-lookup"><span data-stu-id="af667-127">Describes how to copy a profile.</span></span>
    
[<span data-ttu-id="af667-128">删除配置文件</span><span class="sxs-lookup"><span data-stu-id="af667-128">Deleting a Profile</span></span>](deleting-a-profile.md)
  
> <span data-ttu-id="af667-129">介绍如何删除配置文件。</span><span class="sxs-lookup"><span data-stu-id="af667-129">Describes how to delete a profile.</span></span>
    
[<span data-ttu-id="af667-130">设置默认配置文件</span><span class="sxs-lookup"><span data-stu-id="af667-130">Setting a Default Profile</span></span>](setting-a-default-profile.md)
  
> <span data-ttu-id="af667-131">介绍如何设置默认配置文件。</span><span class="sxs-lookup"><span data-stu-id="af667-131">Describes how to set a default profile.</span></span>
    
[<span data-ttu-id="af667-132">查找配置文件名称</span><span class="sxs-lookup"><span data-stu-id="af667-132">Finding a Profile Name</span></span>](finding-a-profile-name.md)
  
> <span data-ttu-id="af667-133">介绍如何查找配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="af667-133">Describes how to find a name of a profile.</span></span>
    
[<span data-ttu-id="af667-134">添加邮件服务</span><span class="sxs-lookup"><span data-stu-id="af667-134">Adding a Message Service</span></span>](adding-a-message-service.md)
  
> <span data-ttu-id="af667-135">介绍如何添加邮件服务。</span><span class="sxs-lookup"><span data-stu-id="af667-135">Describes how to add a message service.</span></span>
    
[<span data-ttu-id="af667-136">配置邮件服务</span><span class="sxs-lookup"><span data-stu-id="af667-136">Configuring a Message Service</span></span>](configuring-a-message-service.md)
  
> <span data-ttu-id="af667-137">介绍如何配置邮件服务。</span><span class="sxs-lookup"><span data-stu-id="af667-137">Describes how to configure a message service.</span></span>
    
[<span data-ttu-id="af667-138">复制邮件服务</span><span class="sxs-lookup"><span data-stu-id="af667-138">Copying a Message Service</span></span>](copying-a-message-service.md)
  
> <span data-ttu-id="af667-139">介绍如何将邮件服务复制到配置文件。</span><span class="sxs-lookup"><span data-stu-id="af667-139">Describes how to copy a message service to a profile.</span></span>
    
[<span data-ttu-id="af667-140">删除邮件服务</span><span class="sxs-lookup"><span data-stu-id="af667-140">Deleting a Message Service</span></span>](deleting-a-message-service.md)
  
> <span data-ttu-id="af667-141">介绍如何删除邮件服务。</span><span class="sxs-lookup"><span data-stu-id="af667-141">Describes how to delete a message service.</span></span>
    
[<span data-ttu-id="af667-142">在邮件服务中添加或删除提供程序</span><span class="sxs-lookup"><span data-stu-id="af667-142">Adding or Deleting Providers in a Message Service</span></span>](adding-or-deleting-providers-in-a-message-service.md)
  
> <span data-ttu-id="af667-143">介绍如何在邮件服务中添加或删除提供程序。</span><span class="sxs-lookup"><span data-stu-id="af667-143">Describes how to add or delete providers in a message service.</span></span>
    

