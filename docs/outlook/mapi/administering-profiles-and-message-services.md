---
title: 管理配置文件和消息服务
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 89a2ac43-9601-47fc-b736-db48585fe879
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 71e8cf50c1951abf1df6163cae4757ffebc979b2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774516"
---
# <a name="administering-profiles-and-message-services"></a><span data-ttu-id="d67c1-103">管理配置文件和消息服务</span><span class="sxs-lookup"><span data-stu-id="d67c1-103">Administering Profiles and Message Services</span></span>

  
  
<span data-ttu-id="d67c1-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="d67c1-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="d67c1-105">配置文件和消息服务管理可涉及创建新配置文件，删除旧的配置文件，并通过更改消息服务和服务提供商，其中包含修改现有配置文件的内容。</span><span class="sxs-lookup"><span data-stu-id="d67c1-105">Profile and message service administration can involve creating new profiles, deleting old profiles, and modifying the contents of existing profiles by changing the message services and service providers contained within them.</span></span> <span data-ttu-id="d67c1-106">并非所有客户端支持为标准版功能的配置文件和消息服务管理。</span><span class="sxs-lookup"><span data-stu-id="d67c1-106">Not all clients support profile and message service administration as standard features.</span></span> <span data-ttu-id="d67c1-107">某些客户端有什么要使用配置文件不是允许用户可以选择其中一个在登录时执行的操作。</span><span class="sxs-lookup"><span data-stu-id="d67c1-107">Some clients have nothing more to do with profiles than allow their users to select one at logon time.</span></span>
  
<span data-ttu-id="d67c1-108">如果您支持配置文件或消息服务管理，很可能将使用的由 MAPI 实现以下接口：</span><span class="sxs-lookup"><span data-stu-id="d67c1-108">If you support profile or message service administration, chances are you will use the following interfaces that are implemented by MAPI:</span></span>
  
- <span data-ttu-id="d67c1-109">[IMsgServiceAdmin: IUnknown](imsgserviceadminiunknown.md)管理配置文件，可以通过[IMAPISession::AdminServices](imapisession-adminservices.md)或[IProfAdmin::AdminServices](iprofadmin-adminservices.md)访问中的消息服务。</span><span class="sxs-lookup"><span data-stu-id="d67c1-109">[IMsgServiceAdmin : IUnknown](imsgserviceadminiunknown.md) to administer a message service in a profile, accessible through either [IMAPISession::AdminServices](imapisession-adminservices.md) or [IProfAdmin::AdminServices](iprofadmin-adminservices.md).</span></span> <span data-ttu-id="d67c1-110">通常，消息客户端配置客户端或不发送或接收邮件，呼叫**IProfAdmin**的客户端时调用**IMAPISession** 。</span><span class="sxs-lookup"><span data-stu-id="d67c1-110">Messaging clients typically call **IMAPISession** while configuration clients, or clients that do not send or receive messages, call **IProfAdmin**.</span></span> <span data-ttu-id="d67c1-111">只要有可能，调用**IProfAdmin**方法，因为它不会导致邮件服务启动。</span><span class="sxs-lookup"><span data-stu-id="d67c1-111">Whenever possible, call the **IProfAdmin** method because it does not cause the message service to be started.</span></span> <span data-ttu-id="d67c1-112">有关使用**IMsgServiceAdmin**接口的详细信息，请参阅下列主题：[消息服务配置](configuring-a-message-service.md)、[复制邮件服务](copying-a-message-service.md)和[删除邮件服务](deleting-a-message-service.md)。</span><span class="sxs-lookup"><span data-stu-id="d67c1-112">For more information about using the **IMsgServiceAdmin** interface, see the following topics: [Configuring a Message Service](configuring-a-message-service.md), [Copying a Message Service](copying-a-message-service.md), and [Deleting a Message Service](deleting-a-message-service.md).</span></span>
    
