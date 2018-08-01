---
title: PidLidAddressBookProviderArrayType 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAddressBookProviderArrayType
api_type:
- COM
ms.assetid: ca4eb6c2-98e9-4dbc-9f5a-f0f257456ead
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3515d0f751cb6d8d0d427079691456519bac97dc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776578"
---
# <a name="pidlidaddressbookproviderarraytype-canonical-property"></a>PidLidAddressBookProviderArrayType 规范属性

  
  
**适用于**： Outlook 
  
指定联系人的电子地址的状态，表示一位标志。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidABPArrayType  <br/> |
|属性进行设置：  <br/> |PSETID_Address  <br/> |
|长 ID （盖）：  <br/> |0x00008029  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |联系人  <br/> |
   
## <a name="remarks"></a>说明

**DispidABPArrayType**属性的值必须是指定联系对象的状态标志的组合。 下表中指定的单个标志。 如果设置此属性， **dispidABPEmailList** ([PidLidAddressBookProviderEmailList](pidlidaddressbookprovideremaillist-canonical-property.md)) 属性必须设置，以及。 这两个属性必须保持相互同步。 例如，如果**dispidABPArrayType**位"0x00000001 设置"， **dispidABPEmailList**值之一必须是"0x00000000"。 
  
|**位**|**说明**|
|:-----|:-----|
|0x00000001  <br/> |为该联系人定义电子邮件 1。  <br/> |
|0x00000002  <br/> |为该联系人定义电子邮件 2。  <br/> |
|0x00000004  <br/> |为该联系人定义电子邮件 3。  <br/> |
|0x00000008  <br/> |商务传真定义为该联系人。  <br/> |
|0x00000010  <br/> |住宅传真定义为该联系人。  <br/> |
|0x00000020  <br/> |主要传真定义为该联系人。  <br/> |
   
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

