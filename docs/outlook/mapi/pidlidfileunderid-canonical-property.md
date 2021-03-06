---
title: PidLidFileUnderId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidFileUnderId
api_type:
- COM
ms.assetid: 917431a9-fd90-4b4d-b042-886e3dbf47c0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7af30866a5fd2846327223b7a58c6de91f5fef7a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355704"
---
# <a name="pidlidfileunderid-canonical-property"></a>PidLidFileUnderId 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定当其他联系人姓名属性更改时如何生成和重新计算 **dispidFileUnder** ([PidLidFileUnder](pidlidfileunder-canonical-property.md)) 属性的值。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidFileUnderId  <br/> |
|属性集：  <br/> |PSETID_Address  <br/> |
|LONG ID (的一) ：  <br/> |0x00008006  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |联系人  <br/> |
   
## <a name="remarks"></a>备注

如果此属性缺失或设置为下表或 [[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)中未详细说明的值，应用程序可以选择自己的逻辑，以重新编译 **dispidFileUnder** 的值，因为其他联系人姓名属性会发生变化。 
  
在下表中，表示 <PropertyName> 法用于指定"PropertyName 的值"。 例如，如果 **PR_SURNAME** ([PidTagSurname](pidtagsurname-canonical-property.md)) 属性的值为"Smith"，而 **PR_GIVEN_NAME** ([PidTagGivenName](pidtaggivenname-canonical-property.md)) 属性的值为"Ben"，则" " 指定字符串 <PidTagGivenName> <PidTagSurname> "Ben Smith"。 在表中，"\r"指定回车符，"\n"指定换行符，并 <space> 代表空格字符。
  
|****dispidFileUnderId 属性的值****|****dispidFileUnder 属性** 的说明**|
|:-----|:-----|
|0x00000000  <br/> |空PT_UNICODE。  <br/> |
|0x00003001  <br/> |" \< PidTagDisplayName \> "  <br/> |
|0x00003A06  <br/> |" \< PidTagGivenName \> "  <br/> |
|0x00003A11  <br/> |" \< PidTagSurname \> "  <br/> |
|0x00003A16  <br/> |" \< PidTagCompanyName \> "  <br/> |
|0x00008017  <br/> |" \< PidTagSurname \> ， space \< \> \< PidTagGivenName space \> \< \> \< PidTagMiddleName \> "  <br/> |
|0x00008018  <br/> |" \< PidTagCompanyName \>\r\n\< PidTagSurname \> ， space \< \> \< PidTagGivenName space \> \< \> \< PidTagMiddleName \> "  <br/> |
|0x00008019  <br/> |" \< PidTagSurname \> ， space \< \> \< PidTagGivenName space \> \< \> \< PidTagMiddleName\r\n\> \< PidTagCompanyName \> "  <br/> |
|0x00008030  <br/> |" \< PidTagSurname \> \< PidTagGivenName \> \< space \> \< PidTagMiddleName \> "  <br/> |
|0x00008031  <br/> |" \< PidTagSurname \> \< space \> \< PidTagGivenName \> \< space \> \< PidTagMiddleName \> "  <br/> |
|0x00008032  <br/> |" \< PidTagCompanyName \>\r\n\< \> \< PidTagSurname PidTagGivenName \> \< space \> \< PidTagMiddleName \> "  <br/> |
|0x00008033  <br/> |" \< PidTagCompanyName \>\r\n\< \> \< PidTagSurname space \> \< PidTagGivenName \> \< space \> \< PidTagMiddleName \> "  <br/> |
|0x00008034  <br/> |" \< PidTagSurname \> \< PidTagGivenName \> \< space \> \< PidTagMiddleName \>\r\n\< PidTagCompanyName \> "  <br/> |
|0x00008035  <br/> |" \< PidTagSurname \> \< space \> \< PidTagGivenName \> \< space \> \< PidTagMiddleName\r\n\> \< PidTagCompanyName \> "  <br/> |
|0x00008036  <br/> |" \< PidTagSurname \> \< space \> \< PidTagGivenName \> \< space \> \< PidTagMiddleName space \> \< \> \< PidTagGeneration \> "  <br/> |
|0x00008037  <br/> |" \< PidTagGivenName \> \< space \> \< PidTagMiddleName \> \< space \> \< PidTagSurname space \> \< \> \< PidTagGeneration \> "  <br/> |
|0x00008038  <br/> |" \< PidTagSurname \> \< PidTagGivenName \> \< space \> \< PidTagMiddleName \> \< space \> \< PidTagGeneration \> "  <br/> |
|0xfffffffd  <br/> |指定在显示联系人时，应用程序应尝试使用 **dispidFileUnder** 的当前值和其他联系人属性查找 **dispidFileUnderId** 与此表中之前值之一的"最佳匹配"。  <br/> |
|0xfffffffe  <br/> |指定在显示联系人时，应用程序应该根据 **dispidFileUnderId** 的语言区域设置 (选择适当的默认值) ，并更新 **dispidFileUnder** 以匹配该选择。  <br/> |
|0xffffffff  <br/> |**dispidFileUnder** 是用户提供的PT_UNICODE，不应在更改其他联系人姓名属性时进行更改。  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关协议规范Exchange Server引用。
    
[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)
  
> 指定联系人和个人通讯组列表允许的属性和操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

