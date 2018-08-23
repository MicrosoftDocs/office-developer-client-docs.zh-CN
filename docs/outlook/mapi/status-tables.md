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
ms.openlocfilehash: ee7d729000fbda895918458993437fd4fe72e370
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22591609"
---
# <a name="status-tables"></a>状态表

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
状态表包含与当前会话的状态相关的信息。 一个状态表是为每个 MAPI 会话包含提供通过 MAPI 和服务提供商信息。 MAPI 提供的三行的数据： MAPI 子系统某一行、 某一行的 MAPI 后台处理程序和集成的通讯簿行。 传输提供程序所需状态信息提供给状态表，因为没有一行，每个活动传输提供程序。 地址簿和消息存储提供程序可以选择是否支持状态表。 
  
因为不同资源提供了每个行，则一列的可能各不相同行行。 没有的列的每个状态对象，需要提供一组及一系列 MAPI 提供的列。 服务提供商可以添加这些集来公开特定于提供程序的属性。 例如，消息存储提供程序可能添加**PR_STORE_RECORD_KEY** ([PidTagStoreRecordKey](pidtagstorerecordkey-canonical-property.md)) 提供其消息存储的标识符的客户端。 客户端必须具有此额外信息，以便能够使用它的存在的高级知识。 
  
下表列出了必须在每个状态表格行中的属性。 状态对象的实施者提供的某些属性;通过 MAPI 情况下，其他人来计算。
  
|**提供状态对象的属性**|**提供的 MAPI 属性**|
|:-----|:-----|
|**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))  <br/> |**PR_PROVIDER_DLL_NAME**([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md))  <br/> |
|**PR_STATUS_CODE**([PidTagStatusCode](pidtagstatuscode-canonical-property.md))  <br/> |**PR_RESOURCE_FLAGS**([PidTagResourceFlags](pidtagresourceflags-canonical-property.md))  <br/> |
|**PR_RESOURCE_METHODS**([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md))  <br/> |**PR_RESOURCE_TYPE**([PidTagResourceType](pidtagresourcetype-canonical-property.md))  <br/> |
   
如果状态对象提供了 identity，它应设置**PR_IDENTITY_DISPLAY** ([PidTagIdentityDisplay](pidtagidentitydisplay-canonical-property.md))、 **PR_IDENTITY_ENTRYID** ([PidTagIdentityEntryId](pidtagidentityentryid-canonical-property.md)) 和**PR_IDENTITY_SEARCH_KEY** ([PidTagIdentitySearchKey](pidtagidentitysearchkey-canonical-property.md))，并在表格中包括这些属性。 
  
四个属性通过 MAPI 计算出的每个状态表格行：
  
|||
|:-----|:-----|
|**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))  <br/> |**PR_INSTANCE_KEY**([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))  <br/> |
|**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))  <br/> |**PR_ROWID**([PidTagRowid](pidtagrowid-canonical-property.md))  <br/> |
   
MAPI 将分配给要允许客户端打开相应的状态对象的状态行的项标识符。 行标识符将同时赋标识表中的行，如是实例密钥标识状态对象中的数据。 **PR_OBJECT_TYPE**属性设置为 MAPI_STATUS。 
  
若要访问状态表，客户端调用[IMAPISession::GetStatusTable](imapisession-getstatustable.md)方法。 不应在启动时立即进行此呼叫。 这是因为**GetStatusTable**等待 MAPI 后台处理程序初始化传输提供程序，客户端已完成其登录后，直到推迟操作。 **GetStatusTable**后 MAPI 后台处理程序已完成其启动处理相对较快的呼叫。 
  
表的状态信息可在多种方式，如访问状态对象，以确定是否在连接或脱机模式下，运行客户端以及监控的提供程序的状态。 例如，客户端可以通过将**PR_ENTRYID**属性的值传递给[IMAPISession::OpenEntry](imapisession-openentry.md)方法打开特定服务提供商的状态对象。 状态对象支持**IMAPIStatus**接口，包含方法更改服务提供程序密码、 刷新消息队列，显示配置属性表，或直接与提供程序确认状态的接口。 表的状态信息还可用于构建一个对话框，冗长操作期间告知客户端的进度。 
  
服务提供商并支持状态表使用[IMAPISupport::ModifyStatusRow](imapisupport-modifystatusrow.md)方法创建和更新其行。 当到其行发生了更改时，所有建议必须通知接收器注册接收该状态表通知的对象。 使用 MAPI 通知实用程序或直接调用每个通知接收器[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法时，服务提供商可以调用[IMAPISupport::Notify](imapisupport-notify.md)方法。 
  
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

