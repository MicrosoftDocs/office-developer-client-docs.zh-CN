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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25397427"
---
# <a name="pidtaguserfields-canonical-property"></a>PidTagUserFields 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含名称、 数据类型和用户定义的字段的其他信息。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_USERFIELDS  <br/> |
|标识符：  <br/> |0x36E3  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |MAPI 文件夹  <br/> |
   
## <a name="remarks"></a>说明

对于每个项，Outlook 相应**IMessage**对象的[PidLidPropertyDefinitionStream](pidlidpropertydefinitionstream-canonical-property.md)属性中存储所有用户定义的字段的定义。 **PidLidPropertyDefinitionStream**属性将包含二进制流称为[属性定义](propertydefinition-stream-structure.md)，其中包含的字段定义。 有关字段定义流结构的详细信息，请参阅[流结构](stream-structures.md)。
  
对于每个文件夹中，Outlook 将在该文件夹中的邮件类 IPC.MS 关联的邮件的**PidTagUserFields**属性存储所有用户定义的字段的定义。REN。USERFIELDS-每个文件夹假定包含不多个此类及其关联的内容表中的邮件。 
  
> [!NOTE]
> 一组的文件夹中的用户定义的字段不一定是匹配每个其项目中的用户定义的字段的集。 
  
中的不同位置的 Outlook UI，例如文件夹的字段选择器中显示的文件夹中的用户定义的字段集。 消息的**PidTagUserFields**属性包含二进制数据流， **FolderUserFields**，其中包含的文件夹字段定义。 有关流结构文件夹字段定义的详细信息，请参阅[文件夹字段流结构](folder-fields-stream-structures.md)和[FolderUserFields 流示例](folderuserfields-stream-sample.md)。
  
## <a name="section-heading"></a>节标题

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[Outlook 项和字段](outlook-items-and-fields.md)
  
[为新的用户定义字段添加定义](how-to-add-a-definition-for-a-new-user-defined-field.md)
  
[PropertyDefinition 流示例](propertydefinition-stream-sample.md)
  
[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

