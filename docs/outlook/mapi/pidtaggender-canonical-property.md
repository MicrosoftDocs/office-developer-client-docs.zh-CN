---
title: PidTagGender 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagGender
api_type:
- HeaderDef
ms.assetid: a79a139a-6813-49f6-b622-bb66d62c4462
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: b2ac7aa4fca8583fc59d727c55433108bee62dee
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777677"
---
# <a name="pidtaggender-canonical-property"></a>PidTagGender 规范属性

  
  
**适用于**： Outlook 
  
包含消息的用户的性别。
  
|||
|:-----|:-----|
|关联的属性：  <br/> |PR_GENDER  <br/> |
|标识符:  <br/> |0x3A4D  <br/> |
|数据类型：  <br/> |PT_I2  <br/> |
|区域：  <br/> |MAPI 邮件用户  <br/> |
   
## <a name="remarks"></a>备注

此属性提供标识和访问有关消息的用户信息并且其内容。 按消息的用户和邮件用户的组织定义的内容。 
  
此属性的可能值是性别枚举中定义的。 排列，如下所示：
  
|**性别枚举**|**值**|**说明**|
|:-----|:-----|:-----|
|genderUnspecified  <br/> |0x0000  <br/> |未指定联系人的性别。  <br/> |
|genderFemale  <br/> |0x0001  <br/> |联系人正在女。  <br/> |
|genderMale  <br/> |0x0002  <br/> |联系人正在男性。  <br/> |
   
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
  
[映射到 MAPI 名称的规范属性名称](mapping-canonical-property-names-to-mapi-names.md)
  
[MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

