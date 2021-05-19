---
title: PidTagMemberId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMemberId
api_type:
- HeaderDef
ms.assetid: 64faef3c-27b2-49d2-9d0c-8b9d33f1cb71
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b5d1d4456856f1640bbed8589fc0583060cd2520
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342635"
---
# <a name="pidtagmemberid-canonical-property"></a>PidTagMemberId 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含对文件夹或邮箱具有所述权限的表Microsoft Exchange Server标识符。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_MEMBER_ID  <br/> |
|标识符:  <br/> |0x6671  <br/> |
|数据类型：  <br/> |PT_I8  <br/> |
|区域：  <br/> |访问控制  <br/> |
   
## <a name="remarks"></a>备注

此属性返回表的唯一标识符。 目录用户标识符与每个成员标识符相关联，由此属性指定。 [IExchangeModifyTable](iexchangemodifytableiunknown.md)接口使用此属性检索对文件夹具有显式权限的成员的目录条目标识符。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXCPERM]](https://msdn.microsoft.com/library/944ddb65-6249-4c34-a46e-363fcd37195e%28Office.15%29.aspx)
  
> 处理对服务器上存储的文件夹权限列表的检索。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagMemberEntryId 规范属性](pidtagmemberentryid-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

