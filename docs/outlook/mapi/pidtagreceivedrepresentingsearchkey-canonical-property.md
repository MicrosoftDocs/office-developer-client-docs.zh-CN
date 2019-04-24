---
title: PidTagReceivedRepresentingSearchKey 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagReceivedRepresentingSearchKey
api_type:
- COM
ms.assetid: 234c797c-4a3c-4e05-be22-2a2fa377871f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: bcf310138e4b43b1cc36a177194f721c401caba6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356817"
---
# <a name="pidtagreceivedrepresentingsearchkey-canonical-property"></a>PidTagReceivedRepresentingSearchKey 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含接收用户表示的消息用户的搜索关键字。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RCVD_REPRESENTING_SEARCH_KEY  <br/> |
|标识符:  <br/> |0x0052  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |Address  <br/> |
   
## <a name="remarks"></a>注解

此属性是接收用户表示的邮件用户的地址属性之一。 必须由传入传输提供程序 (它还负责授权或验证代理) 进行设置。 如果未表示邮件用户, 则应将此属性设置为**PR_RECEIVED_BY_SEARCH_KEY** ([PidTagReceivedBySearchKey](pidtagreceivedbysearchkey-canonical-property.md)) 属性中包含的搜索关键字。
  
客户端应用程序答复代表另一个客户端收到的邮件时, 应将该属性从收到的邮件复制到答复的**PR_SENT_REPRESENTING_SEARCH_KEY** ([PidTagSentRepresentingSearchKey](pidtagsentrepresentingsearchkey-canonical-property.md)) 属性。
  
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
    
[[毫秒-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)
  
> 指定用于连接邮箱和将邮箱配置为代理的方法, 以及当邮件和日历对象代表其他用户操作时与这些对象的交互。
    
[[毫秒-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)
  
> 将邮件和附件对象编码并解码为高效流表示形式。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为关联属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagSearchKey 规范属性](pidtagsearchkey-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

