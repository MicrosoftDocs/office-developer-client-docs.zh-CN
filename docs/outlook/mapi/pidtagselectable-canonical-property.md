---
title: PidTagSelectable 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagSelectable
api_type:
- COM
ms.assetid: eeecd957-dd50-4849-9698-8bc7106301e9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 17343a721cbcc642c8cffe95112f25710c0c130c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359015"
---
# <a name="pidtagselectable-canonical-property"></a>PidTagSelectable 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
如果可以选择一次表中的条目，则包含 TRUE。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SELECTABLE  <br/> |
|标识符:  <br/> |0x3609  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |通讯簿容器  <br/> |
   
## <a name="remarks"></a>备注

此属性主要用于一次表的可视格式设置。 可以通过创建一个指示组标题的条目来对模板进行分组。 将标题的此属性设置为 FALSE 可确保用户只能选择组中的实际模板，而不是此标题条目。 
  
此属性仅适用于一对一表，不应用于通讯簿层次结构表。 
  
MAPI 允许通讯簿提供程序以两种方式直观地对项目进行分组。 首先，某些行可以通过不可选择来用作标题。 其次，可以使用[PidTagDepth](pidtagdepth-canonical-property.md) PR_DEPTH (项相对于其标题缩进) 缩进。 此属性在此类分组中用于指示是否可以从列表中选择此项来创建一次地址。 例如，如果客户端具有多个用于生成传真地址的模板，可以按如下方式显示这些模板： 
  
传真模板 (深度 0，不可选择) 
  
 本地 (深度 1，可选择)  
  
 长距离 (深度 1，可选择)  
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXOABKT]](https://msdn.microsoft.com/library/cd5a3e78-1eeb-4a75-88eb-e82c8c96ff31%28Office.15%29.aspx)
  
> 指定允许通讯簿模板使用的属性和操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为关联属性列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[IABLogon::GetOneOffTable](iablogon-getoneofftable.md)
  
[PidTagFolderType 规范属性](pidtagfoldertype-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

