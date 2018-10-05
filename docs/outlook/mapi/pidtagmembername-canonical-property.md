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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25390889"
---
# <a name="pidtagmembername-canonical-property"></a>PidTagMemberName 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含成员的访问控制列表 (ACL) 表的显示的名称。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_MEMBER_NAME，PR_MEMBER_NAME_A，PR_MEMBER_NAME_W  <br/> |
|标识符：  <br/> |0x6672  <br/> |
|数据类型：  <br/> |PT_STRING8  <br/> |
|区域：  <br/> |访问控制  <br/> |
   
## <a name="remarks"></a>说明

通过使用这些属性[IExchangeModifyTable: IUnknown](iexchangemodifytableiunknown.md)界面来显示 ACL 表，即的人员或与显式权限的文件夹或邮箱角色的成员的名称。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXCPERM]](https://msdn.microsoft.com/library/944ddb65-6249-4c34-a46e-363fcd37195e%28Office.15%29.aspx)
  
> 处理检索存储在服务器的文件夹的权限列表。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含列为相关属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[IExchangeModifyTable : IUnknown](iexchangemodifytableiunknown.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

