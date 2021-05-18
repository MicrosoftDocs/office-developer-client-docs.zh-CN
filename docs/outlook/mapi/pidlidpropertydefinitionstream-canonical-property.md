---
title: PidLidPropertyDefinitionStream 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidPropertyDefinitionStream
api_type:
- COM
ms.assetid: ead35049-e60e-4b46-bf12-f73d77cd36b2
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b5ddb87111cfb0039cb1150338945615bbd5afc5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315937"
---
# <a name="pidlidpropertydefinitionstream-canonical-property"></a>PidLidPropertyDefinitionStream 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
表示用户定义的字段的定义和邮件的内置字段的数据绑定设置。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidPropDefStream  <br/> |
|属性集：  <br/> |PSETID_Common  <br/> |
|LONG ID (的一) ：  <br/> |0x00008540  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |运行时配置  <br/> |
   
## <a name="remarks"></a>备注

**PidLidPropertyDefinitionStream** 属性的值保存为邮件的自定义窗体定义的一部分。 
  
此属性的值为二进制流。 有关此流的结构的信息，请参阅[PropertyDefinition Stream Structure。](propertydefinition-stream-structure.md) 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关协议规范Exchange Server引用。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[Outlook 项目和字段](outlook-items-and-fields.md)
  
[添加新字段User-Defined定义](how-to-add-a-definition-for-a-new-user-defined-field.md)
  
[PropertyDefinition Stream 示例](propertydefinition-stream-sample.md)
  
[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

