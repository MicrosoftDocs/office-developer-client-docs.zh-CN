---
title: PidTagContactAddressBookMultipleAddressFlags 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagContactAddressBookMultipleAddressFlags
api_type:
- HeaderDef
ms.assetid: ed3bc585-13f6-46a5-9e71-9c8513ddfc0a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ecd795490d953f1aa237dfbd77585ba79c8b3234
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429248"
---
# <a name="pidtagcontactaddressbookmultipleaddressflags-canonical-property"></a>PidTagContactAddressBookMultipleAddressFlags 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含指示提供程序是否支持每个联系人项目的多个电子邮件地址的标志。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_CONTAB_MULTI_ADDR_FLAGS  <br/> |
|标识符:  <br/> |0x6625  <br/> |
|数据类型：  <br/> |PT_MV_LONG  <br/> |
|区域：  <br/> |联系人通讯簿  <br/> |
   
## <a name="remarks"></a>备注

如果此属性中的标志为 TRUE，则提供程序不包括没有电子邮件地址的联系人。 将仅接收主电子邮件地址。 这是联系人通讯簿配置文件部分的属性。
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为关联属性列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

