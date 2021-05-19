---
title: PidTagTemplateid 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagTemplateid
api_type:
- COM
ms.assetid: 1a418c76-ebc7-47f2-ac91-797162e6e099
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 96bcd15606771bd112568ad94133507ab14b2bcd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358819"
---
# <a name="pidtagtemplateid-canonical-property"></a>PidTagTemplateid 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含 PR_ENTRYID **(** [PidTagEntryId](pidtagentryid-canonical-property.md)) ，表示为永久条目 ID 格式。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_TEMPLATEID  <br/> |
|标识符:  <br/> |0x3902  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |MAPI 通讯簿  <br/> |
   
## <a name="remarks"></a>备注

对于名称服务提供程序接口 (NSPI) 服务器上的所有通讯簿对象，此值必须存在，其可分辨名称 (DN) 必须与 PR_EMAIL_ADDRESS ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md) **)** 的值匹配，并且其 DN 必须遵循 DN 格式规范（特别是对象类型）。 
  
脱机通讯簿中的对象上不存在此属性。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)
  
> 指定用户、联系人、组和资源的列表的属性和操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为关联属性列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

