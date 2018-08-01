---
title: PidLidNoteColor 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidNoteColor
api_type:
- COM
ms.assetid: 9d4b8f5f-1789-497c-8010-f83da9ba5966
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7ff0bb5ec1eb56724bee7be7dec13f0474711083
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776919"
---
# <a name="pidlidnotecolor-canonical-property"></a>PidLidNoteColor 规范属性

  
  
**适用于**： Outlook 
  
指定注释的建议的背景的色。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidNoteColor  <br/> |
|属性进行设置：  <br/> |PSETID_Note  <br/> |
|长 ID （盖）：  <br/> |0x00008B00  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |粘滞便笺  <br/> |
   
## <a name="remarks"></a>说明

此属性必须为下表中的项之一：
  
|**值**|**颜色**|
|:-----|:-----|
|0x00000000  <br/> |蓝色  <br/> |
|0x00000001  <br/> |绿色  <br/> |
|0x00000002  <br/> |粉红色  <br/> |
|0x00000003  <br/> |黄色  <br/> |
|0x00000004  <br/> |白色  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
[[MS OXONOTE]](http://msdn.microsoft.com/library/6bf4ed7e-316c-4a3c-be27-5ec93e7ab39f%28Office.15%29.aspx)
  
> 指定的属性和说明在允许的操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

