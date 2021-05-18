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
ms.openlocfilehash: fe14f6ca101e6a546f99989ecc87b0c516ee5df4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316350"
---
# <a name="pidtagextendedfolderflags-canonical-property"></a>PidTagExtendedFolderFlags 规范属性
 
**适用于**：Outlook 2013 | Outlook 2016 
  
包含有关文件夹的扩展标志。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_EXTENDED_FOLDER_FLAGS  <br/> |
|标识符:  <br/> |0x36DA  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |MAPI 容器  <br/> |
   
## <a name="remarks"></a>备注

此属性是包含文件夹的编码子属性的二进制流。 它的格式设置为一系列可变长度子项。 子项的前 8 位是一个 ID 字段，它指示子项表示的标志类型。 第二个 8 位是后续数据字节数。
  
可能的 ID 值包括：
  
- Invalid
    
   请勿使用此值
    
- ExtendedFlags
    
   数据是四字节值，格式为：
    
   |**位数**|**说明**|
   |:-----|:-----|
   |0-1  <br/> |保留。  <br/> |
   |2  <br/> |如果应用程序应显示策略说明，设置为 0。  <br/> |
   |3-5  <br/> |保留。  <br/> |
   |6-7  <br/> |控制文件夹中邮件数量的显示。  <br/> 0 - 使用默认设置  <br/> 1 - 使用未读邮件的数量  <br/> 3 - 使用邮件总数  <br/> |
   |8-31  <br/> |保留。  <br/> |
   
可以忽略保留项，但必须保留现有值。
    
- SearchFolderID
    
   数据字段是一个 16 字节字段。 当应用程序创建永久搜索文件夹时，它必须将文件夹上的此字段设置为与搜索文件夹邮件的 **PR_WB_SF_TAG** ([PidTagSearchFolderId)](pidtagsearchfolderid-canonical-property.md)) 二进制属性相同的值。
    
- ToDoFolderVersion
    
   数据字段是一个 4 字节字段。 当应用程序创建"to-do"搜索文件夹时，它必须将文件夹上的此字段的值设置为"0x000c0000"的 little-endian 整数值：
    
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXOCFG]](https://msdn.microsoft.com/library/7d466dd5-c156-4da9-9a01-75c78e7e1a67%28Office.15%29.aspx)
  
> 指定客户端和服务器配置数据的位置和属性，例如共享类别列表和工作时间。
    
[[MS-OXOSRCH]](https://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)
  
> 指定用于操作搜索文件夹列表配置的属性和操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅

- [MAPI 属性](mapi-properties.md)
- [MAPI 规范属性](mapi-canonical-properties.md)
- [将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
- [将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

