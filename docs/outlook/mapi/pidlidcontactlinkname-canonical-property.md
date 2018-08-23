---
title: PidLidContactLinkName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidContactLinkName
api_type:
- COM
ms.assetid: 7b9be1cd-e81e-42f3-b391-036afa2ae1b4
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: cd29ed24f155e3d39d367d677f3760b2aa12a18d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22582376"
---
# <a name="pidlidcontactlinkname-canonical-property"></a>PidLidContactLinkName 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含**dispidContacts** ([PidLidContacts](pidlidcontacts-canonical-property.md)) 属性的元素。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidContactLinkName  <br/> |
|属性进行设置：  <br/> |PSETID_Common  <br/> |
|长 ID （盖）：  <br/> |0x00008586  <br/> |
|数据类型：  <br/> |PT_UNICODE  <br/> |
|区域：  <br/> |联系人  <br/> |
   
## <a name="remarks"></a>注解

由分号和空格分隔**dispidContactLinkName**属性中的元素 （";"）。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件的对象。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

