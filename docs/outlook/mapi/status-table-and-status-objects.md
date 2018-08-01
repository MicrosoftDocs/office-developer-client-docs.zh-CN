---
title: 状态表和状态对象
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 203765c1-4b08-4032-a5bf-18f3e752a899
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 774aaea0365066981b9d6426a2579160f6578844
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778877"
---
# <a name="status-table-and-status-objects"></a>状态表和状态对象

  
  
**适用于**： Outlook 
  
MAPI 提供了一个表格的 MAPI 子系统、 MAPI 后台处理程序、 通讯簿或的特定服务提供商的状态信息。 您可以通过调用[IMAPISession::GetStatusTable](imapisession-getstatustable.md)访问此表。
  
状态表中的各行代表由 MAPI 或服务提供商实现状态对象。 您可以使用状态对象显示的提供程序的配置属性表中，更改提供程序的密码，来上载或下载的邮件，以及与特定的传输提供程序进行通信。 
  
有两种方法访问状态对象：
  
- 通过状态表
    
- 通过登录对象的**OpenStatusEntry**方法 
    
由于登录对象是对客户端不可用，您必须使用状态表访问状态对象。 间接，打开状态对象和指向其**IMAPIStatus**实现的指针返回之前，需要几个呼叫状态表方法。 
  
 **使用状态表打开状态对象**
  
1. 调用**IMAPIStatus::GetStatusTable**检索[IMAPITable](imapitableiunknown.md)指针。 
    
2. 呼叫状态表的[IMAPITable::SetColumns](imapitable-setcolumns.md)方法，以限制设置为**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))、 **PR_RESOURCE_TYPE** ([PidTagResourceType](pidtagresourcetype-canonical-property.md)) 和**PR_DISPLAY_NAME** ([列PidTagDisplayName](pidtagdisplayname-canonical-property.md))。
    
3. 限制对特定状态对象表视图。 对于 MAPI 实现，客户端可以定义使用**PR_RESOURCE_TYPE**属性限制。 服务提供程序实现的客户端可以限制在**PR_PROVIDER_DISPLAY** ([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md))，提供程序的名称或**PR_PROVIDER_DLL_NAME** ([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md))，提供程序 DLL 的名称文件。
    
4. 调用[IMAPITable::Restrict](imapitable-restrict.md)设置限制。 
    
5. 呼叫[HrQueryAllRows](hrqueryallrows.md)，传递[SPropertyRestriction](spropertyrestriction.md)结构中，若要检索的行代表提供程序的状态。 
    
6. 调用[IMAPISession::OpenEntry](imapisession-openentry.md)，指定状态表行中的项标识符来打开状态对象和检索**IMAPIStatus**指针。 
    
若要显示属性表，请为目标提供程序调用状态对象的[IMAPIStatus::SettingsDialog](imapistatus-settingsdialog.md)方法。 **留待**显示属性表查看并在某些情况下，更改提供程序的配置属性。 
  
要与传输提供程序通信，调用其状态对象[IMAPIStatus::ValidateState](imapistatus-validatestate.md)方法。 **ValidateState**可以重新配置的传输提供程序、 禁止显示用户界面，提供程序和控制会话涉及下载邮件头从远程服务器，具体取决于您传入的标志。 例如，如果要取消的远程标头下载，传递给**ValidateState**的 ABORT_XP_HEADER_OPERATION 标志。 若要连接或断开与远程服务器的连接，请传递 FORCE_XP_CONNECT 或 FORCE_XP_DISCONNECT。 若要重新配置提供程序，请传递 CONFIG_CHANGED。 
  
实现发送或接收的消息的需求的客户端调用传输提供程序或 MAPI 后台处理程序的[IMAPIStatus::FlushQueues](imapistatus-flushqueues.md)方法。 您可以传递到方法的三个标志： FLUSH_UPLOAD、 FLUSH_DOWNLOAD 和 FLUSH_FORCE。 FLUSH_UPLOAD 指示提供程序或 MAPI 后台处理程序发送时 FLUSH_DOWNLOAD 指示提供程序输出队列中等待的任何邮件或 MAPI 后台处理程序以接收任何传入消息。 若要使该状态对象以执行 timing 无论刷新，可以与其他标志任一设置 FLUSH_FORCE。 
  
不希望能够调用**留待**或[ChangePassword](imapistatus-changepassword.md)上的任何 MAPI 子系统、 MAPI 后台处理程序或地址簿状态对象。 子系统和地址簿状态对象仅支持**ValidateState**;MAPI 后台处理程序状态对象支持**FlushQueues**除了**ValidateState**。
  
## <a name="see-also"></a>另请参阅



[状态表](status-tables.md)
  
[MAPI 状态对象](mapi-status-objects.md)

