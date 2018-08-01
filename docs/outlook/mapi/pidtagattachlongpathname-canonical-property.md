---
title: PidTagAttachLongPathname 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachLongPathname
api_type:
- HeaderDef
ms.assetid: 3262cf95-48b5-4764-a96e-d752ce35b2dc
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a2230f2c2b1d4793c425694f76bb79fb7284c479
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777334"
---
# <a name="pidtagattachlongpathname-canonical-property"></a>PidTagAttachLongPathname 规范属性

  
  
**适用于**： Outlook 
  
包含附件的完全限定长路径和文件名。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ATTACH_LONG_PATHNAME，PR_ATTACH_LONG_PATHNAME_A，PR_ATTACH_LONG_PATHNAME_W  <br/> |
|标识符：  <br/> |0x370D  <br/> |
|数据类型：  <br/> |PT_STRING8 PT_UNICODE  <br/> |
|区域：  <br/> |邮件附件  <br/> |
   
## <a name="remarks"></a>说明

您可以使用任何指示附件通过引用**PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) 属性的值时，这些属性都适用： **ATTACH_BY_REFERENCE**、 **ATTACH_BY_REF_RESOLVE**或**ATTACH_BY_REF_ONLY**。 支持长文件名的平台应设置**PR_ATTACH_LONG_PATHNAME**或相关的属性和时发送，并应检查**PR_ATTACH_LONG_PATHNAME **PR_ATTACH_PATHNAME** ([PidTagAttachPathname](pidtagattachpathname-canonical-property.md)) 属性**或时接收首先关联的属性。 
  
客户端应用程序应将这些属性设置为建议长路径和文件名用于接收邮件主机支持长文件名。 设置这些属性指示附件数据不包含在邮件，但在常见的文件服务器上可用。 
  
与不同的目录和供稿**PR_ATTACH_PATHNAME**的文件名，这些目录和文件名不限制为八个字符目录或文件名扩展名三个字符。 而是每个目录或文件名可以最多 256 个字符长，包括名称、 extension 和分隔符时间段。 但是，总体路径仅限于 256 个字符。 
  
文件共享，以及本地文件时，应使用绝对路径时，客户端应在大多数情况下使用通用命名约定 (UNC)。
  
MAPI 仅适用于路径和文件名 ansi 字符集。 使用 OEM 字符集中的路径和文件名的客户端应用程序必须将其转换为 ANSI 调用 MAPI 之前。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件的对象。
    
[[MS OXORMMS]](http://msdn.microsoft.com/library/a121dda4-48f3-41f8-b12f-170f533038bb%28Office.15%29.aspx)
  
> 指定权限管理编码邮件的属性。
    
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

