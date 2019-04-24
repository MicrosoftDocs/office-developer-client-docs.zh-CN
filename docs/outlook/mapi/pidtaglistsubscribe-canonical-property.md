---
title: PidTagListSubscribe 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagListSubscribe
api_type:
- HeaderDef
ms.assetid: 97387a82-8e40-4c76-818c-2229fac12e01
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: bee11c495d7f1ef21f9af70e6aa89f8c0d0f78b4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32279655"
---
# <a name="pidtaglistsubscribe-canonical-property"></a>PidTagListSubscribe 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含多用途 Internet 邮件扩展 (MIME) 邮件的列表的值-订阅头字段。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_LIST_SUBSCRIBE、PR_LIST_SUBSCRIBE_A、PR_LIST_SUBSCRIBE_W  <br/> |
|标识符:  <br/> |0x1044  <br/> |
|数据类型：  <br/> |PT_STRING8、PT_UNICODE  <br/> |
|区域：  <br/> |其他  <br/> |
   
## <a name="remarks"></a>注解

若要生成列表订阅标头字段, 客户端必须将这些属性的值设置为所需的值。 MIME 编写器必须将这些属性的值复制到列表订阅头字段。
  
若要设置与服务器相关的属性的值 (如这些属性), MIME 客户端必须按下表中所指定的方式写入标头字段。
  
|**Property**|**首选标头字段名称**|**备用标头字段名称**|
|:-----|:-----|:-----|
|**PidTagListSubscribe** <br/> |列表-订阅  <br/> |X-列表-订阅  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)
  
> 从 Internet 标准电子邮件约定转换为邮件对象。
    
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

