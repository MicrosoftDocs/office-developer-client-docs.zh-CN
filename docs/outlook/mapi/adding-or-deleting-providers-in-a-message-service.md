---
title: 在邮件服务中添加或删除提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 44bb4d34-ca96-4d5a-93fe-85e09bd7971d
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 569c9d8a7ed3f56d88d83ea6fdac4477d39e50a2
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569482"
---
# <a name="adding-or-deleting-providers-in-a-message-service"></a><span data-ttu-id="08b64-103">在邮件服务中添加或删除提供程序</span><span class="sxs-lookup"><span data-stu-id="08b64-103">Adding or Deleting Providers in a Message Service</span></span>

  
  
<span data-ttu-id="08b64-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="08b64-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="08b64-105">若要添加或删除的消息服务服务提供商，请使用[IProviderAdmin: IUnknown](iprovideradminiunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="08b64-105">To add or delete service providers in a message service, use the [IProviderAdmin : IUnknown](iprovideradminiunknown.md) interface.</span></span> <span data-ttu-id="08b64-106">您可以通过调用[IMsgServiceAdmin::AdminProviders](imsgserviceadmin-adminproviders.md)检索**IProviderAdmin**指针。</span><span class="sxs-lookup"><span data-stu-id="08b64-106">You can retrieve an **IProviderAdmin** pointer by calling [IMsgServiceAdmin::AdminProviders](imsgserviceadmin-adminproviders.md).</span></span> <span data-ttu-id="08b64-107">提供程序表中，通过[IProviderAdmin::GetProviderTable](iprovideradmin-getprovidertable.md)，读取列出了有关当前安装的消息服务中的服务提供程序的信息。</span><span class="sxs-lookup"><span data-stu-id="08b64-107">The provider table, accessable through [IProviderAdmin::GetProviderTable](iprovideradmin-getprovidertable.md), lists information about the service providers currently installed in the message service.</span></span> <span data-ttu-id="08b64-108">客户端和服务提供商可以使用提供程序表中访问的提供程序 DLL 文件，例如，或**MAPIUID**、 显示名称和提供程序以及有关消息服务的信息的类型名称。</span><span class="sxs-lookup"><span data-stu-id="08b64-108">Clients and service providers can use the provider table to access the name of the provider DLL file, for example, or the **MAPIUID**, display name, and type of the provider as well as information about the message service.</span></span> <span data-ttu-id="08b64-109">有关详细信息，请参阅[提供程序表](provider-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="08b64-109">For more information, see [Provider Tables](provider-tables.md).</span></span>
  
 <span data-ttu-id="08b64-110">**若要添加或删除邮件服务中的服务提供商**</span><span class="sxs-lookup"><span data-stu-id="08b64-110">**To add or delete a service provider in a message service**</span></span>
  
1. <span data-ttu-id="08b64-111">调用**AdminServices**方法来访问邮件服务管理对象。</span><span class="sxs-lookup"><span data-stu-id="08b64-111">Call the **AdminServices** method to access a message service administration object.</span></span> 
    
2. <span data-ttu-id="08b64-112">调用[IMsgServiceAdmin::GetMsgServiceTable](imsgserviceadmin-getmsgservicetable.md)访问邮件服务表。</span><span class="sxs-lookup"><span data-stu-id="08b64-112">Call [IMsgServiceAdmin::GetMsgServiceTable](imsgserviceadmin-getmsgservicetable.md) to access the message service table.</span></span> 
    
3. <span data-ttu-id="08b64-113">构建使用和消息服务的名称匹配**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 或**PR_SERVICE_NAME** ([PidTagServiceName](pidtagservicename-canonical-property.md)) [SPropertyRestriction](spropertyrestriction.md)结构在属性限制修改。</span><span class="sxs-lookup"><span data-stu-id="08b64-113">Build a property restriction using an [SPropertyRestriction](spropertyrestriction.md) structure that matches **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) or **PR_SERVICE_NAME** ([PidTagServiceName](pidtagservicename-canonical-property.md)) with the name of the message service to be modified.</span></span> 
    
4. <span data-ttu-id="08b64-114">调用邮件服务表[IMAPITable::FindRow](imapitable-findrow.md)方法，以表示目标的邮件服务表中找到的行。</span><span class="sxs-lookup"><span data-stu-id="08b64-114">Call the message service table's [IMAPITable::FindRow](imapitable-findrow.md) method to locate the row in the table that represents the targeted message service.</span></span> 
    
5. <span data-ttu-id="08b64-115">调用[IMsgServiceAdmin::AdminProviders](imsgserviceadmin-adminproviders.md)检索**IProviderAdmin**指针。</span><span class="sxs-lookup"><span data-stu-id="08b64-115">Call [IMsgServiceAdmin::AdminProviders](imsgserviceadmin-adminproviders.md) to retrieve an **IProviderAdmin** pointer.</span></span> <span data-ttu-id="08b64-116">将**PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) 列作为_lpUID_参数传递从消息服务表格行。</span><span class="sxs-lookup"><span data-stu-id="08b64-116">Pass the **PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) column from the message service table row as the  _lpUID_ parameter.</span></span> 
    
