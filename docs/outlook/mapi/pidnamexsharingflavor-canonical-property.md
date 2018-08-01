---
title: PidNameXSharingFlavor 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidNameXSharingFlavor
api_type:
- COM
ms.assetid: 7757fde1-564b-4f3a-9b9e-f80a143690ea
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1f07a11c47c6785bc9a166f11bde8f2e5ef464a0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777255"
---
# <a name="pidnamexsharingflavor-canonical-property"></a>PidNameXSharingFlavor 规范属性

  
  
**适用于**： Outlook 
  
代表**dispidSharingFlavor** ([PidLidSharingFlavor](pidlidsharingflavor-canonical-property.md)) 属性的值。
  
|||
|:-----|:-----|
|友好名称：  <br/> |无  <br/> |
|属性进行设置：  <br/> |PS_INTERNET_HEADERS  <br/> |
|属性名称：  <br/> |X 共享风格  <br/> |
|数据类型：  <br/> |PT_UNICODE  <br/> |
|区域：  <br/> |共享  <br/> |
   
## <a name="remarks"></a>说明

**DispidSharingFlavor**属性必须为下列值之一。 
  
|**值**|**类型的共享邮件**|
|:-----|:-----|
|0x00020310  <br/> |特殊文件夹的共享邀请。  <br/> |
|0x00000310  <br/> |不是一个特殊文件夹的文件夹共享邀请。  <br/> |
|0x00020500  <br/> |共享请求。  <br/> |
|0x00020710  <br/> |这两个共享邀请的特殊文件夹和共享请求收件人的等效的特殊文件夹。  <br/> |
|0x00025100  <br/> |一个共享响应，其中将拒绝请求。  <br/> |
|0x00023310  <br/> |接受的请求 （还一类型的共享邀请） 共享响应。  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
[[MS OXSHARE]](http://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)
  
> 共享客户端之间的邮箱文件夹。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

