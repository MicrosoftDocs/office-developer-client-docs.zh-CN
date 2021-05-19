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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415150"
---
# <a name="pidtagstoreentryidemsmdbv1-canonical-property"></a>PidTagStoreEntryIdEmsmdbV1 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含 microsoft (2002 Outlook 2002 和早期版本) 的 Microsoft Exchange Server 2010 或 Exchange Server 2013 邮件存储的条目标识符的旧样式。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_STORE_ENTRYID_EMSMDB_V1  <br/> |
|标识符:  <br/> |0x65F60102  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |ID 属性  <br/> |
   
## <a name="remarks"></a>备注

从 Microsoft Outlook 2003 开始，服务器 FQN 已集成到条目 ID 中，从而避免了用于引用的其他 RPC。 但是，这会使条目 ID 更长，并引入更多方案， **其中必须使用 CompareEntryIDs** 方法来确定两个条目 ID 是否等效。 PR_STORE_ENTRYID_EMSMDB_V1 (PidTagStoreIdEmsbdbV1) 属性访问 Microsoft Outlook 2002 (Microsoft Office XP) 及早期版本使用的 Exchange Server 条目 ID 的较旧格式。 这可以节省空间，还可以减少确定条目 ID 何时等效所需的 **CompareEntryIDs** 调用次数。 请注意，如果需要引用，使用较旧的条目 ID 打开邮箱可能会产生一些额外的 RPC。 
  
若要在PR_STORE_ENTRYID_EMSMDB_V1访问 PR_STORE_ENTRYID_EMSMDB_V1 属性，必须使用带 [IMAPIProp：：GetProps](imapiprop-getprops.md) 方法的 MAPI_NO_CACHE 标志绕过缓存。 如果 **PR_STORE_ENTRYID_EMSMDB_V1** 不可用，则代码应回退到PR_STORE_ENTRYID。 只有 Outlook 2003 Microsoft Outlook 2013支持 PR_STORE_ENTRYID_EMSMDB_V1 属性。 
  
## <a name="see-also"></a>另请参阅



[PidTagStoreEntryId 规范属性](pidtagstoreentryid-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

