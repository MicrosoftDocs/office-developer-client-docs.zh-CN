---
title: PidTagContactAddressBookMultipleAddressFlag 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagContactAddressBookMultipleAddressFlag
api_type:
- HeaderDef
ms.assetid: aefc34c5-1beb-44cf-a455-90f466e157ce
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6fabb03d552f195c200b0ecbd8fd69f470c0e1fd
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431566"
---
# <a name="pidtagcontactaddressbookmultipleaddressflag-canonical-property"></a>PidTagContactAddressBookMultipleAddressFlag 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一个标记，当提供程序支持每个联系人项目的多个电子邮件地址时，该标志为 TRUE。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_CONTAB_MULTI_ADDR_FLAG  <br/> |
|标识符:  <br/> |0x6614  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |联系人通讯簿  <br/> |
   
## <a name="remarks"></a>备注

如果此属性为 TRUE，则提供程序不允许没有电子邮件地址的联系人。 如果为 FALSE，则提供程序会显示所有联系人，无论他们是否具有主电子邮件地址。 将仅接收主电子邮件地址。 这是联系人通讯簿容器上的属性，以及联系人通讯簿容器表中的列。
  
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

