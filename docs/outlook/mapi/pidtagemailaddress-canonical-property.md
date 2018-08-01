---
title: PidTagEmailAddress 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagEmailAddress
api_type:
- HeaderDef
ms.assetid: bbd1e187-172e-4612-9efe-7c8e52967dfe
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: cb8b7d0fca6b30f75bd35d1e4e48fa359100ad18
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777585"
---
# <a name="pidtagemailaddress-canonical-property"></a>PidTagEmailAddress 规范属性

  
  
**适用于**： Outlook 
  
包含消息的用户的电子邮件地址。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_EMAIL_ADDRESS，PR_EMAIL_ADDRESS_A，PR_EMAIL_ADDRESS_W  <br/> |
|标识符：  <br/> |0x3003  <br/> |
|数据类型：  <br/> |PT_STRING8 PT_UNICODE  <br/> |
|区域：  <br/> |常见的 MAPI  <br/> |
   
## <a name="remarks"></a>说明

这些属性是所有邮件用户的基址属性的示例。 它是以 null 结尾的字符串，其格式有意义仅为基础邮件系统。 
  
与**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) 和**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 寻址的消息中的属性结合使用这些属性。 字符串格式是由**PR_ADDRTYPE**限定。 
  
此属性的有效值包括： 
  
```cpp
network/postoffice/user 
Bruce@XYZZY.COM 
/c=US/a=att/p=Microsoft/o=Finance/ou=Purchasing/s=Furthur/g=Joe 
 
```

## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)
  
> 指定的属性和用户、 联系人、 组和资源的操作列表。
    
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

