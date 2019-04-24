---
title: PidTagCountry 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagCountry
api_type:
- HeaderDef
ms.assetid: c9470496-fb37-4019-ae1b-b4f93ac55048
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 85a0421c8ce364ed75850c2b330ae0a54a5fed9a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357909"
---
# <a name="pidtagcountry-canonical-property"></a>PidTagCountry 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含收件人所在国家/地区的名称。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_COUNTRY、PR_COUNTRY_A、PR_COUNTRY_W、PR_BUSINESS_ADDRESS_COUNTRY、PR_BUSINESS_ADDRESS_COUNTRY_A、PR_BUSINESS_ADDRESS_COUNTRY_W  <br/> |
|标识符:  <br/> |0x3A26  <br/> |
|数据类型：  <br/> |PT_UNICODE、PT_STRING8  <br/> |
|区域：  <br/> |Contact  <br/> |
   
## <a name="remarks"></a>注解

这些属性是提供有关收件人的标识和访问信息的属性示例。 这些属性由收件人和收件人的组织定义。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)
  
> 指定允许用于联系人和个人通讯组列表对象的属性和操作。
    
[[毫秒-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)
  
> 指定用户、联系人、组和资源列表的属性和操作。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为替换名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