- <span data-ttu-id="d67c1-113">[IProfAdmin: IUnknown](iprofadminiunknown.md)管理配置文件，可通过[MAPIAdminProfiles](mapiadminprofiles.md)函数。</span><span class="sxs-lookup"><span data-stu-id="d67c1-113">[IProfAdmin : IUnknown](iprofadminiunknown.md) to administer a profile, accessible through the [MAPIAdminProfiles](mapiadminprofiles.md) function.</span></span> <span data-ttu-id="d67c1-114">有关使用**IProfAdmin**接口的详细信息，请参阅下列主题：[创建一个配置文件使用自定义代码](creating-a-profile-by-using-custom-code.md)、[复制一个配置文件](copying-a-profile.md)，[删除配置文件](deleting-a-profile.md)、[查找配置文件的名称](finding-a-profile-name.md)和[设置默认配置文件](setting-a-default-profile.md)。</span><span class="sxs-lookup"><span data-stu-id="d67c1-114">For more information about using the **IProfAdmin** interface, see the following topics: [Creating a Profile by Using Custom Code](creating-a-profile-by-using-custom-code.md), [Copying a Profile](copying-a-profile.md), [Deleting a Profile](deleting-a-profile.md), [Finding a Profile Name](finding-a-profile-name.md), and [Setting a Default Profile](setting-a-default-profile.md).</span></span>
    
