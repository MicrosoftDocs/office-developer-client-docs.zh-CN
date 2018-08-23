---
title: PidTagAttachLongFilename 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachLongFilename
api_type:
- HeaderDef
ms.assetid: 83b69e8f-0b5a-4992-b5b8-160d3bdfa22a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0f1e86924c0464814e3aa1e219930bd23fc78fb5
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22563483"
---
# <a name="pidtagattachlongfilename-canonical-property"></a>PidTagAttachLongFilename 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含附件的长文件名和扩展名，不包括路径。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ATTACH_LONG_FILENAME，PR_ATTACH_LONG_FILENAME_A，PR_ATTACH_LONG_FILENAME_W  <br/> |
|标识符：  <br/> |0x3707  <br/> |
|数据类型：  <br/> |PT_STRING8 PT_UNICODE  <br/> |
|区域：  <br/> |邮件附件  <br/> |
   
## <a name="remarks"></a>注解

这些属性与 ATTACH_BY_VALUE、 ATTACH_BY_REFERENCE、 ATTACH_BY_REF_RESOLVE 和 ATTACH_BY_REF_ONLY **PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) 属性的值。 支持长文件名的平台应发送时，设置的**PR_ATTACH_LONG_FILENAME**和**PR_ATTACH_FILENAME** ([PidTagAttachFilename](pidtagattachfilename-canonical-property.md)) 属性，并应检查**PR_ATTACH_LONG_FILENAME**首先时接收。 
  
客户端应用程序应将此属性设置为建议的长文件名用于接收邮件主机支持长文件名。 **PR_ATTACH_LONG_FILENAME**可以用作文件名，用于保存附件，并提供文件扩展名，如果未提供**PR_ATTACH_EXTENSION** ([PidTagAttachExtension](pidtagattachextension-canonical-property.md)) 属性。 
  
与供稿**PR_ATTACH_FILENAME**文件名，此名称不是限制为八个字符 filename 扩展名为三个字符。 相反，它可以是最多 256 个字符长，包括文件名、 extension 和分隔符句号。 
  
MAPI 仅适用于 ANSI 字符集中的文件名。 使用 OEM 字符集中的文件名的客户端应用程序必须将其转换为 ANSI 调用 MAPI 之前。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件的对象。
    
[[MS OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)
  
> 从 Internet 标准电子邮件约定转换为消息对象。
    
[[MS OXORMMS]](http://msdn.microsoft.com/library/a121dda4-48f3-41f8-b12f-170f533038bb%28Office.15%29.aspx)
  
> 指定权限管理编码邮件的属性。
    
[[MS OXOUM]](http://msdn.microsoft.com/library/2a0696c5-2caf-4f20-87fb-085db430afec%28Office.15%29.aspx)
  
> 指定的属性和操作所允许的表示语音邮件和传真消息。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mmapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

