---
title: PidLidSharingFlavor 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidSharingFlavor
api_type:
- COM
ms.assetid: c91ab5c7-82ac-4895-bf54-2863ca5e2410
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 21144af15e7a36f54af3032f735c391b3038305b
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25383609"
---
# <a name="pidlidsharingflavor-canonical-property"></a>PidLidSharingFlavor 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将指定的共享邮件的属性。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidSharingFlavor  <br/> |
|属性进行设置：  <br/> |PSETID_Sharing  <br/> |
|长 ID （盖）：  <br/> |0x00008A18  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |共享  <br/> |
   
## <a name="remarks"></a>说明

此属性的值必须是下列选项之一：
  
|**值**|**共享 Message 对象的类型**|
|:-----|:-----|
|0x00020310  <br/> |特殊文件夹的共享邀请。  <br/> |
|0x00000310  <br/> |不是一个特殊文件夹的文件夹共享邀请。  <br/> |
|0x00020500  <br/> |共享请求。  <br/> |
|0x00020710  <br/> |这两个共享邀请的特殊文件夹和共享请求收件人的等效的特殊文件夹。  <br/> |
|0x00025100  <br/> |共享响应拒绝请求。  <br/> |
|0x00023310  <br/> |接受请求 （还一类型的共享邀请） 共享响应。  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
[[MS OXSHARE]](https://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)
  
> 共享客户端之间的邮箱文件夹。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

