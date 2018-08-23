---
title: PidNameKeywords 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidNameKeywords
api_type:
- COM
ms.assetid: bcc0cda0-02bc-49a5-9fb9-850b4c2867c1
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: caa337541b45c2cb602f0848769b3b07028ea0fd
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22590538"
---
# <a name="pidnamekeywords-canonical-property"></a>PidNameKeywords 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含关键字或 message 对象的类别。
  
|||
|:-----|:-----|
|友好名称：  <br/> |无  <br/> |
|属性进行设置：  <br/> |PS_PUBLIC_STRINGS  <br/> |
|属性名称：  <br/> |Keywords  <br/> |
|数据类型：  <br/> |PT_MV_UNICODE  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>注解

多字符串值，该值指定的类别的消息对象，在此属性多值字符串，每个字符串的长度必须少于 256。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件的对象。
    
[[MS OXODOC]](http://msdn.microsoft.com/library/103007c8-5066-4bed-84e3-4465907af098%28Office.15%29.aspx)
  
> 指定的属性和允许对文档的操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

