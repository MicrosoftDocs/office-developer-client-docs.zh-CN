---
title: PidTagRecipientDisplayName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRecipientDisplayName
api_type:
- COM
ms.assetid: 8373edff-ef3e-4491-8cf3-e6609e1cb9b0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 388ff3e88119e7fff67193104b36bcd23202b6b9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356705"
---
# <a name="pidtagrecipientdisplayname-canonical-property"></a>PidTagRecipientDisplayName 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性的值。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RECIPIENT_DISPLAY_NAME、PR_RECIPIENT_DISPLAY_NAME_A、PR_RECIPIENT_DISPLAY_NAME_W  <br/> |
|标识符:  <br/> |0x5FF6  <br/> |
|数据类型：  <br/> |PT_STRING8、PT_UNICODE  <br/> |
|区域：  <br/> |传输收件人  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供数据类型定义。
    
[[毫秒-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> 定义在远程操作中使用的基本数据结构。
    
[[毫秒-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)
  
> 在 IETF RFC2445、RFC2446 和 RFC2447 以及约会和会议对象之间进行转换。
    
[[毫秒-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件对象。
    
[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定允许用于电子邮件对象的属性和操作。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为替换名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

