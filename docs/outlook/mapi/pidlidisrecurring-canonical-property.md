---
title: PidLidIsRecurring 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidIsRecurring
api_type:
- COM
ms.assetid: 1f8ecc22-badc-4278-a3c6-fcd398f5bf24
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c920cd42a27c03ffcff63bbd2e0049ddb6f81158
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315433"
---
# <a name="pidlidisrecurring-canonical-property"></a>PidLidIsRecurring 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定对象是否与定期系列相关联。
  
|||
|:-----|:-----|
|相关属性：  <br/> |LID_IS_RECURRING  <br/> |
|属性集:  <br/> |PSETID_Meeting  <br/> |
|长 ID (盖子):  <br/> |0x00000005  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |会议  <br/> |
   
## <a name="remarks"></a>注解

如果值为 TRUE, 则表示对象表示定期系列或异常 (包括孤立实例)。 值为 FALSE, 或缺少此属性时, 表示对象代表单个实例。 请注意此属性与**PR_RECURRING** ([PidLidRecurring](pidlidrecurring-canonical-property.md)) 属性之间的差异。
  
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

