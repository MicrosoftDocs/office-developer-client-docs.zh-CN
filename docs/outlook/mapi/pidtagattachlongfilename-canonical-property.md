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
ms.openlocfilehash: 45b6b3fb0c67d854fddf3773c06cef7b36f54992
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339324"
---
# <a name="pidtagattachlongfilename-canonical-property"></a>PidTagAttachLongFilename 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含附件的长文件名和扩展名，不包括路径。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ATTACH_LONG_FILENAME、PR_ATTACH_LONG_FILENAME_A、PR_ATTACH_LONG_FILENAME_W  <br/> |
|标识符:  <br/> |0x3707  <br/> |
|数据类型：  <br/> |PT_STRING8、PT_UNICODE  <br/> |
|区域：  <br/> |邮件附件  <br/> |
   
## <a name="remarks"></a>备注

这些属性与 ATTACH_BY_VALUE [PidTagAttachMethod](pidtagattachmethod-canonical-property.md) PR_ATTACH_METHOD ATTACH_BY_REFERENCE ATTACH_BY_REF_RESOLVE ATTACH_BY_REF_ONLY 属性的 PR_ATTACH_METHOD  (、ATTACH_BY_REF_RESOLVE 和) 值相关。 在发送时，支持长文件名的平台应同时设置 **PR_ATTACH_LONG_FILENAME** 和 **PR_ATTACH_FILENAME** ([PidTagAttachFilename](pidtagattachfilename-canonical-property.md)) 属性，并且应在接收时PR_ATTACH_LONG_FILENAME检查文件。  
  
如果接收邮件的主机支持长文件名，客户端应用程序应将此属性设置为建议使用的长文件名。 **PR_ATTACH_LONG_FILENAME** 用作保存附件的文件名，如果未提供 **PR_ATTACH_EXTENSION** ([PidTagAttachExtension](pidtagattachextension-canonical-property.md)) ，则提供文件名扩展名。 
  
与由 PR_ATTACH_FILENAME 提供的文件名不同，此名称不限于八字符文件名和三字符扩展名。 相反，它可以最多为 256 个字符，包括文件名、扩展名和分隔符段。 
  
MAPI 仅适用于 ANSI 字符集的文件名。 在 OEM 字符集内使用文件名的客户端应用程序必须先将其转换为 ANSI，然后才能调用 MAPI。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件对象。
    
[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)
  
> 从 Internet 标准电子邮件约定转换为邮件对象。
    
[[MS-OXORMMS]](https://msdn.microsoft.com/library/a121dda4-48f3-41f8-b12f-170f533038bb%28Office.15%29.aspx)
  
> 指定权限管理编码邮件的属性。
    
[[MS-OXOUM]](https://msdn.microsoft.com/library/2a0696c5-2caf-4f20-87fb-085db430afec%28Office.15%29.aspx)
  
> 指定允许用于表示语音邮件和传真邮件的属性和操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mmapitags.h
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

