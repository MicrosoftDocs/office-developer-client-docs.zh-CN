---
title: PidTagOriginalSentRepresentingEmailAddress 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_type:
- COM
ms.assetid: e2c3d2c3-5451-45cb-b0ec-bdbf5b39a0ba
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2530e27993163505b28fa7d08fd5caf4cc9b03be
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341186"
---
# <a name="pidtagoriginalsentrepresentingemailaddress-canonical-property"></a>PidTagOriginalSentRepresentingEmailAddress 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含代表其发送原始邮件的邮件用户的电子邮件地址。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ORIGINAL_SENT_REPRESENTING_EMAIL_ADDRESS、PR_ORIGINAL_SENT_REPRESENTING_EMAIL_ADDRESS_A、PR_ORIGINAL_SENT_REPRESENTING_EMAIL_ADDRESS_W  <br/> |
|标识符:  <br/> |0x0069  <br/> |
|数据类型：  <br/> |PT_STRING8、PT_UNICODE  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>备注

这些属性是邮件的原始表示发件人的地址属性示例。 它在对话线程中使用。
  
代表其他客户端发送邮件的客户端应用程序应在第一次提交邮件时将这些属性设置为 **PR_SENT_REPRESENTING_EMAIL_ADDRESS** ([PidTagSentRepresentingEmailAddress](pidtagsentrepresentingemailaddress-canonical-property.md)) 属性的值。 设置后，不应更改它。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定允许对电子邮件对象执行的属性和操作。
    
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

