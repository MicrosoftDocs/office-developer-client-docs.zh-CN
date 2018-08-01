---
title: PidTagContactAddressBookStoreSupportMask 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagContactAddressBookStoreSupportMask
api_type:
- HeaderDef
ms.assetid: 34f649c8-29bf-470f-9b05-31b69d069259
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5cd113c263c97ba306fcf7bf97c750e710eac922
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777448"
---
# <a name="pidtagcontactaddressbookstoresupportmask-canonical-property"></a>PidTagContactAddressBookStoreSupportMask 规范属性

  
  
**适用于**： Outlook 
  
包含从包含联系人文件夹的存储区获得的**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagcontactaddressbookstoresupportmask-canonical-property.md)) 属性。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_CONTAB_STORE_SUPPORT_MASK  <br/> |
|标识符：  <br/> |0x6611  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |联系人通讯簿  <br/> |
   
## <a name="remarks"></a>说明

联系人通讯簿提供程序使用此属性来评估适用性的存储支持的功能。 这是联系人通讯簿容器和联系人通讯簿容器的表中的列上的属性。
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含列为相关属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

