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
ms.openlocfilehash: f3e4f19ab43a3da7c4840d762d5131813c83d996
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32361087"
---
# <a name="pidtagattachsize-canonical-property"></a>PidTagAttachSize 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含附件中所有属性的大小的总和 (以字节为单位)。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ATTACH_SIZE  <br/> |
|标识符:  <br/> |0x0E20  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |邮件附件  <br/> |
   
## <a name="remarks"></a>注解

建议附件子类型公开**PR_ATTACH_SIZE**属性。 包含在**PR_ATTACH_SIZE**中的总和包括**PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) 或**PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) 属性的大小。 因此, **PR_ATTACH_SIZE**通常比单独的附件的内容大。 
  
此属性可用于在通过调制解调器执行远程传输之前检查附件的近似大小, 并在将附件保存到磁盘时显示进度指示器。 它对附加的 OLE 对象尤其有用。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件对象。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
mapitags
  
> 包含列为替换名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagMessageSize 规范属性](pidtagmessagesize-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

