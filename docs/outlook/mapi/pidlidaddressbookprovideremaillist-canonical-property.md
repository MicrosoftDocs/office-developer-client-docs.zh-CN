---
title: PidLidAddressBookProviderEmailList 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAddressBookProviderEmailList
api_type:
- COM
ms.assetid: 9c0527ea-e922-4514-b913-d3520350c452
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 053ec531f69ff7734872466b7a661beff3177b2c
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25390357"
---
# <a name="pidlidaddressbookprovideremaillist-canonical-property"></a>PidLidAddressBookProviderEmailList 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定哪个电子通讯属性设置该联系人上。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidABPEmailList  <br/> |
|属性进行设置：  <br/> |PSETID_Address  <br/> |
|长 ID （盖）：  <br/> |0x00008028  <br/> |
|数据类型：  <br/> |PT_MV_LONG  <br/> |
|区域：  <br/> |联系人  <br/> |
   
## <a name="remarks"></a>说明

此属性中的每个 PT_LONG 值必须是唯一的属性中，并且必须设置为下表中的值之一。 如果设置此属性，还必须设置**dispidABPArrayType** ([PidLidAddressBookProviderArrayType](pidlidaddressbookproviderarraytype-canonical-property.md)) 属性。 这两个属性必须保持相互同步。 例如，如果一个**dispidABPEmailList**中的值是"0x00000000"，然后**dispidABPArrayType**必须具有位"0x00000001"设置。 
  
|**值**|**说明**|
|:-----|:-----|
|0x00000000  <br/> |为该联系人定义电子邮件 1。  <br/> |
|0x00000001  <br/> |为该联系人定义电子邮件 2。  <br/> |
|0x00000002  <br/> |为该联系人定义电子邮件 3。  <br/> |
|0x00000003  <br/> |商务传真定义为该联系人。  <br/> |
|0x00000004  <br/> |住宅传真定义为该联系人。  <br/> |
|0x00000005  <br/> |主要传真定义为该联系人。  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
[[MS OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)
  
> 指定的属性和操作所允许的联系人和个人通讯组列表。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

