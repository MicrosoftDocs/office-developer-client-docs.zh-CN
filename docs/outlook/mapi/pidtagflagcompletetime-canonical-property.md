---
title: PidTagFlagCompleteTime 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagFlagCompleteTime
api_type:
- HeaderDef
ms.assetid: effc738a-30f4-4a5e-b21d-04b50dad1f45
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5dd0d4c19f30e189218b1aeddd333df58e42102a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316287"
---
# <a name="pidtagflagcompletetime-canonical-property"></a>PidTagFlagCompleteTime 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定邮件对象标记为已完成 (UTC) 协调世界时日期和时间。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_FLAG_COMPLETE_TIME  <br/> |
|标识符:  <br/> |0x1091  <br/> |
|数据类型：  <br/> |PT_SYSTIME  <br/> |
|区域：  <br/> |其他  <br/> |
   
## <a name="remarks"></a>备注

如果邮件对象未标记为完成，则删除此属性。 时间最短的分辨率必须为分钟数 (该值必须是 600，000，000 的倍数) 。 如果对象是会议相关的对象，则此属性不能存在，并且不应存在于任务对象上。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)
  
> 指定与标记相关的属性和操作。
    
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

