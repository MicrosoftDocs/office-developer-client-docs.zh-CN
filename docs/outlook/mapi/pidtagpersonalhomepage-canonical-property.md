---
title: PidTagPersonalHomePage 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagPersonalHomePage
api_type:
- COM
ms.assetid: 1ce4cb8b-b1f7-420a-b0b2-322c70e4b0f3
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1cc8471f9a3125ce89d5baefac6058e368e601d8
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22570406"
---
# <a name="pidtagpersonalhomepage-canonical-property"></a>PidTagPersonalHomePage 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含用户的个人主页的 URL。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_PERSONAL_HOME_PAGE，PR_PERSONAL_HOME_PAGE_A，PR_PERSONAL_HOME_PAGE_W  <br/> |
|标识符：  <br/> |0x3A50  <br/> |
|数据类型：  <br/> |PT_STRING8 PT_UNICODE  <br/> |
|区域：  <br/> |MAPI 邮件用户  <br/> |
   
## <a name="remarks"></a>注解

由用户或用户的组织定义这些属性。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)
  
> 指定的属性和操作所允许的联系人和个人通讯组列表。
    
[[MS OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)
  
> 指定的属性和用户、 联系人、 组和资源的操作列表。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

