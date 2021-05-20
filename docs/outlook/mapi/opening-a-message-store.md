---
title: 打开邮件存储
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 43b23fd7-999a-42c0-8f4d-47f5de266bdb
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 665c14b285db166e4f2a421d46e57f23e2f7ad52
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432371"
---
# <a name="opening-a-message-store"></a>打开邮件存储

**适用于**：Outlook 2013 | Outlook 2016 
  
根据配置文件，客户端将需要在典型会话期间打开一个或多个邮件存储。 打开消息存储意味着获取指向其 [IMsgStore： IMAPIProp](imsgstoreimapiprop.md) 实现指针的访问权限。 **IMsgStore** 接口提供用于通知、进行文件夹分配以及访问文件夹和邮件的方法。 
  
客户端在登录时和修改配置文件时打开邮件存储。 如果客户端允许用户在活动会话期间将邮件存储添加到配置文件，您可以立即打开它们，也可以忽略它们，直到下一个会话。 通过注册邮件存储表上的通知，将提醒您新邮件存储的可用性。
  
若要打开邮件存储，您必须具有其条目标识符可用。 大多数客户端访问要通过邮件存储表打开的邮件存储的条目标识符。 但是，某些邮件存储记录其条目标识符的格式，从而使客户端可以绕过邮件存储表并构造必要的条目标识符。 他们可以将此条目标识符直接传递到 [IMAPISession：：OpenMsgStore，MAPI](imapisession-openmsgstore.md) 会自动为提供程序创建配置文件节，而不将其与任何邮件服务关联。 
  
## <a name="retrieve-an-entry-identifier-from-the-message-store-table"></a>从邮件存储表中检索条目标识符
  
1. 调用 [IMAPISession：：GetMsgStoresTable](imapisession-getmsgstorestable.md) 以打开消息存储表。 
    
2. 调用 **IMAPITable：：SetColumns** 将表限制为包含以下列的小列集： 
    
   - **PR_PROVIDER_DISPLAY** 或 **PR_DISPLAY_NAME**
   - **PR_ENTRYID** 属性 
   - **PR_MDB_PROVIDER**
   - **PR_RESOURCE_FLAGS**
    
3. 构建限制以筛选出代表要打开的邮件存储的行。 有关查找默认邮件存储的信息，请参阅打开 [默认邮件存储](opening-the-default-message-store.md)。 若要按名称查找邮件存储，请应用以下任一属性限制：
    
   - 将 **PR_PROVIDER_DISPLAY (** [PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md)) 与这种类型的邮件存储的常规名称相匹配。 例如，PR_PROVIDER_DISPLAY设置为"个人文件夹"。
    
   - 将 **PR_MDB_PROVIDER (** [PidTagStoreProvider](pidtagstoreprovider-canonical-property.md)) 与这种类型的邮件存储的特定 **MAPIUID** 相匹配。 
    
   - 将 **PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 匹配为此特定邮件存储的名称。 例如 **，PR_DISPLAY_NAME** 设置为"My Messages for Fiscal Year 2010"。 
    
4. 调用 [HrQueryAllRows](hrqueryallrows.md) 从邮件存储表中检索相应的行。 行的条目标识符将包含在 _pprows_ 参数指向的行集的 **aRow** 成员属性值数组中。 
    
5. 调用 [FreeProws](freeprows.md) 以释放  _pprows 指向的行集_。
    
6. 通过调用其 **IUnknown：：Release** 方法释放邮件存储表。 
    
如果已创建要打开的邮件存储的自定义条目标识符，请调用 [WrapStoreEntryID](wrapstoreentryid.md) 函数将其转换为标准条目标识符。 
  
在拥有邮件存储的条目标识符后，调用以下方法之一以打开它：
  
- [IMAPISession::OpenMsgStore](imapisession-openmsgstore.md)
- [IMAPISession::OpenEntry](imapisession-openentry.md)
    
如果需要为邮件存储指定各种特殊选项，请调用 **OpenMsgStore。** **OpenMsgStore** 允许您禁止显示对话框、将邮件存储标识为临时存储区或非邮件存储、设置访问级别以及延迟错误。 **OpenEntry** 仅允许设置访问级别和延迟错误。 
  
设置 MDB_NO_MAIL 标志将指示 MAPI 邮件存储不用于发送或接收邮件。 MAPI 不会通知 MAPI 后台处理程序存在此消息存储。 此MDB_TEMPORARY标志将邮件存储指定为临时存储，表示它不能用于存储永久信息。 临时邮件存储不显示在邮件存储表中。 
  
## <a name="see-also"></a>另请参阅

- [IMAPITable::SetColumns](imapitable-setcolumns.md)

