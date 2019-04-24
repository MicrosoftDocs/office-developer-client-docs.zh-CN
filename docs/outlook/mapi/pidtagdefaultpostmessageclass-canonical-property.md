---
title: PidTagDefaultPostMessageClass 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDefaultPostMessageClass
api_type:
- HeaderDef
ms.assetid: 231c288f-547b-4463-9442-1499661b925e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0ab904625d3a23462a4fedf3b64f49c54b34ad28
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357902"
---
# <a name="pidtagdefaultpostmessageclass-canonical-property"></a>PidTagDefaultPostMessageClass 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含自定义窗体邮件类的名称。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_DEF_POST_MSGCLASS  <br/> |
|标识符:  <br/> |0x36E5  <br/> |
|数据类型：  <br/> |PT_STRING8  <br/> |
|区域：  <br/> |MAPI 容器  <br/> |
   
## <a name="remarks"></a>注解

如果在文件夹上设置了此属性, 则该值必须包含完全的基本邮件类 (例如, "IPM。"联系人" 文件夹或 "IPM" 的联系人。"日历" 文件夹的 "约会"), 或以基本邮件类 (例如, "IPM。MyContact ")。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> 指定约会、会议请求和响应邮件的属性和操作。
    
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

