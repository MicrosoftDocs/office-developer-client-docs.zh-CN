---
title: PidTagSenderAddressType 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagSenderAddressType
api_type:
- COM
ms.assetid: ad7f49ac-6fe8-4037-90f3-8dabd5648bed
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1389c1189293955145f14e65f4c0f3e58bec909f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359141"
---
# <a name="pidtagsenderaddresstype-canonical-property"></a>PidTagSenderAddressType 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含邮件发件人的电子邮件地址类型。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SENDER_ADDRTYPE、PR_SENDER_ADDRTYPE_A、PR_SENDER_ADDRTYPE_W  <br/> |
|标识符:  <br/> |0x0C1E  <br/> |
|数据类型：  <br/> |PT_UNICODE、PT_STRING8  <br/> |
|区域：  <br/> |Address  <br/> |
   
## <a name="remarks"></a>注解

这些属性是邮件发件人的地址属性的示例。 它必须由传出传输提供程序设置, 该提供程序决不会传播任何以前存在的值。
  
如果没有任何传输提供程序提供任何发件人地址属性, MAPI 后台处理程序将尝试通过调用条目标识符的[IMAPISession:: QueryIdentity](imapisession-queryidentity.md)方法来填充这些属性。 如果未提供条目标识符, MAPI 后台处理程序会在类型 PT_TSTRING 的所有发件人地址属性中存储 "Unknown"。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定允许用于电子邮件对象的属性和操作。
    
[[毫秒-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> 处理客户端与服务器之间的数据传输的顺序和流。
    
[[毫秒-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)
  
> 在 IETF RFC2445、RFC2446 和 RFC2447 以及约会和会议对象之间进行转换。
    
[[毫秒-OXOPOST]](https://msdn.microsoft.com/library/9b18fdab-aacd-4d73-9534-be9b6ba2f115%28Office.15%29.aspx)
  
> 指定允许用于 post 对象的属性和操作。
    
[[毫秒-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)
  
> 指定允许用于联系人和个人通讯组列表对象的属性和操作。
    
[[毫秒-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)
  
> 将邮件和附件对象编码并解码为高效流表示形式。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为关联属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

