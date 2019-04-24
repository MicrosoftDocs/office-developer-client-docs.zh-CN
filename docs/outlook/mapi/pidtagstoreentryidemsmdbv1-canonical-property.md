---
title: PidTagStoreEntryIdEmsmdbV1 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 40161358-4d41-43cf-83c7-fdd843bec87b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c8bccbfeb7f04745a66831618deff490bc651b02
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278769"
---
# <a name="pidtagstoreentryidemsmdbv1-canonical-property"></a>PidTagStoreEntryIdEmsmdbV1 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含 microsoft Exchange server 2010 或 Exchange server 2013 邮件存储的条目标识符的旧样式 (Microsoft Outlook 2002 及更早版本)。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_STORE_ENTRYID_EMSMDB_V1  <br/> |
|标识符:  <br/> |0x65F60102  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |ID 属性  <br/> |
   
## <a name="remarks"></a>注解

从 Microsoft Outlook 2003 开始, 服务器 fqdn 已集成到条目 id 中, 从而避免了其他用于引用的 rpc。 但是, 这会使条目 id 变长并引入更多方案, 在这些方案中, 必须使用**CompareEntryIDs**方法来确定两个条目 id 是否等效。 PR_STORE_ENTRYID_EMSMDB_V1 (PidTagStoreIdEmsbdbV1) 属性访问 microsoft Outlook 2002 (microsoft Office XP) 和早期版本使用的 Exchange Server 条目 ID 的旧格式。 这样可以节省空间, 还可以减少确定条目 id 何时等效时所需的**CompareEntryIDs**调用数。 请注意, 如果需要引用, 使用较旧的条目 id 打开邮箱可能会产生一些额外的 rpc。 
  
若要在缓存模式下访问 PR_STORE_ENTRYID_EMSMDB_V1 属性, 必须使用 MAPI_NO_CACHE 标志和[IMAPIProp:: GetProps](imapiprop-getprops.md)方法绕过缓存。 如果**PR_STORE_ENTRYID_EMSMDB_V1**不可用, 则代码应回退到 PR_STORE_ENTRYID。 只有 Outlook 2003 至 Microsoft Outlook 2013 支持 PR_STORE_ENTRYID_EMSMDB_V1 属性。 
  
## <a name="see-also"></a>另请参阅



[PidTagStoreEntryId 规范属性](pidtagstoreentryid-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

