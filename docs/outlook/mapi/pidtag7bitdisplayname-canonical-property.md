---
title: PidTag7BitDisplayName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTag7BitDisplayName
api_type:
- HeaderDef
ms.assetid: 803d7c4e-ed80-4d5b-988f-27068a8ccd63
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 4ae7645e45efb461ac53b6718569d909cec76504
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777273"
---
# <a name="pidtag7bitdisplayname-canonical-property"></a>PidTag7BitDisplayName 规范属性

  
  
**适用于**： Outlook 
  
包含邮件用户的名称的 7 位 ASCII 表示形式。 
  
|||
|:-----|:-----|
|关联的属性：  <br/> |PR_7BIT_DISPLAY_NAME，PR_7BIT_DISPLAY_NAME_A，PR_7BIT_DISPLAY_NAME_W  <br/> |
|标识符:  <br/> |0x39FF  <br/> |
|数据类型：  <br/> |PT_STRING8 PT_UNICODE  <br/> |
|区域：  <br/> |通讯簿  <br/> |
   
## <a name="remarks"></a>备注

这些属性映射到 7 位字符集**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性。 某些消息系统，如 Internet 和某些 X.400 链接被限制为 128 个字符 7 位 ASCII 代码集。 与此类邮件系统的网关可提高性能，通过调用[IAddrBook::PrepareRecips](iaddrbook-preparerecips.md)方法直接检索此属性，从而避免额外处理代码转换。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)
  
> 指定的属性和操作对列表的用户、 联系人、 组和资源。
    
[[MS NSPI]](http://msdn.microsoft.com/library/6dd0a3ea-b4d4-4a73-a857-add03a89a543%28Office.15%29.aspx)
  
> 处理与 NSPI 服务器的客户端的通信。
    
[[MS OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> 处理用于客户端和服务器之间传输数据顺序和数据流。
    
[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件的对象。
    
[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定的属性和电子邮件中允许的操作。
    
### <a name="header-files"></a>头文件

Mapitags.h
  
> 包含列为相关属性的属性的定义。
    
Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[映射到 MAPI 名称的规范属性名称](mapping-canonical-property-names-to-mapi-names.md)
  
[MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

