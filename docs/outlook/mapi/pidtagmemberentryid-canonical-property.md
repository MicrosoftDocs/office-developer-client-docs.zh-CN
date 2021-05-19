---
title: PidTagMemberEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMemberEntryId
api_type:
- HeaderDef
ms.assetid: b1e166fd-7e15-4371-8510-63001317fb90
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 83a645b49e5bb48051bbaedb26058d2da053348b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433036"
---
# <a name="pidtagmemberentryid-canonical-property"></a>PidTagMemberEntryId 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含 SACL 表成员中的系统访问控制列表 (目录) 标识符。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_MEMBER_ENTRYID  <br/> |
|标识符:  <br/> |0x0FFF  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |服务器端规则  <br/> |
   
## <a name="remarks"></a>备注

[IExchangeModifyTable](iexchangemodifytableiunknown.md)接口使用此属性来唯一标识应用 SACL 的一个或多个角色。 在 SACL 表中创建成员后，无法更改 **ENTRYID。** 若要更改它，您必须删除表成员，然后使用不同的 **ENTRYID** 重新创建它。
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

