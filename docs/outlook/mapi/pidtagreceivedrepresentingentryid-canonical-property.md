---
title: PidTagReceivedRepresentingEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagReceivedRepresentingEntryId
api_type:
- COM
ms.assetid: 2ae2266c-f093-41e5-b4d0-e12aa0f03190
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 33e41343e0c159be20ed1499fc24223947975e1d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359092"
---
# <a name="pidtagreceivedrepresentingentryid-canonical-property"></a>PidTagReceivedRepresentingEntryId 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含由接收用户表示的邮件用户的条目标识符。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RCVD_REPRESENTING_ENTRYID  <br/> |
|标识符:  <br/> |0x0043  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |Address  <br/> |
   
## <a name="remarks"></a>注解

此属性是由接收用户表示的邮件用户的地址属性之一。 必须由传入传输提供程序 (它还负责授权或验证代理) 进行设置。 如果未表示邮件用户, 则应将此属性设置为**PR_RECEIVED_BY_ENTRYID** ([PidTagReceivedByEntryId](pidtagreceivedbyentryid-canonical-property.md)) 属性中包含的条目标识符。
  
客户端应用程序答复代表另一个客户端收到的邮件时, 应将该属性从收到的邮件复制到答复的**PR_SENT_REPRESENTING_ENTRYID** ([PidTagSentRepresentingEntryId](pidtagsentrepresentingentryid-canonical-property.md)) 属性。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定允许用于电子邮件对象的属性和操作。
    
[[毫秒-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> 处理客户端与服务器之间的数据传输的顺序和流。
    
[[毫秒-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)
  
> 指定用于连接邮箱和将邮箱配置为代理的方法, 以及当邮件和日历对象代表其他用户操作时与这些对象的交互。
    
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

