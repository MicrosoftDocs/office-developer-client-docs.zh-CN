---
title: PidTagFlagStatus 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagFlagStatus
api_type:
- HeaderDef
ms.assetid: b5117360-0939-4535-83fe-3b4a240b5217
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: bca8fccaa43bb3157b3d4e2af7d6aafa64972b41
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316294"
---
# <a name="pidtagflagstatus-canonical-property"></a>PidTagFlagStatus 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定邮件对象的标志状态。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_FLAG_STATUS  <br/> |
|标识符:  <br/> |0x1090  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |其他  <br/> |
   
## <a name="remarks"></a>备注

此属性不能存在于与会议相关的对象上，并且不应存在于任务对象上。 在其他邮件对象上设置时，此属性必须设置为下列值之一：
  
|**数值**|**名称**|**说明**|
|:-----|:-----|:-----|
|不存在  <br/> |不适用  <br/> |未标记  <br/> |
|0x00000001  <br/> |followupComplete  <br/> |已标记完成  <br/> |
|0x00000002  <br/> |followupFlagged  <br/> |已标记  <br/> |
   
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

