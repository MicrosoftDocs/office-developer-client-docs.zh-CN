---
title: PidTagControlId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagControlId
api_type:
- HeaderDef
ms.assetid: 281bc3e0-7c69-461b-bf09-4281abbb5e1b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b27f59e0bfdcac8eca1751af2f07139f12e2b3a7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32334739"
---
# <a name="pidtagcontrolid-canonical-property"></a>PidTagControlId 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含对话框中使用的控件的唯一标识符。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_CONTROL_ID  <br/> |
|标识符:  <br/> |0x3F07  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |MAPI 显示表  <br/> |
   
## <a name="remarks"></a>注解

此属性包含控件的唯一标识符。 此标识符应包含[GUID](guid.md)结构和**LONG**类型的二进制值。 对话框中的所有控件都应使用相同的**GUID**来标识服务提供程序, 并且每个控件应使用唯一的**长整型**值, 以确保控件不会发生冲突。 
  
此属性在通知中使用。 例如, 在显示表上发送的通知必须设置该属性来唯一标识要更新的控件。 
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为替换名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

