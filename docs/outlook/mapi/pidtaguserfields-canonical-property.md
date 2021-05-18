---
title: PidTagUserFields 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: db3a6947-f640-43e8-a2df-71e96560fd81
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 680c9dd9db2743c031de7cda4673d7044ec533e8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360737"
---
# <a name="pidtaguserfields-canonical-property"></a>PidTagUserFields 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含有关数据类型字段的名称、名称和其他信息。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_USERFIELDS  <br/> |
|标识符:  <br/> |0x36E3  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |MAPI 文件夹  <br/> |
   
## <a name="remarks"></a>备注

对于每个项，Outlook定义字段的定义存储在相应 **IMessage** 对象的 [PidLidPropertyDefinitionStream](pidlidpropertydefinitionstream-canonical-property.md)属性中。 **PidLidPropertyDefinitionStream** 属性包含一个称为 [PropertyDefinition](propertydefinition-stream-structure.md)的二进制流，其中包含字段定义。 有关字段定义的流结构详细信息，请参阅 [Stream Structures](stream-structures.md)。
  
对于每个文件夹，Outlook邮件类关联的邮件的 **PidTagUserFields** 属性中存储该文件夹中所有用户定义字段 IPC.MS。REN。USERFIELDS - 每个文件夹假定在其关联内容表中包含此类的邮件不超过一条。 
  
> [!NOTE]
> 文件夹中的用户定义字段集不一定与其中每个项中的用户定义字段集匹配。 
  
文件夹中的用户定义字段集显示在用户界面中Outlook位置，例如文件夹的字段选择器。 邮件的 **PidTagUserFields** 属性包含二进制流 **FolderUserFields**，其中包含文件夹字段定义。 有关文件夹字段定义的流结构详细信息，请参阅 Folder Fields [Stream Structures](folder-fields-stream-structures.md) 和 [FolderUserFields Stream Sample](folderuserfields-stream-sample.md)。
  
## <a name="section-heading"></a>节标题

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关协议规范Exchange Server引用。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[Outlook项目和字段](outlook-items-and-fields.md)
  
[添加新字段User-Defined定义](how-to-add-a-definition-for-a-new-user-defined-field.md)
  
[PropertyDefinition Stream 示例](propertydefinition-stream-sample.md)
  
[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

