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
  
MAPI 提供了一个表，该表包含有关 MAPI 子系统、MAPI 后台处理程序、通讯簿或特定服务提供商的状态的信息。 可以通过调用 [IMAPISession：：GetStatusTable 访问此表](imapisession-getstatustable.md)。
  
状态表中的每一行都代表 MAPI 或服务提供商实现的状态对象。 可以使用 status 对象显示提供程序的配置属性表、更改提供程序密码、上载或下载邮件，以及与特定传输提供程序通信。 
  
有两种方法可以访问状态对象：
  
- 通过状态表
    
- 通过登录对象的 **OpenStatusEntry** 方法 
    
由于客户端无法使用登录对象，因此必须使用状态表访问状态对象。 状态表方法是间接的，在打开状态对象之前需要调用几个，并返回指向 **其 IMAPIStatus 实现** 指针。 
  
 **使用状态表打开状态对象**
  
1. 调用 **IMAPIStatus：：GetStatusTable** 以检索 [IMAPITable](imapitableiunknown.md) 指针。 
    
2. 调用状态表 [的 IMAPITable：：SetColumns](imapitable-setcolumns.md)方法，将列集限制为 **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 、PR_RESOURCE_TYPE ([PidTagResourceType](pidtagresourcetype-canonical-property.md)) 和 **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 。 
    
3. 将表视图限制为特定的状态对象。 对于 MAPI 实现，客户端可以使用 PR_RESOURCE_TYPE 定义 **属性限制**。 对于服务提供商实现，客户端可以限制为 **PR_PROVIDER_DISPLAY** ([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md)) 、提供程序的名称或 **PR_PROVIDER_DLL_NAME** ([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md)) （提供程序 DLL 文件的名称）。
    
4. 调用 [IMAPITable：：Restrict](imapitable-restrict.md) 以设置限制。 
    
5. 调用 [HrQueryAllRows（](hrqueryallrows.md)传递 [SPropertyRestriction](spropertyrestriction.md) 结构）以检索表示提供程序状态的行。 
    
6. 调用 [IMAPISession：：OpenEntry，](imapisession-openentry.md)指定状态表行中的条目标识符，以打开状态对象并检索 **IMAPIStatus** 指针。 
    
若要显示属性表，请为目标提供程序调用状态对象的 [IMAPIStatus：：SettingsDialog](imapistatus-settingsdialog.md) 方法。 **SettingsDialog** 显示属性表视图，在某些情况下，更改提供程序的配置属性。 
  
若要与传输提供程序通信，请调用其状态对象的 [IMAPIStatus：：ValidateState](imapistatus-validatestate.md) 方法。 **ValidateState** 可以重新配置传输提供程序，阻止提供程序显示用户界面，并控制涉及从远程服务器下载邮件头的会话，具体取决于您传递的标志。 例如，若要取消下载远程邮件头，将 ABORT_XP_HEADER_OPERATION标志传递到 **ValidateState**。 若要连接或断开与远程服务器的连接，请FORCE_XP_CONNECT或FORCE_XP_DISCONNECT。 若要重新配置提供程序，请传递CONFIG_CHANGED。 
  
实现按需发送或接收邮件的客户端调用传输提供程序或 MAPI 后台处理程序的 [IMAPIStatus：：FlushQueues](imapistatus-flushqueues.md) 方法。 可以将三个标志传递到 方法中：FLUSH_UPLOAD、FLUSH_DOWNLOAD 和 FLUSH_FORCE。 FLUSH_UPLOAD指示提供程序或 MAPI 后台处理程序发送输出队列中等待的任何邮件，而 FLUSH_DOWNLOAD 指示提供程序或 MAPI 后台处理程序接收任何传入邮件。 FLUSH_FORCE可以使用其他任一标志进行设置，使状态对象执行刷新，而不考虑计时。 
  
不要期望能够在任何 MAPI 子系统、MAPI 后台处理程序或通讯簿状态对象上调用 **SettingsDialog** 或 [ChangePassword。](imapistatus-changepassword.md) 子系统和通讯簿状态对象都仅支持 **ValidateState**;MAPI 后台处理程序状态对象除了支持 ValidateState 之外，还支持 **FlushQueues。** 
  
## <a name="see-also"></a>另请参阅



[状态表](status-tables.md)
  
[MAPI 状态对象](mapi-status-objects.md)

