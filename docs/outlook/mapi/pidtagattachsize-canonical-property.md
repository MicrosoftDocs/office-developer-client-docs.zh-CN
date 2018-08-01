---
title: PidTagAttachSize 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachSize
api_type:
- HeaderDef
ms.assetid: 768b3215-dd9f-4aa0-b52c-178ca81a7b07
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2d6b585c00ffb3d9dd5fb0864d98b0a221c7d8c2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777368"
---
# <a name="pidtagattachsize-canonical-property"></a>PidTagAttachSize 规范属性

  
  
**适用于**： Outlook 
  
包含附件上的所有属性的大小的总和，以字节为单位。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ATTACH_SIZE  <br/> |
|标识符：  <br/> |0x0E20  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |邮件附件  <br/> |
   
## <a name="remarks"></a>说明

建议附件子对象公开**PR_ATTACH_SIZE**属性。 包含在**PR_ATTACH_SIZE**总和包括**PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) 或**PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) 属性的大小。 因此， **PR_ATTACH_SIZE**大于通常表达附件的内容。 
  
可以使用此属性，以检查的附件之前执行调制解调器远程传输大致大小并保存到磁盘上的附件时显示进度指示器。 它是附加的 OLE 对象特别有用。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件的对象。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagMessageSize 规范属性](pidtagmessagesize-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

