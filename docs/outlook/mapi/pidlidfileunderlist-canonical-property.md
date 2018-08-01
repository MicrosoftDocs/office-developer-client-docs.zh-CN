---
title: PidLidFileUnderList 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidFileUnderList
api_type:
- COM
ms.assetid: a84d8143-5fe7-4a33-bce4-aebf7a824d5f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: cec541db3cc46c108d2a5c41b1d5fbd4d8fac4f2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776840"
---
# <a name="pidlidfileunderlist-canonical-property"></a>PidLidFileUnderList 规范属性

  
  
**适用于**： Outlook 
  
指定**dispidFileUnderId** ([PidLidFileUnderId](pidlidfileunderid-canonical-property.md)) 属性的可能值的列表。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidFileUnderList  <br/> |
|属性进行设置：  <br/> |PSETID_Address  <br/> |
|长 ID （盖）：  <br/> |0x00008026  <br/> |
|数据类型：  <br/> |PT_MV_LONG  <br/> |
|区域：  <br/> |联系人  <br/> |
   
## <a name="remarks"></a>说明

每个中的多值属性的值必须是**dispidFileUnderId** [[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)中指定的允许值之一。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
[[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)
  
> 指定的属性和操作所允许的联系人和个人通讯组列表。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

