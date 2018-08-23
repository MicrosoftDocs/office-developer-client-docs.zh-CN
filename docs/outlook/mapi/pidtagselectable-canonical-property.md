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
ms.openlocfilehash: d376a5219125866f467be01709a6a611ed8d47f7
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576419"
---
# <a name="pidtagselectable-canonical-property"></a>PidTagSelectable 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含 TRUE，则可以选择一次性表中的条目。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SELECTABLE  <br/> |
|标识符：  <br/> |0x3609  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |通讯簿容器  <br/> |
   
## <a name="remarks"></a>注解

此属性主要用于可视一次性表的格式设置。 模板可以通过创建指示组标题条目进行分组。 此属性设置为 FALSE 的标题，则确保用户可以组和不此标题条目的选择实际的模板。 
  
此属性仅适用于一次性表，不适用于通讯簿层次结构表。 
  
MAPI 允许直观地通过两种方法对项目进行分组的通讯簿提供程序。 首先，某些行可以充当标题的不可选择。 其次，可以使用**PR_DEPTH** ([PidTagDepth](pidtagdepth-canonical-property.md)) 属性相对于其标题缩可选项目。 此属性在此类分组中用于指示此项目可选择列表中创建一个一次性地址。 例如，如果客户端有几个模板构建传真地址，它可以如下所示显示这些： 
  
传真模板 （深度 0，不可选）
  
 本地 （深度 1，可选） 
  
 长途 （深度 1，可选） 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXOABKT]](http://msdn.microsoft.com/library/cd5a3e78-1eeb-4a75-88eb-e82c8c96ff31%28Office.15%29.aspx)
  
> 指定的属性和操作所允许的地址簿模板。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含列为相关属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[IABLogon::GetOneOffTable](iablogon-getoneofftable.md)
  
[PidTagFolderType 规范属性](pidtagfoldertype-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

