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
ms.openlocfilehash: 42f164f09dbffcc05986771aa05f7ce14eee789c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777442"
---
# <a name="pidtagcontactaddressbookmultipleaddressflag-canonical-property"></a>PidTagContactAddressBookMultipleAddressFlag 规范属性

  
  
**适用于**： Outlook 
  
包含一个提供程序支持每个联系人项目的多个电子邮件地址时为 TRUE 的标志。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_CONTAB_MULTI_ADDR_FLAG  <br/> |
|标识符：  <br/> |0x6614  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |联系人通讯簿  <br/> |
   
## <a name="remarks"></a>说明

如果此属性为 TRUE，则提供程序不允许没有电子邮件地址的联系人。 如果为 FALSE，提供程序将显示所有联系人拥有主电子邮件地址。 将有效仅的主电子邮件地址。 这是联系人通讯簿容器和联系人通讯簿容器的表中的列上的属性。
  
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

