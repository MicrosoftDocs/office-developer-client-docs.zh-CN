---
title: 在邮件服务中添加或删除提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 44bb4d34-ca96-4d5a-93fe-85e09bd7971d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ed5ea8bdfcbdaaa6b6abd81a39f0e8df50d3b314
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433421"
---
# <a name="adding-or-deleting-providers-in-a-message-service"></a><span data-ttu-id="15406-103">在邮件服务中添加或删除提供程序</span><span class="sxs-lookup"><span data-stu-id="15406-103">Adding or Deleting Providers in a Message Service</span></span>

  
  
<span data-ttu-id="15406-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="15406-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="15406-105">若要在邮件服务中添加或删除服务提供程序，请使用 [IProviderAdmin ： IUnknown](iprovideradminiunknown.md) 接口。</span><span class="sxs-lookup"><span data-stu-id="15406-105">To add or delete service providers in a message service, use the [IProviderAdmin : IUnknown](iprovideradminiunknown.md) interface.</span></span> <span data-ttu-id="15406-106">可以通过调用 [IMsgServiceAdmin：：AdminProviders](imsgserviceadmin-adminproviders.md)来检索 **IProviderAdmin** 指针。</span><span class="sxs-lookup"><span data-stu-id="15406-106">You can retrieve an **IProviderAdmin** pointer by calling [IMsgServiceAdmin::AdminProviders](imsgserviceadmin-adminproviders.md).</span></span> <span data-ttu-id="15406-107">提供程序表（可以通过 [IProviderAdmin：：GetProviderTable](iprovideradmin-getprovidertable.md)访问）列出了有关邮件服务中当前安装的服务提供商的信息。</span><span class="sxs-lookup"><span data-stu-id="15406-107">The provider table, accessable through [IProviderAdmin::GetProviderTable](iprovideradmin-getprovidertable.md), lists information about the service providers currently installed in the message service.</span></span> <span data-ttu-id="15406-108">客户端和服务提供程序可以使用提供程序表访问提供程序 DLL 文件的名称，例如 **，或者 MAPIUID**、显示名称 和提供程序的类型，以及有关邮件服务的信息。</span><span class="sxs-lookup"><span data-stu-id="15406-108">Clients and service providers can use the provider table to access the name of the provider DLL file, for example, or the **MAPIUID**, display name, and type of the provider as well as information about the message service.</span></span> <span data-ttu-id="15406-109">有关详细信息，请参阅提供程序 [表](provider-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="15406-109">For more information, see [Provider Tables](provider-tables.md).</span></span>
  
 <span data-ttu-id="15406-110">**在邮件服务中添加或删除服务提供程序**</span><span class="sxs-lookup"><span data-stu-id="15406-110">**To add or delete a service provider in a message service**</span></span>
  
1. <span data-ttu-id="15406-111">调用 **AdminServices** 方法来访问邮件服务管理对象。</span><span class="sxs-lookup"><span data-stu-id="15406-111">Call the **AdminServices** method to access a message service administration object.</span></span> 
    
2. <span data-ttu-id="15406-112">调用 [IMsgServiceAdmin：：GetMsgServiceTable](imsgserviceadmin-getmsgservicetable.md) 以访问邮件服务表。</span><span class="sxs-lookup"><span data-stu-id="15406-112">Call [IMsgServiceAdmin::GetMsgServiceTable](imsgserviceadmin-getmsgservicetable.md) to access the message service table.</span></span> 
    
3. <span data-ttu-id="15406-113">使用与要修改的邮件服务名称相匹配的 **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 或 **PR_SERVICE_NAME** ([PidTagServiceName](pidtagservicename-canonical-property.md)) 的 [SPropertyRestriction](spropertyrestriction.md)结构构建属性限制。</span><span class="sxs-lookup"><span data-stu-id="15406-113">Build a property restriction using an [SPropertyRestriction](spropertyrestriction.md) structure that matches **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) or **PR_SERVICE_NAME** ([PidTagServiceName](pidtagservicename-canonical-property.md)) with the name of the message service to be modified.</span></span> 
    
4. <span data-ttu-id="15406-114">调用邮件服务表的 [IMAPITable：：FindRow](imapitable-findrow.md) 方法来查找表中表示目标邮件服务的行。</span><span class="sxs-lookup"><span data-stu-id="15406-114">Call the message service table's [IMAPITable::FindRow](imapitable-findrow.md) method to locate the row in the table that represents the targeted message service.</span></span> 
    
5. <span data-ttu-id="15406-115">调用 [IMsgServiceAdmin：：AdminProviders](imsgserviceadmin-adminproviders.md) 以检索 **IProviderAdmin** 指针。</span><span class="sxs-lookup"><span data-stu-id="15406-115">Call [IMsgServiceAdmin::AdminProviders](imsgserviceadmin-adminproviders.md) to retrieve an **IProviderAdmin** pointer.</span></span> <span data-ttu-id="15406-116">将邮件 **PR_SERVICE_UID (** [PidTagServiceUid) 行中的 PidTagServiceUid](pidtagserviceuid-canonical-property.md) 参数作为  _lpUID_ 参数传递。</span><span class="sxs-lookup"><span data-stu-id="15406-116">Pass the **PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) column from the message service table row as the  _lpUID_ parameter.</span></span> 
    
