---
title: PidTagTelecommunicationsDeviceForDeafTelephoneNumber 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagTelecommunicationsDeviceForDeafTelephon
api_type:
- COM
ms.assetid: 9b1bea60-1946-48ea-8312-c85fcbe944a8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8f116aade555fc3d5fa1ab63635b540826652ec3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358850"
---
# <a name="pidtagtelecommunicationsdevicefordeaftelephonenumber-canonical-property"></a>PidTagTelecommunicationsDeviceForDeafTelephoneNumber 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含消息传递用户的失聪用户电信设备 (TTYTDD) 电话号码。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_TTYTDD_PHONE_NUMBER、PR_TTYTDD_PHONE_NUMBER_A、PR_TTYTDD_PHONE_NUMBER_W  <br/> |
|标识符:  <br/> |0x3A4B  <br/> |
|数据类型：  <br/> |PT_STRING8、PT_UNICODE  <br/> |
|区域：  <br/> |MAPI 邮件用户  <br/> |
   
## <a name="remarks"></a>备注

这些属性提供有关邮件用户的标识和访问信息。 内容由邮件用户和邮件用户的组织定义。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)
  
> 指定联系人和个人通讯组列表允许的属性和操作。
    
[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)
  
> 指定用户、联系人、组和资源的列表的属性和操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

