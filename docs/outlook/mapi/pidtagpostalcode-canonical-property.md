---
title: PidTagPostalCode 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagPostalCode
api_type:
- COM
ms.assetid: dd8e04b3-8959-4df4-ba2c-f6371180929b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f2c4efc8f8c04229901f03fd01381d13127575a3
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589012"
---
# <a name="pidtagpostalcode-canonical-property"></a>PidTagPostalCode 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含收信人的邮政地址的邮政编码。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_POSTAL_CODE、 PR_POSTAL_CODE_A、 PR_POSTAL_CODE_W、 PR_BUSINESS_ADDRESS_POSTAL_CODE、 PR_BUSINESS_ADDRESS_POSTAL_CODE_A、 PR_BUSINESS_ADDRESS_POSTAL_CODE_W  <br/> |
|标识符：  <br/> |0x3A2A  <br/> |
|数据类型：  <br/> |PT_UNICODE PT_STRING8  <br/> |
|区域：  <br/> |MAPI 邮件用户  <br/> |
   
## <a name="remarks"></a>注解

这些属性提供标识和访问收件人的信息。 它们是按收件人和组织定义的。 
  
特定于收件人的国家/地区的邮政编码。 在美国，此属性包含邮政编码。
  
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

