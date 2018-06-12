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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: ce6925f40e09261494e4edbcbd7314728debbe2b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777854"
---
# <a name="pidtagmemberid-canonical-property"></a>PidTagMemberId 规范属性

  
  
**适用于**： Outlook 
  
包含在 Microsoft Exchange Server 文件夹或邮箱上具有所述的权限表成员标识符。
  
|||
|:-----|:-----|
|关联的属性：  <br/> |PR_MEMBER_ID  <br/> |
|标识符:  <br/> |0x6671  <br/> |
|数据类型：  <br/> |PT_I8  <br/> |
|区域：  <br/> |访问控制  <br/> |
   
## <a name="remarks"></a>备注

此属性返回的标识符到表唯一。 目录用户标识符与每个成员标识符相关联，并由该属性。 此属性由[IExchangeModifyTable](iexchangemodifytableiunknown.md)接口用于检索具有显式权限的文件夹的成员的目录项标识符。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXCPERM]](http://msdn.microsoft.com/library/944ddb65-6249-4c34-a46e-363fcd37195e%28Office.15%29.aspx)
  
> 处理检索存储在服务器的文件夹的权限列表。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagMemberEntryId 规范属性](pidtagmemberentryid-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[映射到 MAPI 名称的规范属性名称](mapping-canonical-property-names-to-mapi-names.md)
  
[MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

