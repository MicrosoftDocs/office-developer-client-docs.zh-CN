---
title: PidTagOriginalSentRepresentingAddressType 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginalSentRepresentingAddressType
api_type:
- COM
ms.assetid: 93f40161-d4e5-4ef9-a55f-cee62529fc04
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ce3678c5137caec2e9f80c7fc15cde0ae99441ae
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22572527"
---
# <a name="pidtagoriginalsentrepresentingaddresstype-canonical-property"></a>PidTagOriginalSentRepresentingAddressType 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含的名义原始邮件已发送的邮件用户的地址类型。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ORIGINAL_SENT_REPRESENTING_ADDRTYPE，PR_ORIGINAL_SENT_REPRESENTING_ADDRTYPE_A，PR_ORIGINAL_SENT_REPRESENTING_ADDRTYPE_W  <br/> |
|标识符：  <br/> |0x0068  <br/> |
|数据类型：  <br/> |PT_STRING8 PT_UNICODE  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>注解

这些属性是表示原始发件人的邮件的类型。 在对话的线程中使用它们。
  
发送一条消息，代表另一个客户端的客户端应用程序应将这些属性设置为在首次提交邮件**PR_SENT_REPRESENTING_ADDRTYPE** ([PidTagSentRepresentingAddressType](pidtagsentrepresentingaddresstype-canonical-property.md)) 属性的值。 设置后，它应永远不会更改。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定的属性和电子邮件消息对象在允许的操作。
    
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

