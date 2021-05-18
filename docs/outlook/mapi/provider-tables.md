---
title: 提供程序表
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 99709a4c-cb52-436e-a322-02ded5d65ce5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2b81f4aebae692d28ed492df102d59ba34debf63
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408969"
---
# <a name="provider-tables"></a><span data-ttu-id="9aaa9-103">提供程序表</span><span class="sxs-lookup"><span data-stu-id="9aaa9-103">Provider Tables</span></span>

  
  
<span data-ttu-id="9aaa9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9aaa9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9aaa9-105">提供程序表包含有关服务提供商的信息。</span><span class="sxs-lookup"><span data-stu-id="9aaa9-105">A provider table contains information about service providers.</span></span> <span data-ttu-id="9aaa9-106">有两个不同的提供程序表，这两个表都由 MAPI 实现，并且由客户端使用。</span><span class="sxs-lookup"><span data-stu-id="9aaa9-106">There are two different provider tables, both implemented by MAPI and used by clients.</span></span> <span data-ttu-id="9aaa9-107">通过调用 [IMsgServiceAdmin：：GetProviderTable](imsgserviceadmin-getprovidertable.md) 方法访问的第一个表包含有关当前配置文件的所有提供程序的信息。</span><span class="sxs-lookup"><span data-stu-id="9aaa9-107">The first table, accessed by calling the [IMsgServiceAdmin::GetProviderTable](imsgserviceadmin-getprovidertable.md) method, holds information about all of the providers for the current profile.</span></span> <span data-ttu-id="9aaa9-108">第二个表通过 [IProviderAdmin：：GetProviderTable](iprovideradmin-getprovidertable.md)访问，它创建一个表，用于存储有关邮件服务的所有服务提供程序的信息。</span><span class="sxs-lookup"><span data-stu-id="9aaa9-108">The second table, accessed through [IProviderAdmin::GetProviderTable](iprovideradmin-getprovidertable.md), creates a table that stores information about all of the service providers for a message service.</span></span>
  
<span data-ttu-id="9aaa9-109">这两个表有另一个区别。</span><span class="sxs-lookup"><span data-stu-id="9aaa9-109">These two tables have another difference.</span></span> <span data-ttu-id="9aaa9-110">通过 **IMsgServiceAdmin：：GetProviderTable** 提供的提供程序表仅包含表示服务提供商的行，而通过 **IProviderAdmin：：GetProviderTable** 提供的表可能包含表示与服务提供商关联的其他信息的行。</span><span class="sxs-lookup"><span data-stu-id="9aaa9-110">The provider table available through **IMsgServiceAdmin::GetProviderTable** contains only rows that represent service providers while the table available through **IProviderAdmin::GetProviderTable** may include rows that represent additional information associated with a service provider.</span></span> <span data-ttu-id="9aaa9-111">此额外信息将添加到具有 MAPISVC.INF 的"Sections"关键字的配置文件中。</span><span class="sxs-lookup"><span data-stu-id="9aaa9-111">This extra information is added to the profile with the "Sections" keyword of MAPISVC.INF.</span></span> <span data-ttu-id="9aaa9-112">当提供程序具有额外的配置文件节时，它将这些节的 **MAPIUID** 值存储在 **PR_SERVICE_EXTRA_UIDS** ([PidTagServiceExtraUids](pidtagserviceextrauids-canonical-property.md)) 属性中。</span><span class="sxs-lookup"><span data-stu-id="9aaa9-112">When a provider has extra profile sections, it stores the **MAPIUID** values for these sections in the **PR_SERVICE_EXTRA_UIDS** ([PidTagServiceExtraUids](pidtagserviceextrauids-canonical-property.md)) property.</span></span> <span data-ttu-id="9aaa9-113">**PR_SERVICE_EXTRA_UIDS** 保存在邮件服务配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="9aaa9-113">**PR_SERVICE_EXTRA_UIDS** is saved in the message service profile section.</span></span> 
  