- <span data-ttu-id="d67c1-115">[IProfSect: IMAPIProp](iprofsectimapiprop.md)维护配置文件内容，可通过[IMAPISession::OpenProfileSection](imapisession-openprofilesection.md)或[IProviderAdmin::OpenProfileSection](iprovideradmin-openprofilesection.md)方法访问中的属性。</span><span class="sxs-lookup"><span data-stu-id="d67c1-115">[IProfSect : IMAPIProp](iprofsectimapiprop.md) to maintain the properties in a profile section, accessible through the [IMAPISession::OpenProfileSection](imapisession-openprofilesection.md) or [IProviderAdmin::OpenProfileSection](iprovideradmin-openprofilesection.md) method.</span></span> <span data-ttu-id="d67c1-116">有关配置文件节的详细信息，请参阅[MAPI 配置文件](mapi-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="d67c1-116">For more information about profile sections, see [MAPI Profiles](mapi-profiles.md).</span></span>
    
- <span data-ttu-id="d67c1-117">[IProviderAdmin: IUnknown](iprovideradminiunknown.md)管理消息服务，可通过[IMsgServiceAdmin::AdminProviders](imsgserviceadmin-adminproviders.md)访问中的服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="d67c1-117">[IProviderAdmin : IUnknown](iprovideradminiunknown.md) to administer the service providers in a message service, accessible through [IMsgServiceAdmin::AdminProviders](imsgserviceadmin-adminproviders.md).</span></span> <span data-ttu-id="d67c1-118">有关使用**IProviderAdmin**接口的详细信息，请参阅[添加或删除邮件服务中的提供程序](adding-or-deleting-providers-in-a-message-service.md)。</span><span class="sxs-lookup"><span data-stu-id="d67c1-118">For more information about using the **IProviderAdmin** interface, see [Adding or Deleting Providers in a Message Service](adding-or-deleting-providers-in-a-message-service.md).</span></span>
    
<span data-ttu-id="d67c1-119">注意在您的配置文件和消息服务管理的支持。</span><span class="sxs-lookup"><span data-stu-id="d67c1-119">Be careful in your support of profile and message service administration.</span></span> <span data-ttu-id="d67c1-120">没有任何安全措施防御产生不利修改正在使用的配置文件。</span><span class="sxs-lookup"><span data-stu-id="d67c1-120">There are no safeguards to protect against adversely modifying a profile that is in use.</span></span> <span data-ttu-id="d67c1-121">MAPI 可以防止删除配置文件中使用，但无法防止删除在每个邮件服务。</span><span class="sxs-lookup"><span data-stu-id="d67c1-121">MAPI can prevent you from deleting a profile in use, but cannot prevent you from deleting every message service in it.</span></span> <span data-ttu-id="d67c1-122">如果您删除配置文件中的每个邮件服务，所有这些服务的服务提供程序将停止从而导致无法预料的结果发生。</span><span class="sxs-lookup"><span data-stu-id="d67c1-122">If you delete every message service in a profile, all of the service providers in these services will stop thereby causing unpredictable results to occur.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="d67c1-123">本节内容</span><span class="sxs-lookup"><span data-stu-id="d67c1-123">In this section</span></span>

[<span data-ttu-id="d67c1-124">创建一个配置文件</span><span class="sxs-lookup"><span data-stu-id="d67c1-124">Creating a Profile</span></span>](creating-a-profile.md)
  
> <span data-ttu-id="d67c1-125">介绍如何创建一个配置文件。</span><span class="sxs-lookup"><span data-stu-id="d67c1-125">Describes how to create a profile.</span></span>
    
[<span data-ttu-id="d67c1-126">复制一个配置文件</span><span class="sxs-lookup"><span data-stu-id="d67c1-126">Copying a Profile</span></span>](copying-a-profile.md)
  
> <span data-ttu-id="d67c1-127">介绍如何将配置文件复制。</span><span class="sxs-lookup"><span data-stu-id="d67c1-127">Describes how to copy a profile.</span></span>
    
[<span data-ttu-id="d67c1-128">删除配置文件</span><span class="sxs-lookup"><span data-stu-id="d67c1-128">Deleting a Profile</span></span>](deleting-a-profile.md)
  
> <span data-ttu-id="d67c1-129">介绍如何删除配置文件。</span><span class="sxs-lookup"><span data-stu-id="d67c1-129">Describes how to delete a profile.</span></span>
    
[<span data-ttu-id="d67c1-130">设置默认配置文件</span><span class="sxs-lookup"><span data-stu-id="d67c1-130">Setting a Default Profile</span></span>](setting-a-default-profile.md)
  
> <span data-ttu-id="d67c1-131">介绍如何设置默认配置文件。</span><span class="sxs-lookup"><span data-stu-id="d67c1-131">Describes how to set a default profile.</span></span>
    
[<span data-ttu-id="d67c1-132">查找配置文件名称</span><span class="sxs-lookup"><span data-stu-id="d67c1-132">Finding a Profile Name</span></span>](finding-a-profile-name.md)
  
> <span data-ttu-id="d67c1-133">介绍如何查找配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="d67c1-133">Describes how to find a name of a profile.</span></span>
    
[<span data-ttu-id="d67c1-134">添加的消息服务</span><span class="sxs-lookup"><span data-stu-id="d67c1-134">Adding a Message Service</span></span>](adding-a-message-service.md)
  
> <span data-ttu-id="d67c1-135">介绍如何添加邮件服务。</span><span class="sxs-lookup"><span data-stu-id="d67c1-135">Describes how to add a message service.</span></span>
    
[<span data-ttu-id="d67c1-136">配置邮件服务</span><span class="sxs-lookup"><span data-stu-id="d67c1-136">Configuring a Message Service</span></span>](configuring-a-message-service.md)
  
> <span data-ttu-id="d67c1-137">介绍如何配置的消息服务。</span><span class="sxs-lookup"><span data-stu-id="d67c1-137">Describes how to configure a message service.</span></span>
    
[<span data-ttu-id="d67c1-138">复制邮件服务</span><span class="sxs-lookup"><span data-stu-id="d67c1-138">Copying a Message Service</span></span>](copying-a-message-service.md)
  
> <span data-ttu-id="d67c1-139">介绍如何向一个配置文件复制的消息服务。</span><span class="sxs-lookup"><span data-stu-id="d67c1-139">Describes how to copy a message service to a profile.</span></span>
    
[<span data-ttu-id="d67c1-140">删除消息服务</span><span class="sxs-lookup"><span data-stu-id="d67c1-140">Deleting a Message Service</span></span>](deleting-a-message-service.md)
  
> <span data-ttu-id="d67c1-141">介绍如何删除消息服务。</span><span class="sxs-lookup"><span data-stu-id="d67c1-141">Describes how to delete a message service.</span></span>
    
[<span data-ttu-id="d67c1-142">添加或删除的消息服务提供程序</span><span class="sxs-lookup"><span data-stu-id="d67c1-142">Adding or Deleting Providers in a Message Service</span></span>](adding-or-deleting-providers-in-a-message-service.md)
  
> <span data-ttu-id="d67c1-143">介绍如何添加或删除的消息服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="d67c1-143">Describes how to add or delete providers in a message service.</span></span>
    

