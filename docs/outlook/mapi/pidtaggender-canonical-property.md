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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b8ce3898ac021bc6eec2af6220889d71ff5a18dc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316154"
---
# <a name="pidtaggender-canonical-property"></a>PidTagGender 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含邮件用户的性别。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_GENDER  <br/> |
|标识符:  <br/> |0x3A4D  <br/> |
|数据类型：  <br/> |PT_I2  <br/> |
|区域：  <br/> |MAPI 邮件用户  <br/> |
   
## <a name="remarks"></a>备注

此属性提供有关消息传递用户和内容的标识和访问信息。 内容由邮件用户和邮件用户的组织定义。 
  
此属性的可能值在性别枚举中定义。 它们列出如下：
  
|**性别枚举**|**值**|**说明**|
|:-----|:-----|:-----|
|genderUnspecified  <br/> |0x0000  <br/> |未指定联系人的性别。  <br/> |
|genderFemale  <br/> |0x0001  <br/> |联系人是男性。  <br/> |
|genderMale  <br/> |0x0002  <br/> |联系人是男性。  <br/> |
   
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

