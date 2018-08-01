---
title: PidTagOtherTelephoneNumber 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOtherTelephoneNumber
api_type:
- COM
ms.assetid: 60b11733-20c2-4fe9-8406-c3103b2852ba
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c3af4e5afa272233cb435b2f856c0aadb42ed16f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778013"
---
# <a name="pidtagothertelephonenumber-canonical-property"></a>PidTagOtherTelephoneNumber 规范属性

  
  
**适用于**： Outlook 
  
包含的收件人的备用电话号码。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_OTHER_TELEPHONE_NUMBER，PR_OTHER_TELEPHONE_NUMBER_A，PR_OTHER_TELEPHONE_NUMBER_W  <br/> |
|标识符：  <br/> |0x3A1F  <br/> |
|数据类型：  <br/> |PT_UNICODE PT_STRING8  <br/> |
|区域：  <br/> |Address  <br/> |
   
## <a name="remarks"></a>说明

这些属性提供标识和访问收件人的信息。 它们是按收件人和组织定义的。 
  
这些属性用于在收件人的位置的业务，主页或 office 以外的其他电话号码。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)
  
> 指定的属性和操作所允许的地址簿模板。
    
[[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)
  
> 指定的属性和操作所允许的联系人和个人通讯组列表。
    
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

