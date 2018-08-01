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
ms.openlocfilehash: 74626b735599a5f1485b26fcb65d907b552b3089
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778460"
---
# <a name="pidtagstoreentryidemsmdbv1-canonical-property"></a>PidTagStoreEntryIdEmsmdbV1 规范属性

  
  
**适用于**： Outlook 
  
包含 Microsoft Exchange Server 2010 或 Exchange Server 2013 的消息存储的项标识符的旧样式 （Microsoft Outlook 2002 和更早版本）。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_STORE_ENTRYID_EMSMDB_V1  <br/> |
|标识符：  <br/> |0x65F60102  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |ID 属性  <br/> |
   
## <a name="remarks"></a>说明

启动与 Microsoft Outlook 2003 的服务器 Fqdn 已集成到条目 Id，从而避免其他 Rpc 的引用。 但是，这使得条目 Id 更长时间，并介绍了其中的**CompareEntryIDs**方法必须用于确定是否两个条目 Id 是等效的更多方案。 PR_STORE_ENTRYID_EMSMDB_V1 (PidTagStoreIdEmsbdbV1) 属性访问由 Microsoft Outlook 2002 (Microsoft Office XP) 和早期版本的 Exchange Server 条目 ID 的旧格式。 这可以节省空间并还可以减少所需确定何时条目 Id 是等效的**CompareEntryIDs**呼叫的数目。 请注意，使用旧条目 Id 打开邮箱可能会引发一些其他的 Rpc 是否需要引用。 
  
若要访问在缓存模式下的 PR_STORE_ENTRYID_EMSMDB_V1 属性，必须绕过缓存与[IMAPIProp::GetProps](imapiprop-getprops.md)方法使用 MAPI_NO_CACHE 标志。 如果**PR_STORE_ENTRYID_EMSMDB_V1**不可用，则代码应回退到 PR_STORE_ENTRYID。 仅 Outlook 2003 通过 Microsoft Outlook 2013 支持 PR_STORE_ENTRYID_EMSMDB_V1 属性。 
  
## <a name="see-also"></a>另请参阅



[PidTagStoreEntryId 规范属性](pidtagstoreentryid-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

