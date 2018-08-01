---
title: PidTagListHelp 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagListHelp
api_type:
- HeaderDef
ms.assetid: 403324b8-c992-4823-aa0f-0414b283debc
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7a9a5d090babce8105fab43bf8401448373777cd
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777826"
---
# <a name="pidtaglisthelp-canonical-property"></a>PidTagListHelp 规范属性

  
  
**适用于**： Outlook 
  
包含多用途 Internet 邮件扩展 (MIME) 消息的列表帮助标头字段的值。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_LIST_HELP，PR_LIST_HELP_A，PR_LIST_HELP_W  <br/> |
|标识符：  <br/> |0x1043  <br/> |
|数据类型：  <br/> |PT_STRING8 PT_UNICODE  <br/> |
|区域：  <br/> |其他  <br/> |
   
## <a name="remarks"></a>说明

若要生成列表帮助头字段，客户端必须将**PR_LIST_HELP**或相关联的属性的值设置为所需的值。 MIME 作者必须将此值复制到列表帮助标头字段。 
  
若要设置这些列表服务器相关的属性的值，MIME 客户端必须编写为下表中指定的标题字段：
  
|**属性**|**首选标头字段名称**|**备用标头字段名称**|
|:-----|:-----|:-----|
|**PR_LIST_HELP** <br/> |列表帮助  <br/> |X-列表-帮助  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)
  
> 从 Internet 标准电子邮件约定转换为消息对象。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

