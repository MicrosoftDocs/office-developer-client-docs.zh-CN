---
title: PidTagExtendedFolderFlags 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagExtendedFolderFlags
api_type:
- HeaderDef
ms.assetid: e0c04f98-3d66-4ab5-ba05-69f9df539fcf
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4a4d3c940539c23be8ec212cb85e3dd4f3a04aab
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777614"
---
# <a name="pidtagextendedfolderflags-canonical-property"></a>PidTagExtendedFolderFlags 规范属性
 
**适用于**： Outlook 
  
包含有关文件夹扩展的标志。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_EXTENDED_FOLDER_FLAGS  <br/> |
|标识符：  <br/> |0x36DA  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |MAPI 容器  <br/> |
   
## <a name="remarks"></a>说明

此属性是包含文件夹的编码子属性的二进制流。 它的格式设置为一系列的可变长度子项目。 Sub 项目的第 8 位是标志的 ID 字段，这表明哪种类型 sub 该项表示。 第二个 8 位是按照的数据的字节数。
  
可能的 ID 值包括：
  
- Invalid
    
   不要使用此值
    
- ExtendedFlags
    
   数据是格式为四个字节的值：
    
   |**Bits**|**说明**|
   |:-----|:-----|
   |0-1  <br/> |保留。  <br/> |
   |2  <br/> |如果应用程序应显示的策略说明，设置为 0。  <br/> |
   |3-5  <br/> |保留。  <br/> |
   |6-7  <br/> |控件显示的文件夹中的消息数。  <br/> 0-使用默认设置  <br/> 1-使用未读邮件数  <br/> 3-使用消息的总数  <br/> |
   |8-31  <br/> |保留。  <br/> |
   
可以忽略保留的项目，但必须保留现有的值。
    
- SearchFolderID
    
   数据字段是 16 字节字段。 当应用程序创建永久搜索文件夹时，必须相同的值为**PR_WB_SF_TAG**文件夹上设置此字段 ([PidTagSearchFolderId)](pidtagsearchfolderid-canonical-property.md)) 上搜索文件夹消息二进制属性。
    
- ToDoFolderVersion
    
   数据字段是 4 字节字段。 当应用程序创建待办事项搜索文件夹时，必须为-little-endian 整数值的"0x000c0000"的文件夹设置此字段的值：
    
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXOCFG]](http://msdn.microsoft.com/library/7d466dd5-c156-4da9-9a01-75c78e7e1a67%28Office.15%29.aspx)
  
> 指定的位置和客户端和服务器配置数据，如共享的类别列表和工作时间的属性。
    
[[MS OXOSRCH]](http://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)
  
> 指定的属性和操作的搜索文件夹列表配置的操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅

- [MAPI 属性](mapi-properties.md)
- [MAPI 规范属性](mapi-canonical-properties.md)
- [将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
- [将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