6. <span data-ttu-id="08b64-117">调用[IProviderAdmin::GetProviderTable](iprovideradmin-getprovidertable.md)访问提供程序表中。</span><span class="sxs-lookup"><span data-stu-id="08b64-117">Call [IProviderAdmin::GetProviderTable](iprovideradmin-getprovidertable.md) to access the provider table.</span></span> 
    
7. <span data-ttu-id="08b64-118">构建使用匹配**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 或**PR_PROVIDER_DISPLAY** ([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md)) SPropertyRestriction 结构和服务提供程序的名称在属性限制添加或删除。</span><span class="sxs-lookup"><span data-stu-id="08b64-118">Build a property restriction using an SPropertyRestriction structure that matches **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) or **PR_PROVIDER_DISPLAY** ([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md)) with the name of the service provider to be added or deleted.</span></span> 
    
8. <span data-ttu-id="08b64-119">调用提供程序表中的[IMAPITable::FindRow](imapitable-findrow.md)方法，以代表目标的服务提供程序表中找到的行。</span><span class="sxs-lookup"><span data-stu-id="08b64-119">Call the provider table's [IMAPITable::FindRow](imapitable-findrow.md) method to locate the row in the table that represents the targeted service provider.</span></span> 
    
9. <span data-ttu-id="08b64-120">呼叫[IProviderAdmin::CreateProvider](iprovideradmin-createprovider.md)添加提供程序或[IProviderAdmin::DeleteProvider](iprovideradmin-deleteprovider.md)移除邮件服务。</span><span class="sxs-lookup"><span data-stu-id="08b64-120">Call [IProviderAdmin::CreateProvider](iprovideradmin-createprovider.md) to add the provider or [IProviderAdmin::DeleteProvider](iprovideradmin-deleteprovider.md) to remove it from the message service.</span></span> <span data-ttu-id="08b64-121">为**CreateProvider**，作为_lpszProvider_参数中传递提供程序的**PR_DISPLAY_NAME**属性。</span><span class="sxs-lookup"><span data-stu-id="08b64-121">For **CreateProvider**, pass the provider's **PR_DISPLAY_NAME** property as the  _lpszProvider_ parameter.</span></span> <span data-ttu-id="08b64-122">哪种方法，通过作为_lpUID_参数提供程序的**PR_SERVICE_UID**属性。</span><span class="sxs-lookup"><span data-stu-id="08b64-122">For either method, pass the provider's **PR_SERVICE_UID** property as the  _lpUID_ parameter.</span></span> <span data-ttu-id="08b64-123">已添加或删除的服务提供程序后，更改将不明显，直到创建一个新会话。</span><span class="sxs-lookup"><span data-stu-id="08b64-123">After the service provider has been added or deleted, the change will not be apparent until a new session is created.</span></span> 
    
<span data-ttu-id="08b64-124">另一种方法向一个配置文件服务提供商，专门消息存储提供程序，包括为提供程序构建的项标识符。</span><span class="sxs-lookup"><span data-stu-id="08b64-124">Another technique for adding a service provider, specifically a message store provider, to a profile involves constructing an entry identifier for the provider.</span></span> <span data-ttu-id="08b64-125">由于构建条目标识符要求的其格式的知识，此方法仅用于如果服务提供商已公开其条目标识符格式。</span><span class="sxs-lookup"><span data-stu-id="08b64-125">Because constructing an entry identifier requires knowledge of its format, this technique can only be used if the service provider has made its entry identifier format public.</span></span> 
  
<span data-ttu-id="08b64-126">具有新构造的条目标识符，客户端可以调用[IMAPISession::OpenMsgStore](imapisession-openmsgstore.md)。</span><span class="sxs-lookup"><span data-stu-id="08b64-126">With the newly constructed entry identifier, a client can call [IMAPISession::OpenMsgStore](imapisession-openmsgstore.md).</span></span> <span data-ttu-id="08b64-127">MAPI 自动为服务提供商，创建配置文件中的配置文件一节，但不会将其添加到邮件服务。</span><span class="sxs-lookup"><span data-stu-id="08b64-127">MAPI automatically creates a profile section in the profile for the service provider, but does not add it to a message service.</span></span> 
  
<span data-ttu-id="08b64-128">某些消息服务不允许动态修改; 此类型支持的是最多邮件服务。</span><span class="sxs-lookup"><span data-stu-id="08b64-128">Some message services do not allow this type of dynamic modification; whether or not it is supported is up to the message service.</span></span> <span data-ttu-id="08b64-129">另一种可能也可能不受支持的功能是能够直接访问消息服务的专用配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="08b64-129">Another feature that may or may not be supported is the ability to directly access a message service's private profile sections.</span></span> <span data-ttu-id="08b64-130">如果您使用的消息服务允许此类访问权限，它将发布**GUID**值，该值代表 MAPISVC.INF 中的专用一节。</span><span class="sxs-lookup"><span data-stu-id="08b64-130">If the message service you are using permits such access, it will publish the **GUID** that represents the private section in MAPISVC.INF.</span></span> <span data-ttu-id="08b64-131">可以将此**GUID**传递到[IProviderAdmin::OpenProfileSection](iprovideradmin-openprofilesection.md)呼叫中以访问配置文件部分中。</span><span class="sxs-lookup"><span data-stu-id="08b64-131">You can pass this **GUID** in a call to [IProviderAdmin::OpenProfileSection](iprovideradmin-openprofilesection.md) to access the profile section.</span></span> 
  

