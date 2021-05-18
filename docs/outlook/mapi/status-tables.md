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
  
状态表包含与当前会话状态有关的信息。 每个 MAPI 会话都有一个状态表，其中包括 MAPI 和服务提供商提供的信息。 MAPI 为三行提供数据：一行用于 MAPI 子系统，一行用于 MAPI 后台处理程序，另一行用于集成通讯簿。 由于传输提供程序需要向状态表提供状态信息，因此每个活动传输提供程序都有一行。 通讯簿和邮件存储提供程序可以选择是否支持状态表。 
  
由于每一行由不同的资源提供，因此列集因行而异。 每个状态对象都需要提供一组列以及 MAPI 提供的一组列。 服务提供商可以添加到这些集，以公开提供程序特定的属性。 例如，邮件存储提供程序可能会PR_STORE_RECORD_KEY ( [PidTagStoreRecordKey](pidtagstorerecordkey-canonical-property.md)) ，以向客户端提供其邮件存储的标识符。 客户端必须事先知道存在此额外信息才能使用它。 
  
下表列出了每个状态表行中必须包含的属性。 status 对象的实现者提供一些属性;其他函数由 MAPI 计算。
  
|**status 对象提供的属性**|**MAPI 提供的属性**|
|:-----|:-----|
|**PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md))   <br/> |**PR_PROVIDER_DLL_NAME (** [PidTagProviderDllName](pidtagproviderdllname-canonical-property.md))   <br/> |
|**PR_STATUS_CODE (** [PidTagStatusCode](pidtagstatuscode-canonical-property.md))   <br/> |**PR_RESOURCE_FLAGS (** [PidTagResourceFlags)](pidtagresourceflags-canonical-property.md)  <br/> |
|**PR_RESOURCE_METHODS (** [PidTagResourceMethods)](pidtagresourcemethods-canonical-property.md)  <br/> |**PR_RESOURCE_TYPE (** [PidTagResourceType](pidtagresourcetype-canonical-property.md))   <br/> |
   
如果 status 对象提供标识，则它应设置 **PR_IDENTITY_DISPLAY** ([PidTagIdentityDisplay](pidtagidentitydisplay-canonical-property.md)) 、PR_IDENTITY_ENTRYID ( [PidTagIdentityEntryId](pidtagidentityentryid-canonical-property.md)) 和 **PR_IDENTITY_SEARCH_KEY** ([PidTagIdentitySearchKey](pidtagidentitysearchkey-canonical-property.md)) ，并包括这些属性。 
  
MAPI 计算每个状态表行的四个属性：
  
|||
|:-----|:-----|
|**PR_ENTRYID (** [PidTagEntryId](pidtagentryid-canonical-property.md))   <br/> |**PR_INSTANCE_KEY (** [PidTagInstanceKey](pidtaginstancekey-canonical-property.md))   <br/> |
|**PR_OBJECT_TYPE (** [PidTagObjectType](pidtagobjecttype-canonical-property.md))   <br/> |**PR_ROWID (** [PidTagRowid](pidtagrowid-canonical-property.md))   <br/> |
   
MAPI 将条目标识符分配给状态行，使客户端能够打开相应的状态对象。 还将分配行标识符以标识表中的行，就像标识状态对象中数据的实例键一样。 PR_OBJECT_TYPE 属性设置为 MAPI_STATUS。 
  
为了访问状态表，客户端调用 [IMAPISession：：GetStatusTable](imapisession-getstatustable.md) 方法。 启动后不应立即进行此调用。 这是因为 **GetStatusTable** 必须等待 MAPI 后台处理程序初始化传输提供程序，该操作将延迟到客户端完成登录之后。 **GetStatusTable** 是 MAPI 后台处理程序完成其启动处理后相对快速的调用。 
  
状态表信息可以通过多种方式使用，例如访问状态对象、确定客户端是在连接模式下运行还是脱机模式运行，以及监视提供程序的状态。 例如，客户端可以通过将 **PR_ENTRYID** 属性的值传递给 [IMAPISession：：OpenEntry](imapisession-openentry.md) 方法打开特定服务提供程序的状态对象。 status 对象支持 **IMAPIStatus** 接口，该接口包含更改服务提供程序密码、刷新消息队列、显示配置 属性表 或直接向提供程序确认状态的方法。 状态表信息还可用于构建对话框，以在冗长的操作过程中通知客户端进度。 
  
支持状态表的服务提供商使用 [IMAPISupport：：ModifyStatusRow](imapisupport-modifystatusrow.md) 方法创建和更新其行。 只要行发生了更改，就必须通知注册为接收状态表通知的所有通知接收对象。 如果服务提供商使用 MAPI 通知实用工具，可以调用 [IMAPISupport：：Notify](imapisupport-notify.md) 方法，也可以直接调用每个通知接收器的 [IMAPIAdviseSink：：OnNotify](imapiadvisesink-onnotify.md) 方法。 
  
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

