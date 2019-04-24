---
title: PidTagMemberName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMemberName
api_type:
- HeaderDef
ms.assetid: e19129bf-d07c-4d2e-9d4d-edbfda088ea7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a119cf1446600153e433c4aae99037d9810015c0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342481"
---
# <a name="pidtagmembername-canonical-property"></a>PidTagMemberName 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含访问控制列表 (ACL) 表的成员的显示名称。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_MEMBER_NAME、PR_MEMBER_NAME_A、PR_MEMBER_NAME_W  <br/> |
|标识符:  <br/> |0x6672  <br/> |
|数据类型：  <br/> |PT_STRING8  <br/> |
|区域：  <br/> |访问控制  <br/> |
   
## <a name="remarks"></a>注解

[IExchangeModifyTable: IUnknown](iexchangemodifytableiunknown.md)接口使用这些属性来显示 ACL 表的成员名称, 该名称是对文件夹或邮箱具有明确权限的人员或角色。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXCPERM]](https://msdn.microsoft.com/library/944ddb65-6249-4c34-a46e-363fcd37195e%28Office.15%29.aspx)
  
> 处理存储在服务器上的文件夹权限列表的检索。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为关联属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[IExchangeModifyTable : IUnknown](iexchangemodifytableiunknown.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

