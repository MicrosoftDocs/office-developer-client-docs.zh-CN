---
title: PidTagPrimarySendAccount 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagPrimarySendAccount
api_type:
- COM
ms.assetid: 2f268b3b-2e4c-4aea-8879-bdd0ac1df35c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a0f4ae75117dff3610175b785ab3f982cc7e7552
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22590405"
---
# <a name="pidtagprimarysendaccount-canonical-property"></a>PidTagPrimarySendAccount 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含一个字符串，用于将邮件发送第一台服务器的名称。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_PRIMARY_SEND_ACCOUNT  <br/> |
|标识符：  <br/> |0x0E28  <br/> |
|数据类型：  <br/> |PT_UNICODE  <br/> |
|区域：  <br/> |Account  <br/> |
   
## <a name="remarks"></a>注解

指定客户端用于将邮件发送第一台服务器。 这些属性的格式是实现相关。 这些属性可由客户端用来确定哪些服务器直接通过，邮件是可选但值没有任何意义到服务器。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定的属性和操作所允许的电子邮件消息对象。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含列为相关属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

