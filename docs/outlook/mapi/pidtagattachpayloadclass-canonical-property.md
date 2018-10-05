---
title: PidTagAttachPayloadClass 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachPayloadClass
api_type:
- HeaderDef
ms.assetid: bc4de217-8241-45e7-9e97-8f0c1b16691a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6a84e51325fcb60c54c2f6b42af0c26a0efd3382
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25396615"
---
# <a name="pidtagattachpayloadclass-canonical-property"></a>PidTagAttachPayloadClass 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含 MIME X 负载类标头字段的值。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ATTACH_PAYLOAD_CLASS，PR_ATTACH_PAYLOAD_CLASS_A，PR_ATTACH_PAYLOAD_CLASS_W  <br/> |
|标识符：  <br/> |0x371A  <br/> |
|数据类型：  <br/> |PT_STRING8 PT_UNICODE  <br/> |
|区域：  <br/> |Outlook 应用程序  <br/> |
   
## <a name="remarks"></a>说明

若要设置这些属性的值，MIME 客户端应写入负载 X 级标头字段将分析作为附件的 MIME 实体。
  
MIME 读者必须将此标头字段值复制到相应属性的值。 分析作为邮件或邮件正文中，而不是作为附件的 MIME 实体上出现时，MIME 读者应忽略此标头字段。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)
  
> 从 Internet 标准电子邮件约定转换为消息对象。
    
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

