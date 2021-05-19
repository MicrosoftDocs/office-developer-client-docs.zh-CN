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
ms.openlocfilehash: d8fe8525cf4fc11ac17ed6d73fb5d97e4f2d003e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339366"
---
# <a name="pidtagattachlongpathname-canonical-property"></a>PidTagAttachLongPathname 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含附件的完全限定长路径和文件名。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ATTACH_LONG_PATHNAME、PR_ATTACH_LONG_PATHNAME_A、PR_ATTACH_LONG_PATHNAME_W  <br/> |
|标识符:  <br/> |0x370D  <br/> |
|数据类型：  <br/> |PT_STRING8、PT_UNICODE  <br/> |
|区域：  <br/> |邮件附件  <br/> |
   
## <a name="remarks"></a>备注

这些属性适用于使用通过引用指示附件的任何 **PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) 属性值 **：ATTACH_BY_REFERENCE、ATTACH_BY_REF_RESOLVE** 或 **ATTACH_BY_REF_ONLY**。  支持长文件名的平台应在发送时同时设置 **PR_ATTACH_LONG_PATHNAME** 或关联属性和 **PR_ATTACH_PATHNAME** ([PidTagAttachPathname](pidtagattachpathname-canonical-property.md)) 属性，并且应在接收时先检查 **PR_ATTACH_LONG_PATHNAME** 或关联属性。 
  
如果接收邮件的主机支持长文件名，客户端应用程序应将这些属性设置为建议的长路径和文件名。 设置这些属性表示附件数据不包含在邮件中，但在公用文件服务器上可用。 
  
与 PR_ATTACH_PATHNAME 提供的目录和文件名不同，这些目录和文件名不限于八字符目录或文件名加三字符扩展名。 相反，每个目录或文件名最多为 256 个字符，包括名称、扩展名和分隔符。 但是，整个路径限制为 256 个字符。 
  
客户端应在共享文件时 (UNC) 通用命名约定，并且应在文件是本地文件时使用绝对路径。
  
MAPI 仅适用于 ANSI 字符集内的路径和文件名。 在 OEM 字符集内使用路径和文件名的客户端应用程序必须先将其转换为 ANSI，然后才能调用 MAPI。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件对象。
    
[[MS-OXORMMS]](https://msdn.microsoft.com/library/a121dda4-48f3-41f8-b12f-170f533038bb%28Office.15%29.aspx)
  
> 指定权限管理编码邮件的属性。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

