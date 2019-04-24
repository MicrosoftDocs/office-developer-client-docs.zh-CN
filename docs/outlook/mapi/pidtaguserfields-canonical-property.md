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
  
包含有关用户定义的字段的名称、数据类型和其他信息。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_USERFIELDS  <br/> |
|标识符:  <br/> |0x36E3  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |MAPI 文件夹  <br/> |
   
## <a name="remarks"></a>注解

对于每个项目, Outlook 将所有用户定义的字段的定义存储在相应的**IMessage**对象的[PidLidPropertyDefinitionStream](pidlidpropertydefinitionstream-canonical-property.md)属性中。 **PidLidPropertyDefinitionStream**属性包含一个称为[PropertyDefinition](propertydefinition-stream-structure.md)的二进制流, 其中包含字段定义。 有关字段定义的流结构的详细信息, 请参阅[stream 结构](stream-structures.md)。
  
对于每个文件夹, Outlook 会在邮件类 IPC.MS 的相关邮件的**PidTagUserFields**属性中存储该文件夹中所有用户定义的字段的定义。REN.USERFIELDS-每个文件夹假定在其关联的内容表中不包含此类的一条消息。 
  
> [!NOTE]
> 文件夹中用户定义的字段集可能并不一定与其每个项目中的用户定义字段集相匹配。 
  
文件夹中用户定义的字段集显示在 Outlook UI 中的不同位置, 如文件夹的字段选择器。 邮件的**PidTagUserFields**属性包含二进制流**FolderUserFields**, 其中包含文件夹字段定义。 有关文件夹字段定义的流结构的详细信息, 请参阅[folder Fields stream 结构](folder-fields-stream-structures.md)和[FolderUserFields stream Sample](folderuserfields-stream-sample.md)。
  
## <a name="section-heading"></a>节标题

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关 Exchange Server 协议规范的引用。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[Outlook 项目和字段](outlook-items-and-fields.md)
  
[为新的用户定义的字段添加定义](how-to-add-a-definition-for-a-new-user-defined-field.md)
  
[PropertyDefinition 流示例](propertydefinition-stream-sample.md)
  
[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

