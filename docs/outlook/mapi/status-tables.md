---
title: 状态表
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f2b2aca7-757f-4260-96a5-d0af55189711
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d612738ef8bf0e6925d89a5be7cb423695672d28
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422360"
---
# <a name="status-tables"></a>状态表

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
状态表包含与当前会话状态相关的信息。 每个 mapi 会话都有一个状态表, 其中包含由 MAPI 和服务提供商提供的信息。 mapi 为三行提供数据: mapi 子系统的行、mapi 后台处理程序的一行, 以及集成的通讯簿的行。 由于需要传输提供程序向状态表提供状态信息, 因此每个活动的传输提供程序都有一个行。 通讯簿和邮件存储提供程序可以选择是否支持状态表。 
  
由于每个行都由不同的资源提供, 因此列集可以随行而变化。 有一组列, 每个 status 对象都需要提供一组列, 这些列是 MAPI 提供的一组列。 服务提供程序可以添加到这些集以公开提供程序特定的属性。 例如, 邮件存储提供程序可能会添加**PR_STORE_RECORD_KEY** ([PidTagStoreRecordKey](pidtagstorerecordkey-canonical-property.md)), 以向客户端提供其邮件存储区的标识符。 客户端必须事先知道这些额外信息是否存在才能使用。 
  
下表列出了必须位于每个状态表行中的属性。 status 对象的实施者提供一些属性;其他人由 MAPI 计算。
  
|**status 对象提供的属性**|**MAPI 提供的属性**|
|:-----|:-----|
|**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))  <br/> |**PR_PROVIDER_DLL_NAME**([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md))  <br/> |
|**PR_STATUS_CODE**([PidTagStatusCode](pidtagstatuscode-canonical-property.md))  <br/> |**PR_RESOURCE_FLAGS**([PidTagResourceFlags](pidtagresourceflags-canonical-property.md))  <br/> |
|**PR_RESOURCE_METHODS**([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md))  <br/> |**PR_RESOURCE_TYPE**([PidTagResourceType](pidtagresourcetype-canonical-property.md))  <br/> |
   
如果 status 对象提供标识, 则应设置**PR_IDENTITY_DISPLAY** ([PidTagIdentityDisplay](pidtagidentitydisplay-canonical-property.md))、 **PR_IDENTITY_ENTRYID** ([PidTagIdentityEntryId](pidtagidentityentryid-canonical-property.md)) 和**PR_IDENTITY_SEARCH_KEY** ([PidTagIdentitySearchKey](pidtagidentitysearchkey-canonical-property.md)), 并将这些属性包括在表中。 
  
每个状态表行的 MAPI 计算了四个属性:
  
|||
|:-----|:-----|
|**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))  <br/> |**PR_INSTANCE_KEY**([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))  <br/> |
|**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))  <br/> |**PR_ROWID**([PidTagRowid](pidtagrowid-canonical-property.md))  <br/> |
   
MAPI 将条目标识符分配到状态行, 以使客户端能够打开相应的状态对象。 行标识符也被分配为将表中的行标识为标识状态对象中的数据的实例键。 **PR_OBJECT_TYPE**属性设置为 MAPI_STATUS。 
  
若要访问状态表, 客户端将调用[IMAPISession:: GetStatusTable](imapisession-getstatustable.md)方法。 此调用不应在启动时立即发出。 这是因为, **GetStatusTable**必须等待 MAPI 后台处理程序初始化传输提供程序, 在客户端完成登录之前延迟的操作。 在 MAPI 后台处理程序完成其启动处理后, **GetStatusTable**是一个相对较快的调用。 
  
状态表信息可通过多种方式使用, 如访问 status 对象、确定客户端是否在连接或脱机模式下运行, 并监视提供程序的状态。 例如, 客户端可以通过将**PR_ENTRYID**属性的值传递给[IMAPISession:: OpenEntry](imapisession-openentry.md)方法来打开特定的服务提供程序的 status 对象。 status 对象支持**IMAPIStatus**接口, 该接口包含用于更改服务提供程序密码、刷新邮件队列、显示配置属性表或直接使用提供程序确认状态的方法。 状态表信息还可用于生成对话框, 以便在漫长的操作过程中通知客户端的进度。 
  
支持状态表的服务提供程序使用[IMAPISupport:: ModifyStatusRow](imapisupport-modifystatusrow.md)方法来创建和更新其行。 只要对其行进行了更改, 就必须通知注册为接收状态表通知的所有建议接收器对象。 如果服务提供程序使用 MAPI 通知实用程序或直接调用每个通知接收器的[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)方法, 则服务提供程序可以调用[IMAPISupport:: Notify](imapisupport-notify.md)方法。 
  
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

