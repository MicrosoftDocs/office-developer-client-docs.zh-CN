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
ms.openlocfilehash: fb40e2c191056fe164c6a06bfdcf4b8e3d6eb92c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434436"
---
# <a name="pidtagcontactaddressbookstoresupportmask-canonical-property"></a>PidTagContactAddressBookStoreSupportMask 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含从包含 "联系人" 文件夹的存储区获取的**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagcontactaddressbookstoresupportmask-canonical-property.md)) 属性。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_CONTAB_STORE_SUPPORT_MASK  <br/> |
|标识符:  <br/> |0x6611  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |联系人通讯簿  <br/> |
   
## <a name="remarks"></a>说明

联系人通讯簿提供程序使用此属性来评估存储区支持的功能是否够用。 这是联系人通讯簿容器的属性, 以及联系人通讯簿容器表中的列。
  
## <a name="related-resources"></a>相关资源

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

