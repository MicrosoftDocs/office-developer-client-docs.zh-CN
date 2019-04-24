---
title: PidLidGlobalObjectId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidGlobalObjectId
api_type:
- COM
ms.assetid: a4e3f9ab-b7ee-4dff-b7bd-2462c561735c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c7a77e6e295d1433bd617a55656ee15d172f1f06
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357762"
---
# <a name="pidlidglobalobjectid-canonical-property"></a>PidLidGlobalObjectId 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定日历对象的唯一标识符。
  
|||
|:-----|:-----|
|相关属性：  <br/> |LID_GLOBAL_OBJID  <br/> |
|属性集:  <br/> |PSETID_Meeting  <br/> |
|长 ID (盖子):  <br/> |0x00000003  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |会议  <br/> |
   
## <a name="remarks"></a>注解

为 calendar 对象设置后, 此属性的值不得更改。 可以在[[OXOCAL]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)中找到格式的详细说明。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> 指定约会、会议请求和响应邮件的属性和操作。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

