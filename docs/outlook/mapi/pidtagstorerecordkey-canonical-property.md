---
title: PidTagStoreRecordKey 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagStoreRecordKey
api_type:
- COM
ms.assetid: 27347302-bd52-4f62-98f1-6c37f9a66463
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 4598ca5e654308f7701b1dd66adb227599773b7d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778478"
---
# <a name="pidtagstorerecordkey-canonical-property"></a>PidTagStoreRecordKey 规范属性

  
  
**适用于**： Outlook 
  
包含消息存储对象所在唯一的二进制相当的标识符 （记录密钥）。
  
|||
|:-----|:-----|
|关联的属性：  <br/> |PR_STORE_RECORD_KEY  <br/> |
|标识符:  <br/> |0x0FFA  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |ID 属性  <br/> |
   
## <a name="remarks"></a>备注

消息存储区，该属性等同于存储自己**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 属性。
  
该属性与**PR_RECORD_KEY**之间的关系是**PR_STORE_ENTRYID** ([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md)) 和**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 之间的关系相同。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件的对象。
    
[[MS OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)
  
> IETF RFC2445、 RFC2446，和 RFC2447，和约会和会议对象之间进行转换。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[映射到 MAPI 名称的规范属性名称](mapping-canonical-property-names-to-mapi-names.md)
  
[MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

