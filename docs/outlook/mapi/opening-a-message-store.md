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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326220"
---
# <a name="opening-a-message-store"></a>打开邮件存储

**适用于**：Outlook 2013 | Outlook 2016 
  
根据配置文件的不同, 客户端将需要在典型会话期间打开一个或多个邮件存储。 打开邮件存储区意味着获取指向其[IMsgStore: IMAPIProp](imsgstoreimapiprop.md)实现的指针的访问权限。 **IMsgStore**接口提供通知的方法, 从而执行文件夹分配以及访问文件夹和邮件。 
  
客户端在登录时打开邮件存储, 并在修改配置文件时打开。 如果您的客户端允许用户在活动会话期间向配置文件添加邮件存储区, 则可以立即打开它们, 也可以忽略它们, 直到下一个会话。 通过在邮件存储表上注册通知, 您将收到新邮件存储的可用警报。
  
若要打开邮件存储区, 您必须具有可用的条目标识符。 大多数客户端访问要通过邮件存储库表打开的邮件存储区的条目标识符。 但是, 某些邮件将文档存储在其条目标识符的格式中, 从而使客户端可以绕过邮件存储表并构造必要的条目标识符。 它们可以将此条目标识符直接传递给[IMAPISession:: OpenMsgStore](imapisession-openmsgstore.md)和 MAPI 会自动为提供程序创建配置文件部分, 而无需将其与任何邮件服务相关联。 
  
## <a name="retrieve-an-entry-identifier-from-the-message-store-table"></a>从邮件存储库表中检索条目标识符
  
1. 调用[IMAPISession:: GetMsgStoresTable](imapisession-getmsgstorestable.md)以打开邮件存储库表。 
    
2. 调用**IMAPITable:: SetColumns**将表限制为包含以下列的小列集: 
    
   - **PR_PROVIDER_DISPLAY**或**PR_DISPLAY_NAME**
   - **PR_ENTRYID**属性 
   - **PR_MDB_PROVIDER**
   - **PR_RESOURCE_FLAGS**
    
3. 生成限制以筛选出表示要打开的邮件存储的行。 有关查找默认邮件存储区的详细信息, 请参阅[打开默认邮件存储](opening-the-default-message-store.md)。 若要按名称查找邮件存储, 请应用以下任一属性限制:
    
   - 将**PR_PROVIDER_DISPLAY** ([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md)) 与此类型邮件存储的常规名称相匹配。 例如, PR_PROVIDER_DISPLAY 可能设置为 "个人文件夹"。
    
   - 将**PR_MDB_PROVIDER** ([PidTagStoreProvider](pidtagstoreprovider-canonical-property.md)) 与此类型邮件存储的特定**MAPIUID**进行匹配。 
    
   - 将**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 与此特定邮件存储区的名称进行匹配。 例如, **PR_DISPLAY_NAME**可能设置为 "我的会计年度2010的邮件"。 
    
4. 调用[HrQueryAllRows](hrqueryallrows.md)以检索邮件存储表中的相应行。 行的条目标识符将包含在由_pprows_参数指向的行集的**aRow**成员的属性值数组中。 
    
5. 调用[FreeProws](freeprows.md)以释放_pprows_指向的行集。
    
6. 通过调用其**IUnknown:: Release**方法释放邮件存储库表。 
    
如果已为要打开的邮件存储区创建了自定义条目标识符, 请调用[WrapStoreEntryID](wrapstoreentryid.md)函数将其转换为标准条目标识符。 
  
拥有邮件存储区的条目标识符后, 请调用以下方法之一将其打开:
  
- [IMAPISession::OpenMsgStore](imapisession-openmsgstore.md)
- [IMAPISession::OpenEntry](imapisession-openentry.md)
    
如果需要为邮件存储区指定各种特殊选项, 请调用**OpenMsgStore** 。 **OpenMsgStore**允许您禁止显示对话框、将邮件存储区标识为临时或作为 nonmessaging 存储区、设置访问级别和延迟错误。 **OpenEntry**仅允许您设置访问级别和延迟错误。 
  
设置 MDB_NO_MAIL 标志指示 MAPI 邮件存储将不用于发送或接收邮件。 mapi 不会通知 mapi 后台处理程序是否存在此邮件存储区。 MDB_TEMPORARY 标志将邮件存储区指定为临时邮件, 这意味着它不能用于存储永久信息。 临时邮件存储不会出现在邮件存储库表中。 
  
## <a name="see-also"></a>另请参阅

- [IMAPITable::SetColumns](imapitable-setcolumns.md)

