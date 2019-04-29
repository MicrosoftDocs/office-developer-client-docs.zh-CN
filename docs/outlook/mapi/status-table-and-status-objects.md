---
title: 状态表和状态对象
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 203765c1-4b08-4032-a5bf-18f3e752a899
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 3eb190069b43ea1960c3b6edf30a9e0b782d2c41
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425174"
---
# <a name="status-table-and-status-objects"></a>状态表和状态对象

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
mapi 提供了一个表, 其中包含有关 mapi 子系统、mapi 后台处理程序、通讯簿或特定服务提供商状态的信息。 您可以通过调用[IMAPISession:: GetStatusTable](imapisession-getstatustable.md)来访问此表。
  
status 表中的每一行都代表由 MAPI 或服务提供商实现的状态对象。 您可以使用 status 对象显示提供程序的配置属性表、更改提供程序密码、上载或下载邮件以及与特定的传输提供程序进行通信。 
  
有两种访问状态对象的方法:
  
- 通过状态表
    
- 通过登录对象的**OpenStatusEntry**方法 
    
由于客户端无法使用登录对象, 因此必须使用状态表访问 status 对象。 状态表方法是间接的, 在打开 status 对象和返回指向其**IMAPIStatus**实现的指针之前, 需要进行几次调用。 
  
 **使用状态表打开状态对象**
  
1. 调用**IMAPIStatus:: GetStatusTable**以检索[IMAPITable](imapitableiunknown.md)指针。 
    
2. 调用状态表的[IMAPITable:: SetColumns](imapitable-setcolumns.md)方法来限制将列设置为**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))、 **PR_RESOURCE_TYPE** ([PidTagResourceType](pidtagresourcetype-canonical-property.md)) 和**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))。
    
3. 将表视图限制为特定的状态对象。 对于 MAPI 实现, 客户端可以使用**PR_RESOURCE_TYPE**定义属性限制。 对于服务提供程序实现, 客户端可以限制**PR_PROVIDER_DISPLAY** ([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md))、提供程序的名称或**PR_PROVIDER_DLL_NAME** ([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md)) 上的提供程序 DLL 的名称。文本文件.
    
4. 调用[IMAPITable:: Restrict](imapitable-restrict.md)以设置限制。 
    
5. 调用[HrQueryAllRows](hrqueryallrows.md), 在[SPropertyRestriction](spropertyrestriction.md)结构中传递, 以检索表示提供程序状态的行。 
    
6. 调用[IMAPISession:: OpenEntry](imapisession-openentry.md), 从状态表行指定条目标识符, 以打开 status 对象并检索**IMAPIStatus**指针。 
    
若要显示属性表, 请调用目标提供程序的 status 对象的[IMAPIStatus:: SettingsDialog](imapistatus-settingsdialog.md)方法。 **SettingsDialog**显示用于查看的属性表, 在某些情况下, 更改提供程序的配置属性。 
  
若要与传输提供程序通信, 请调用其 status 对象的[IMAPIStatus:: ValidateState](imapistatus-validatestate.md)方法。 **ValidateState**可以重新配置传输提供程序, 阻止提供程序显示用户界面, 并控制包含从远程服务器下载邮件头的会话, 具体取决于您传入的标志。 例如, 若要取消远程头的下载, 请将 ABORT_XP_HEADER_OPERATION 标志传递给**ValidateState**。 若要连接或断开与远程服务器的连接, 请传递 FORCE_XP_CONNECT 或 FORCE_XP_DISCONNECT。 若要重新配置提供程序, 请传递 CONFIG_CHANGED。 
  
按需调用邮件发送或接收邮件的客户端传输提供程序或 MAPI 后台处理程序的[IMAPIStatus:: FlushQueues](imapistatus-flushqueues.md)方法。 您可以将三个标志传递到方法中: FLUSH_UPLOAD、FLUSH_DOWNLOAD 和 FLUSH_FORCE。 FLUSH_UPLOAD 指示提供程序或 mapi 后台处理程序发送在输出队列中等待的任何邮件, 同时 FLUSH_DOWNLOAD 指示提供程序或 mapi 后台处理程序接收任何传入的邮件。 可以使用任何其他标志设置 FLUSH_FORCE, 以使 status 对象执行刷新, 而不考虑计时。 
  
不希望能够在任何 mapi 子系统、mapi 后台处理程序或通讯簿状态对象上调用**SettingsDialog**或[ChangePassword](imapistatus-changepassword.md) 。 "子系统" 和 "通讯簿" 状态对象仅支持**ValidateState**;MAPI 后台处理程序状态对象支持**FlushQueues**以及**ValidateState**。
  
## <a name="see-also"></a>另请参阅



[状态表](status-tables.md)
  
[MAPI 状态对象](mapi-status-objects.md)

