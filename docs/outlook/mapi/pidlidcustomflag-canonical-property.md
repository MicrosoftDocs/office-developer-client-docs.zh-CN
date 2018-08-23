---
title: PidLidCustomFlag 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidCustomFlag
api_type:
- COM
ms.assetid: bfb7fd1e-774f-9a2f-fbbe-ba7f68ed8663
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: cba4989ec3b1afcadb0caddd4af444cc9c96ebda
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22565954"
---
# <a name="pidlidcustomflag-canonical-property"></a>PidLidCustomFlag 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
指定一条消息自定义方式，例如，使用自定义属性保存的位掩码。
  
## 

|||
|:-----|:-----|
|相关属性：  <br/> |dispidCustomFlag  <br/> |
|长 ID （盖）：  <br/> |0x00008251  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
   
## <a name="remarks"></a>注解

若要检索此属性的值，首先使用**[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)** 获取的属性标记，然后指定**[IMAPIProp::GetProps](imapiprop-getprops.md)** 获取值中的此属性标记。 
  
可能的标志如下所示：
  
****

|**常量**|**值**|
|:-----|:-----|
|INSP_ONEOFFFLAGS  <br/> |0x0D000000  <br/> |
|INSP_PROPDEFINITION  <br/> |0x02000000  <br/> |
   
当调用**IMAPIProp::GetIDsFromNames**，指定以下值所指的输入的参数*lppPropNames* **[MAPINAMEID](mapinameid.md)** 结构。 
  
****

|**Member**|**值**|
|:-----|:-----|
|lpGuid:  <br/> |PSETID_Common  <br/> |
|ulKind:  <br/> |MNID_ID  <br/> |
|Kind.lID:  <br/> |dispidCustomFlag  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义。
    
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

