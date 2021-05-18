---
title: PidTagAttachPathname 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachPathname
api_type:
- HeaderDef
ms.assetid: e19c7cd1-7c56-4f63-8736-d6971c7c5f4d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 05df7fe04f511de9310edc7a8ef09130e6354ad2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327228"
---
# <a name="pidtagattachpathname-canonical-property"></a>PidTagAttachPathname 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含附件的完全限定路径和文件名。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ATTACH_PATHNAME、PR_ATTACH_PATHNAME_A、PR_ATTACH_PATHNAME_W  <br/> |
|标识符:  <br/> |0x3708  <br/> |
|数据类型：  <br/> |PT_STRING8、PT_UNICODE  <br/> |
|区域：  <br/> |邮件附件  <br/> |
   
## <a name="remarks"></a>备注

建议附件子对象公开这些属性。 设置它们表示附件数据不包含在邮件中，但在公用文件服务器上可用。 这些属性需要与任何通过引用指示附件的 **PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) 标志结合使用 **：ATTACH_BY_REFERENCE、ATTACH_BY_REF_RESOLVE** 或 **ATTACH_BY_REF_ONLY**。  
  
每个目录或文件名限制为八个字符名称和一个三字符扩展名。 整个路径限制为 256 个字符。 对于支持长文件名的平台，请设置这些属性PR_ATTACH_LONG_PATHNAME ([PidTagAttachLongPathname](pidtagattachlongpathname-canonical-property.md)) 。  
  
客户端应用程序应在共享文件时 (UNC) 通用命名约定，并且应在文件是本地文件时使用绝对路径。
  
MAPI 仅适用于 ANSI 字符集内的路径和文件名。 在 OEM 字符集内使用路径和文件名的客户端必须先将其转换为 ANSI，然后才能调用 MAPI。 
  
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



[ScLocalPathFromUNC](sclocalpathfromunc.md)
  
[ScUNCFromLocalPath](scuncfromlocalpath.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