<span data-ttu-id="9aaa9-114">以下属性在两种类型的提供程序表中都设置了所需的列：</span><span class="sxs-lookup"><span data-stu-id="9aaa9-114">The following properties make up the required column set in both types of provider tables:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="9aaa9-115">**PR_INSTANCE_KEY (** [PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="9aaa9-115">**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="9aaa9-116">**PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="9aaa9-116">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="9aaa9-117">**PR_PROVIDER_DISPLAY (** [PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="9aaa9-117">**PR_PROVIDER_DISPLAY** ([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="9aaa9-118">**PR_PROVIDER_DLL_NAME (** [PidTagProviderDllName](pidtagproviderdllname-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="9aaa9-118">**PR_PROVIDER_DLL_NAME** ([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="9aaa9-119">**PR_PROVIDER_ORDINAL (** [PidTagProviderOrdinal)](pidtagproviderordinal-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="9aaa9-119">**PR_PROVIDER_ORDINAL** ([PidTagProviderOrdinal](pidtagproviderordinal-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="9aaa9-120">**PR_PROVIDER_UID (** [PidTagProviderUid](pidtagprovideruid-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="9aaa9-120">**PR_PROVIDER_UID** ([PidTagProviderUid](pidtagprovideruid-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="9aaa9-121">**PR_RESOURCE_FLAGS (** [PidTagResourceFlags)](pidtagresourceflags-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="9aaa9-121">**PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="9aaa9-122">**PR_RESOURCE_TYPE (** [PidTagResourceType](pidtagresourcetype-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="9aaa9-122">**PR_RESOURCE_TYPE** ([PidTagResourceType](pidtagresourcetype-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="9aaa9-123">**PR_SERVICE_NAME (** [PidTagServiceName](pidtagservicename-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="9aaa9-123">**PR_SERVICE_NAME** ([PidTagServiceName](pidtagservicename-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="9aaa9-124">**PR_SERVICE_UID (** [PidTagServiceUid](pidtagserviceuid-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="9aaa9-124">**PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md))</span></span>  <br/> |
   
<span data-ttu-id="9aaa9-125">提供程序表可用于显示当前传输顺序或更改它。</span><span class="sxs-lookup"><span data-stu-id="9aaa9-125">The provider table can be used to display the current transport order or to change it.</span></span> <span data-ttu-id="9aaa9-126">若要显示当前顺序，请建立一个限制，以仅检索 PR_RESOURCE_TYPE **属性设置为** MAPI_TRANSPORT_PROVIDER。</span><span class="sxs-lookup"><span data-stu-id="9aaa9-126">To display the current order, build a restriction to retrieve only those rows with the **PR_RESOURCE_TYPE** property set to MAPI_TRANSPORT_PROVIDER.</span></span> <span data-ttu-id="9aaa9-127">然后使用 **PR_PROVIDER_ORDINAL** 作为排序键对表进行排序，并使用 [IMAPITable：：QueryRows](imapitable-queryrows.md) 方法或 [HrQueryAllRows](hrqueryallrows.md) 函数检索所有行。</span><span class="sxs-lookup"><span data-stu-id="9aaa9-127">Then use **PR_PROVIDER_ORDINAL** as a sort key to sort the table and retrieve all the rows with either the [IMAPITable::QueryRows](imapitable-queryrows.md) method or the [HrQueryAllRows](hrqueryallrows.md) function.</span></span> 
  
<span data-ttu-id="9aaa9-128">若要更改传输顺序，请应用相同的限制并检索行。</span><span class="sxs-lookup"><span data-stu-id="9aaa9-128">To change the transport order, apply the same restriction and retrieve the rows.</span></span> <span data-ttu-id="9aaa9-129">然后，从 PR_PROVIDER_UID **创建一** 个值数组，该数组代表传输提供程序的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="9aaa9-129">Then create an array of values from the **PR_PROVIDER_UID** property that represents the unique identifiers for the transport providers.</span></span> <span data-ttu-id="9aaa9-130">当标识符按所需顺序时，将它们传递给 [IMsgServiceAdmin：：MsgServiceTransportOrder](imsgserviceadmin-msgservicetransportorder.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="9aaa9-130">When the identifiers are in the desired order, pass them to the [IMsgServiceAdmin::MsgServiceTransportOrder](imsgserviceadmin-msgservicetransportorder.md) method.</span></span> 
  
<span data-ttu-id="9aaa9-131">提供程序表可用后，它将不会反映后续更改，例如添加或删除提供程序。</span><span class="sxs-lookup"><span data-stu-id="9aaa9-131">After a provider table has been made available, it will not reflect subsequent changes, such as the addition or deletion of a provider.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9aaa9-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9aaa9-132">See also</span></span>



[<span data-ttu-id="9aaa9-133">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="9aaa9-133">MAPI Tables</span></span>](mapi-tables.md)

