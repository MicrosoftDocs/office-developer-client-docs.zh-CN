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
ms.openlocfilehash: 09d0ee3be704dc55452b615a23ac9cf20d9254d8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331358"
---
# <a name="pidlidnotecolor-canonical-property"></a>PidLidNoteColor 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定便笺的建议背景颜色。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidNoteColor  <br/> |
|属性集：  <br/> |PSETID_Note  <br/> |
|LONG ID (的一) ：  <br/> |0x00008B00  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |便笺  <br/> |
   
## <a name="remarks"></a>备注

此属性必须是下表中的条目之一：
  
|**值**|**Color**|
|:-----|:-----|
|0x00000000  <br/> |蓝色  <br/> |
|0x00000001  <br/> |绿色  <br/> |
|0x00000002  <br/> |粉红色  <br/> |
|0x00000003  <br/> |黄色  <br/> |
|0x00000004  <br/> |白色  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关协议规范Exchange Server引用。
    
[[MS-OXONOTE]](https://msdn.microsoft.com/library/6bf4ed7e-316c-4a3c-be27-5ec93e7ab39f%28Office.15%29.aspx)
  
> 指定允许对注释使用的属性和操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

