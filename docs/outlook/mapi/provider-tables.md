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
# <a name="provider-tables"></a>提供程序表

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供程序表包含有关服务提供商的信息。 有两个不同的提供程序表，这两个表都由 MAPI 实现，并且由客户端使用。 通过调用 [IMsgServiceAdmin：：GetProviderTable](imsgserviceadmin-getprovidertable.md) 方法访问的第一个表包含有关当前配置文件的所有提供程序的信息。 第二个表通过 [IProviderAdmin：：GetProviderTable](iprovideradmin-getprovidertable.md)访问，它创建一个表，用于存储有关邮件服务的所有服务提供程序的信息。
  
这两个表有另一个区别。 通过 **IMsgServiceAdmin：：GetProviderTable** 提供的提供程序表仅包含表示服务提供商的行，而通过 **IProviderAdmin：：GetProviderTable** 提供的表可能包含表示与服务提供商关联的其他信息的行。 此额外信息将添加到具有 MAPISVC.INF 的"Sections"关键字的配置文件中。 当提供程序具有额外的配置文件节时，它将这些节的 **MAPIUID** 值存储在 **PR_SERVICE_EXTRA_UIDS** ([PidTagServiceExtraUids](pidtagserviceextrauids-canonical-property.md)) 属性中。 **PR_SERVICE_EXTRA_UIDS** 保存在邮件服务配置文件部分。 
  
以下属性在两种类型的提供程序表中都设置了所需的列：
  
|||
|:-----|:-----|
|**PR_INSTANCE_KEY (** [PidTagInstanceKey](pidtaginstancekey-canonical-property.md))   <br/> |**PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md))   <br/> |
|**PR_PROVIDER_DISPLAY (** [PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md))   <br/> |**PR_PROVIDER_DLL_NAME (** [PidTagProviderDllName](pidtagproviderdllname-canonical-property.md))   <br/> |
|**PR_PROVIDER_ORDINAL (** [PidTagProviderOrdinal)](pidtagproviderordinal-canonical-property.md)  <br/> |**PR_PROVIDER_UID (** [PidTagProviderUid](pidtagprovideruid-canonical-property.md))   <br/> |
|**PR_RESOURCE_FLAGS (** [PidTagResourceFlags)](pidtagresourceflags-canonical-property.md)  <br/> |**PR_RESOURCE_TYPE (** [PidTagResourceType](pidtagresourcetype-canonical-property.md))   <br/> |
|**PR_SERVICE_NAME (** [PidTagServiceName](pidtagservicename-canonical-property.md))   <br/> |**PR_SERVICE_UID (** [PidTagServiceUid](pidtagserviceuid-canonical-property.md))   <br/> |
   
提供程序表可用于显示当前传输顺序或更改它。 若要显示当前顺序，请建立一个限制，以仅检索 PR_RESOURCE_TYPE **属性设置为** MAPI_TRANSPORT_PROVIDER。 然后使用 **PR_PROVIDER_ORDINAL** 作为排序键对表进行排序，并使用 [IMAPITable：：QueryRows](imapitable-queryrows.md) 方法或 [HrQueryAllRows](hrqueryallrows.md) 函数检索所有行。 
  
若要更改传输顺序，请应用相同的限制并检索行。 然后，从 PR_PROVIDER_UID **创建一** 个值数组，该数组代表传输提供程序的唯一标识符。 当标识符按所需顺序时，将它们传递给 [IMsgServiceAdmin：：MsgServiceTransportOrder](imsgserviceadmin-msgservicetransportorder.md) 方法。 
  
提供程序表可用后，它将不会反映后续更改，例如添加或删除提供程序。
  
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

