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
ms.openlocfilehash: 68396f210aab465da9cec4a74a3c24cc4e8578a5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348438"
---
# <a name="pidlidaddressbookproviderarraytype-canonical-property"></a>PidLidAddressBookProviderArrayType 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定联系人电子地址的状态并代表一组位标志。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidABPArrayType  <br/> |
|属性集:  <br/> |PSETID_Address  <br/> |
|长 ID (盖子):  <br/> |0x00008029  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |Contact  <br/> |
   
## <a name="remarks"></a>注解

**dispidABPArrayType**属性的值必须是指定 contact 对象的状态的标志的组合。 下表中指定了各个标志。 如果设置了此属性, 则还必须设置**dispidABPEmailList** ([PidLidAddressBookProviderEmailList](pidlidaddressbookprovideremaillist-canonical-property.md)) 属性。 这两个属性必须彼此保持同步。 例如, 如果**dispidABPArrayType**具有位 "0x00000001 set", 则**dispidABPEmailList**的值之一必须为 "0x00000000"。 
  
|**位**|**Description**|
|:-----|:-----|
|0x00000001  <br/> |为联系人定义了 "Email1"。  <br/> |
|0x00000002  <br/> |为联系人定义了 "Email2"。  <br/> |
|0x00000004  <br/> |为联系人定义了 "Email3"。  <br/> |
|0x00000008  <br/> |为联系人定义商务传真。  <br/> |
|0x00000010  <br/> |住宅传真是为联系人定义的。  <br/> |
|0x00000020  <br/> |为联系人定义了主要传真。  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)
  
> 指定允许用于联系人和个人通讯组列表的属性和操作。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

