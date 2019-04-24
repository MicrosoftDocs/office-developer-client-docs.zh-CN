---
title: PidTagSentRepresentingSearchKey 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagSentRepresentingSearchKey
api_type:
- COM
ms.assetid: 7a49b944-cef1-4642-9208-b137fd61171a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a9361f3027453742acbe50c3de01d860289cd0ed
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356684"
---
# <a name="pidtagsentrepresentingsearchkey-canonical-property"></a>PidTagSentRepresentingSearchKey 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含发件人代表的邮件用户的搜索关键字。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SENT_REPRESENTING_SEARCH_KEY  <br/> |
|标识符:  <br/> |0x003B  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |Address  <br/> |
   
## <a name="remarks"></a>注解

此属性是发件人表示的邮件用户的地址属性之一。 当客户端应用代表另一个客户端发送邮件时, 它应将所有表示的发件人属性设置为该客户端的值。 邮件用户代表自己发送通常会将表示的发件人属性设置为未设置。
  
如果发送客户端已设置传出传输提供程序, 则该提供程序必须始终将此属性保持不变。 如果它未设置, 则传输提供程序应将其设置为邮件的出站副本上的**PR_SENDER_SEARCH_KEY** ([PidTagSenderSearchKey](pidtagsendersearchkey-canonical-property.md)), 并将其保留在本地副本上。
  
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
    
[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> 指定约会、会议请求和响应邮件的属性和操作。
    
[[毫秒-OXOPOST]](https://msdn.microsoft.com/library/9b18fdab-aacd-4d73-9534-be9b6ba2f115%28Office.15%29.aspx)
  
> 指定允许用于 post 对象的属性和操作。
    
[[毫秒-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)
  
> 指定允许用于联系人和个人通讯组列表的属性和操作。
    
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

