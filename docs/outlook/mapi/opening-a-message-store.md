---
title: 打开的消息存储
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 43b23fd7-999a-42c0-8f4d-47f5de266bdb
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 4bab31dbcd1f7139980d7df5559c1ee52a6f167f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22563644"
---
# <a name="opening-a-message-store"></a>打开的消息存储

**适用于**： Outlook 2013 |Outlook 2016 
  
配置文件中，根据客户端将需要在典型的会话过程中打开一个或多个邮件存储区。 打开的消息存储是指访问一个指向其[IMsgStore: IMAPIProp](imsgstoreimapiprop.md)实现。 **IMsgStore**接口提供通知，使文件夹分配，以及访问文件夹和邮件的方法。 
  
客户端打开消息存储在登录和时要修改配置文件。 如果您的客户端允许用户在活动会话过程中添加到配置文件的消息存储，您可以立即打开它们或直到下一个会话中忽略。 通过注册消息存储表上的通知，通知您的新消息存储的可用性。
  
若要打开的消息存储，您必须具有其可用的项标识符。 大多数客户端访问他们希望通过消息存储表打开的消息存储的项标识符。 但是，某些消息存储文档其条目标识符，从而启用客户端，以绕过邮件存储表，构造所需的项标识符的格式。 它们可以直接向[IMAPISession::OpenMsgStore](imapisession-openmsgstore.md)传递此条目标识符并 MAPI 自动创建配置文件一节提供程序不关联任何消息服务。 
  
## <a name="retrieve-an-entry-identifier-from-the-message-store-table"></a>消息存储表中检索的项标识符
  
1. 调用[IMAPISession::GetMsgStoresTable](imapisession-getmsgstorestable.md)打开消息存储表。 
    
2. 呼叫**IMAPITable::SetColumns**限制到小型列集，其中包括以下各列的表： 
    
   - **PR_PROVIDER_DISPLAY**或**PR_DISPLAY_NAME**
   - **PR_ENTRYID**属性 
   - **PR_MDB_PROVIDER**
   - **PR_RESOURCE_FLAGS**
    
3. 构建筛选出的行值，该值代表要打开的消息存储限制。 有关查找默认的邮件存储的详细信息，请参阅[打开默认邮件存储区](opening-the-default-message-store.md)。 若要查找按名称的消息存储，应用任何属性存在以下限制：
    
   - 为此类型的消息存储的常规名称匹配**PR_PROVIDER_DISPLAY** ([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md))。 例如，PR_PROVIDER_DISPLAY 可能将设置为"个人文件夹"。
    
   - 此类型的消息存储匹配**PR_MDB_PROVIDER** ([PidTagStoreProvider](pidtagstoreprovider-canonical-property.md)) 与特定**MAPIUID** 。 
    
   - 为此特定邮件存储的名称匹配**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))。 例如， **PR_DISPLAY_NAME**可能会设置为"会计年度 2010年我邮件。" 
    
4. 调用[HrQueryAllRows](hrqueryallrows.md)消息存储表中检索相应行。 将**aRow**成员_pprows_参数指向的行集的属性值数组中包含行中的项标识符。 
    
5. 调用[FreeProws](freeprows.md)以释放所指的_pprows_行集。
    
6. 发布消息存储表通过调用其**IUnknown::Release**方法。 
    
如果您已创建要在打开的消息存储的自定义项标识符，调用[WrapStoreEntryID](wrapstoreentryid.md)函数，以将其转换为标准的项标识符。 
  
消息存储的项标识符后，呼叫以将其打开的以下方法之一：
  
- [IMAPISession::OpenMsgStore](imapisession-openmsgstore.md)
- [IMAPISession::OpenEntry](imapisession-openentry.md)
    
如果您需要指定多种消息存储的特殊选项，请调用**OpenMsgStore** 。 **OpenMsgStore**可以取消显示的对话框，请确定的消息存储临时作为或非邮件存储区中，设置访问级别，并推迟错误。 **OpenEntry**允许您仅可以设置访问级别，并推迟错误。 
  
设置 MDB_NO_MAIL 标志指示为 MAPI 消息存储将不使用发送或接收邮件。 MAPI 不会存在此消息存储有关通知 MAPI 后台处理程序。 MDB_TEMPORARY 标志指定邮件存储为临时，这意味着它不能用于存储永久性信息。 消息存储表中不显示临时邮件存储区。 
  
## <a name="see-also"></a>另请参阅

- [IMAPITable::SetColumns](imapitable-setcolumns.md)