6. <span data-ttu-id="15406-117">调用 [IProviderAdmin：：GetProviderTable](iprovideradmin-getprovidertable.md) 以访问提供程序表。</span><span class="sxs-lookup"><span data-stu-id="15406-117">Call [IProviderAdmin::GetProviderTable](iprovideradmin-getprovidertable.md) to access the provider table.</span></span> 
    
7. <span data-ttu-id="15406-118">使用与要添加或删除的服务提供商的名称匹配的 **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 或 **PR_PROVIDER_DISPLAY** ([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md)) 的 SPropertyRestriction 结构构建属性限制。</span><span class="sxs-lookup"><span data-stu-id="15406-118">Build a property restriction using an SPropertyRestriction structure that matches **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) or **PR_PROVIDER_DISPLAY** ([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md)) with the name of the service provider to be added or deleted.</span></span> 
    
8. <span data-ttu-id="15406-119">调用提供程序表的 [IMAPITable：：FindRow](imapitable-findrow.md) 方法来查找表中表示目标服务提供商的行。</span><span class="sxs-lookup"><span data-stu-id="15406-119">Call the provider table's [IMAPITable::FindRow](imapitable-findrow.md) method to locate the row in the table that represents the targeted service provider.</span></span> 
    
9. <span data-ttu-id="15406-120">调用 [IProviderAdmin：：CreateProvider](iprovideradmin-createprovider.md) 以添加提供程序或 [IProviderAdmin：:D eleteProvider](iprovideradmin-deleteprovider.md) 以将其从邮件服务中删除。</span><span class="sxs-lookup"><span data-stu-id="15406-120">Call [IProviderAdmin::CreateProvider](iprovideradmin-createprovider.md) to add the provider or [IProviderAdmin::DeleteProvider](iprovideradmin-deleteprovider.md) to remove it from the message service.</span></span> <span data-ttu-id="15406-121">对于 **CreateProvider**，将提供程序的 **PR_DISPLAY_NAME** 属性作为  _lpszProvider_ 参数传递。</span><span class="sxs-lookup"><span data-stu-id="15406-121">For **CreateProvider**, pass the provider's **PR_DISPLAY_NAME** property as the  _lpszProvider_ parameter.</span></span> <span data-ttu-id="15406-122">对于任一方法，将提供程序的 **PR_SERVICE_UID** 属性作为  _lpUID_ 参数传递。</span><span class="sxs-lookup"><span data-stu-id="15406-122">For either method, pass the provider's **PR_SERVICE_UID** property as the  _lpUID_ parameter.</span></span> <span data-ttu-id="15406-123">添加或删除服务提供商后，在新建会话之前，更改不会显现出来。</span><span class="sxs-lookup"><span data-stu-id="15406-123">After the service provider has been added or deleted, the change will not be apparent until a new session is created.</span></span> 
    
<span data-ttu-id="15406-124">向配置文件中添加服务提供程序（特别是邮件存储提供程序）的另一种技术涉及构造提供程序的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="15406-124">Another technique for adding a service provider, specifically a message store provider, to a profile involves constructing an entry identifier for the provider.</span></span> <span data-ttu-id="15406-125">由于构造条目标识符需要了解其格式，因此只有在服务提供商公开其条目标识符格式时，才能使用这种技术。</span><span class="sxs-lookup"><span data-stu-id="15406-125">Because constructing an entry identifier requires knowledge of its format, this technique can only be used if the service provider has made its entry identifier format public.</span></span> 
  
<span data-ttu-id="15406-126">使用新构造的条目标识符，客户端可以调用 [IMAPISession：：OpenMsgStore](imapisession-openmsgstore.md)。</span><span class="sxs-lookup"><span data-stu-id="15406-126">With the newly constructed entry identifier, a client can call [IMAPISession::OpenMsgStore](imapisession-openmsgstore.md).</span></span> <span data-ttu-id="15406-127">MAPI 会自动在服务提供程序的配置文件中创建配置文件节，但不将其添加到邮件服务。</span><span class="sxs-lookup"><span data-stu-id="15406-127">MAPI automatically creates a profile section in the profile for the service provider, but does not add it to a message service.</span></span> 
  
<span data-ttu-id="15406-128">某些邮件服务不允许这种类型的动态修改;是否受支持取决于邮件服务。</span><span class="sxs-lookup"><span data-stu-id="15406-128">Some message services do not allow this type of dynamic modification; whether or not it is supported is up to the message service.</span></span> <span data-ttu-id="15406-129">另一个可能受支持也可能不受支持的功能是直接访问邮件服务的专用配置文件部分的功能。</span><span class="sxs-lookup"><span data-stu-id="15406-129">Another feature that may or may not be supported is the ability to directly access a message service's private profile sections.</span></span> <span data-ttu-id="15406-130">如果您使用的邮件服务允许此类访问，它将发布表示 MAPISVC.INF 中的专用节的 **GUID。**</span><span class="sxs-lookup"><span data-stu-id="15406-130">If the message service you are using permits such access, it will publish the **GUID** that represents the private section in MAPISVC.INF.</span></span> <span data-ttu-id="15406-131">您可以在对 [IProviderAdmin：：OpenProfileSection](iprovideradmin-openprofilesection.md)的调用中传递此 **GUID** 以访问配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="15406-131">You can pass this **GUID** in a call to [IProviderAdmin::OpenProfileSection](iprovideradmin-openprofilesection.md) to access the profile section.</span></span> 
  

