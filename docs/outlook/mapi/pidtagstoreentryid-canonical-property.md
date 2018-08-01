---
title: PidTagStoreEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagStoreEntryId
api_type:
- COM
ms.assetid: 0d705667-19f4-4eda-a068-e65ea8f00d9b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 075c5e894d4b039ce06ca0508b838a7094af8768
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778452"
---
# <a name="pidtagstoreentryid-canonical-property"></a>PidTagStoreEntryId 规范属性

  
  
**适用于**： Outlook 
  
包含消息存储对象所在的位置的唯一项标识符。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_STORE_ENTRYID  <br/> |
|标识符：  <br/> |0x0FFB  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |ID 属性  <br/> |
   
## <a name="remarks"></a>说明

此属性用于与[IMAPISession::OpenMsgStore](imapisession-openmsgstore.md)方法打开的消息存储。 它还用于打开拥有的任何对象的消息存储库。 
  
消息存储区，该属性等同于存储自己**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性。 使用[IMAPISession::CompareEntryIDs](imapisession-compareentryids.md)方法的两个属性，可以将进行比较的客户端应用程序。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件的对象。
    
[[MS OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)
  
> IETF RFC2445、 RFC2446，和 RFC2447，和约会和会议对象之间进行转换。
    
[[MS OXOFLAG]](http://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)
  
> 指定的属性和与标记的操作。
    
[[MS OXSHARE]](http://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)
  
> 共享客户端之间的邮箱文件夹。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

