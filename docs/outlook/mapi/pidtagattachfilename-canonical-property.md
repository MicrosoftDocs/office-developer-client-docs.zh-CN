---
title: PidTagAttachFilename 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachFilename
api_type:
- HeaderDef
ms.assetid: cbf34dd6-7733-47f6-9c41-9d82656ca9dc
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c5354618383a97b362348b14aea174d6f2266d6c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22583279"
---
# <a name="pidtagattachfilename-canonical-property"></a>PidTagAttachFilename 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含附件的基文件名和扩展名，不包括路径。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ATTACH_FILENAME，PR_ATTACH_FILENAME_A，PR_ATTACH_FILENAME_W  <br/> |
|标识符：  <br/> |0x3704  <br/> |
|数据类型：  <br/> |PT_STRING8 PT_UNICODE  <br/> |
|区域：  <br/> |邮件附件  <br/> |
   
## <a name="remarks"></a>注解

建议 attachment 对象公开的**PR_ATTACH_METHOD** **ATTACH_BY_VALUE**、 **ATTACH_BY_REFERENCE**、 **ATTACH_BY_REF_RESOLVE**和**ATTACH_BY_REF_ONLY**值与这些属性([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) 属性。 **PR_ATTACH_FILENAME**和关联的属性所需时使用以下任一值。 
  
这些属性可用作建议的文件名保存附件并提供的文件扩展名，如果未提供**PR_ATTACH_EXTENSION** ([PidTagAttachExtension](pidtagattachextension-canonical-property.md)) 属性。 
  
限制为八个字符扩展名为三个字符的文件名称。 支持长文件名的平台，将设置此属性和**PR_ATTACH_LONG_FILENAME** ([PidTagAttachLongFilename](pidtagattachlongfilename-canonical-property.md)) 属性。 
  
MAPI 仅适用于文件的名称，并在其他字符串传递给它，协会 (ANSI) 字符集中。 使用文件名的原始设备制造商 (OEM) 字符集中的客户端应用程序必须将其转换为 ANSI 调用 MAPI 之前。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件的对象。
    
[[MS OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)
  
> 从 Internet 标准电子邮件约定转换为消息对象。
    
[[MS OXORMMS]](http://msdn.microsoft.com/library/a121dda4-48f3-41f8-b12f-170f533038bb%28Office.15%29.aspx)
  
> 指定权限管理编码邮件的属性。
    
[[MS OXOSMIME]](http://msdn.microsoft.com/library/bb17d126-d211-462c-8cd3-454ed33c8746%28Office.15%29.aspx)
  
> 指定 S/MIME 签名和加密的邮件属性。
    
[[MS OXTNEF]](http://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)
  
> 进行编码和解码为有效的流表示形式的消息和附件对象。
    
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

