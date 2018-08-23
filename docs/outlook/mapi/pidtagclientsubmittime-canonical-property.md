---
title: PidTagClientSubmitTime 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagClientSubmitTime
api_type:
- HeaderDef
ms.assetid: d46e1063-6421-410d-a445-7477fea42089
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8c7ca5b2b6f5f3131c2fcb70ff0043825a68a91f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22580122"
---
# <a name="pidtagclientsubmittime-canonical-property"></a>PidTagClientSubmitTime 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含的日期和时间发件人提交一条消息。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |期限  <br/> |
|标识符：  <br/> |0x0039  <br/> |
|数据类型：  <br/> |PT_SYSTIME  <br/> |
|区域：  <br/> |消息时间  <br/> |
   
## <a name="remarks"></a>注解

存储提供程序将**期限**设置为客户端应用程序调用[IMessage::SubmitMessage](imessage-submitmessage.md)的时间。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 处理邮件和附件的对象。
    
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

