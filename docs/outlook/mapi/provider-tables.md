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
ms.openlocfilehash: a613bd744a113b4378c5bef94fb51f6ae3aa4041
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778576"
---
# <a name="provider-tables"></a>提供程序表

  
  
**适用于**： Outlook 
  
提供程序表包含有关服务提供商的信息。 有两个不同的提供程序表 (由 MAPI 实现和使用的客户端）。 第一个表格，通过调用[IMsgServiceAdmin::GetProviderTable](imsgserviceadmin-getprovidertable.md)方法访问包含有关当前配置文件的提供程序的所有信息。 通过[IProviderAdmin::GetProviderTable](iprovideradmin-getprovidertable.md)，访问第二个表创建表，用于存储有关消息服务的服务提供程序的所有信息。
  
这两个表有另一个差别。 可通过**IMsgServiceAdmin::GetProviderTable**提供程序表包含仅表示服务提供商而可通过**IProviderAdmin::GetProviderTable**表可能包括表示行的行与服务提供程序关联的其他信息。 此额外信息添加到与的 MAPISVC.INF"部分"关键字的配置文件。 当提供程序具有额外的配置文件节时，它**PR_SERVICE_EXTRA_UIDS** ([PidTagServiceExtraUids](pidtagserviceextrauids-canonical-property.md)) 属性中存储以下各节的**MAPIUID**值。 **PR_SERVICE_EXTRA_UIDS**保存在邮件服务配置文件部分。 
  
以下属性构成设置两种类型的提供程序表中所需的列：
  
|||
|:-----|:-----|
|**PR_INSTANCE_KEY**([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))  <br/> |**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))  <br/> |
|**PR_PROVIDER_DISPLAY**([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md))  <br/> |**PR_PROVIDER_DLL_NAME**([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md))  <br/> |
|**PR_PROVIDER_ORDINAL**([PidTagProviderOrdinal](pidtagproviderordinal-canonical-property.md))  <br/> |**PR_PROVIDER_UID**([PidTagProviderUid](pidtagprovideruid-canonical-property.md))  <br/> |
|**PR_RESOURCE_FLAGS**([PidTagResourceFlags](pidtagresourceflags-canonical-property.md))  <br/> |**PR_RESOURCE_TYPE**([PidTagResourceType](pidtagresourcetype-canonical-property.md))  <br/> |
|**PR_SERVICE_NAME**([PidTagServiceName](pidtagservicename-canonical-property.md))  <br/> |**PR_SERVICE_UID**([PidTagServiceUid](pidtagserviceuid-canonical-property.md))  <br/> |
   
可使用提供程序表，以显示当前传输订单或更改它。 若要显示当前的顺序，生成**PR_RESOURCE_TYPE**属性设置为 MAPI_TRANSPORT_PROVIDER 检索仅这些行限制。 然后用作**PR_PROVIDER_ORDINAL**排序关键字表格进行排序和检索[IMAPITable::QueryRows](imapitable-queryrows.md)方法或[HrQueryAllRows](hrqueryallrows.md)函数使用的所有行。 
  
若要更改的传输顺序，应用相同的限制和检索的行。 然后创建从**PR_PROVIDER_UID**属性值，该值代表传输提供程序的唯一标识符的值的数组。 所需的顺序标识符时，将它们传递给[IMsgServiceAdmin::MsgServiceTransportOrder](imsgserviceadmin-msgservicetransportorder.md)方法。 
  
提供程序表中为可用后，将不会反映后续更改，如添加或删除提供程序。
  
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

