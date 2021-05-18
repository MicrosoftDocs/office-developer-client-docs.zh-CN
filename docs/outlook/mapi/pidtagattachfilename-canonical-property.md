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
ms.openlocfilehash: f5dcf90e8224f1bf2e96042a7344109293cc2c3f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32319220"
---
# <a name="pidtagattachfilename-canonical-property"></a>PidTagAttachFilename 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含附件的基文件名和扩展名，不包括路径。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ATTACH_FILENAME、PR_ATTACH_FILENAME_A、PR_ATTACH_FILENAME_W  <br/> |
|标识符:  <br/> |0x3704  <br/> |
|数据类型：  <br/> |PT_STRING8、PT_UNICODE  <br/> |
|区域：  <br/> |邮件附件  <br/> |
   
## <a name="remarks"></a>备注

建议 attachment 对象公开这些属性，这些属性与ATTACH_BY_VALUE、ATTACH_BY_REFERENCE、ATTACH_BY_REF_RESOLVE 和 **ATTACH_BY_REF_ONLY** PR_ATTACH_METHOD  ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) 值相关。 **PR_ATTACH_FILENAME** 这些值之一时，需要指定属性和关联属性。 
  
如果未提供 **PR_ATTACH_EXTENSION** ([PidTagAttachExtension](pidtagattachextension-canonical-property.md)) ，则这些属性可以用作保存附件的建议文件名和提供文件扩展名。 
  
文件名限制为 8 个字符加 3 个字符的扩展名。 对于支持长文件名的平台，请同时设置此属性和 PR_ATTACH_LONG_FILENAME ( [PidTagAttachLongFilename](pidtagattachlongfilename-canonical-property.md)) 属性。 
  
MAPI 仅在美国国家标准协会的 ANSI 字符集内处理文件名 (传递给它的) 字符串。 使用原始设备制造商中的文件名的客户端应用程序 (OEM) 集必须先将其转换为 ANSI，然后才能调用 MAPI。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件对象。
    
[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)
  
> 从 Internet 标准电子邮件约定转换为邮件对象。
    
[[MS-OXORMMS]](https://msdn.microsoft.com/library/a121dda4-48f3-41f8-b12f-170f533038bb%28Office.15%29.aspx)
  
> 指定权限管理编码邮件的属性。
    
[[MS-OXOSMIME]](https://msdn.microsoft.com/library/bb17d126-d211-462c-8cd3-454ed33c8746%28Office.15%29.aspx)
  
> 指定 S/MIME 签名和加密的邮件属性。
    
[[MS-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)
  
> 将邮件和附件对象编码和解码为有效的流表示形式。
    
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

