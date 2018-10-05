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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25397189"
---
# <a name="pidlidfileunderid-canonical-property"></a>PidLidFileUnderId 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定如何生成和其他联系人命名属性更改时，重新计算**dispidFileUnder** ([PidLidFileUnder](pidlidfileunder-canonical-property.md)) 属性的值。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidFileUnderId  <br/> |
|属性进行设置：  <br/> |PSETID_Address  <br/> |
|长 ID （盖）：  <br/> |0x00008006  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |联系人  <br/> |
   
## <a name="remarks"></a>说明

如果此属性缺失或设置为不具体的下表中或在[[MS OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)的值，该应用程序可以选择自己的逻辑重新计算的其他联系人姓名属性更改为**dispidFileUnder**值。 
  
在下面的表中，表示法<PropertyName>用于指定"的值的属性名称"。 例如，如果**PR_SURNAME** ([PidTagSurname](pidtagsurname-canonical-property.md)) 属性的值是"Smith"，并且**PR_GIVEN_NAME** ([PidTagGivenName](pidtaggivenname-canonical-property.md)) 属性的值为"Ben"，然后"<PidTagGivenName> <PidTagSurname>"指定"Ben Smith"的字符串。 在表中，"\r"指定回车符，"\n"指定换行字符，并且<space>表示空格字符。
  
|****DispidFileUnderId**属性的值**|****DispidFileUnder**属性的说明**|
|:-----|:-----|
|0x00000000  <br/> |空 PT_UNICODE。  <br/> |
|0x00003001  <br/> |"\<PidTagDisplayName\>"  <br/> |
|0x00003A06  <br/> |"\<PidTagGivenName\>"  <br/> |
|0x00003A11  <br/> |"\<PidTagSurname\>"  <br/> |
|0x00003A16  <br/> |"\<PidTagCompanyName\>"  <br/> |
|0x00008017  <br/> |"\<PidTagSurname\>，\<空间\>\<PidTagGivenName\>\<空间\>\<PidTagMiddleName\>"  <br/> |
|0x00008018  <br/> |"\<PidTagCompanyName\>\r\n\<PidTagSurname\>，\<空间\>\<PidTagGivenName\>\<空间\>\<PidTagMiddleName\>"  <br/> |
|0x00008019  <br/> |"\<PidTagSurname\>，\<空间\>\<PidTagGivenName\>\<空间\>\<PidTagMiddleName\>\r\n\<PidTagCompanyName\>"  <br/> |
|0x00008030  <br/> |"\<PidTagSurname\>\<PidTagGivenName\>\<空间\>\<PidTagMiddleName\>"  <br/> |
|0x00008031  <br/> |"\<PidTagSurname\>\<空间\>\<PidTagGivenName\>\<空间\>\<PidTagMiddleName\>"  <br/> |
|0x00008032  <br/> |"\<PidTagCompanyName\>\r\n\<PidTagSurname\>\<PidTagGivenName\>\<空间\>\<PidTagMiddleName\>"  <br/> |
|0x00008033  <br/> |"\<PidTagCompanyName\>\r\n\<PidTagSurname\>\<空间\>\<PidTagGivenName\>\<空间\>\<PidTagMiddleName\>"  <br/> |
|0x00008034  <br/> |"\<PidTagSurname\>\<PidTagGivenName\>\<空间\>\<PidTagMiddleName\>\r\n\<PidTagCompanyName\>"  <br/> |
|0x00008035  <br/> |"\<PidTagSurname\>\<空间\>\<PidTagGivenName\>\<空间\>\<PidTagMiddleName\>\r\n\<PidTagCompanyName\>"  <br/> |
|0x00008036  <br/> |"\<PidTagSurname\>\<空间\>\<PidTagGivenName\>\<空间\>\<PidTagMiddleName\>\<空间\>\<PidTagGeneration\>"  <br/> |
|0x00008037  <br/> |"\<PidTagGivenName\>\<空间\>\<PidTagMiddleName\>\<空间\>\<PidTagSurname\>\<空间\>\<PidTagGeneration\>"  <br/> |
|0x00008038  <br/> |"\<PidTagSurname\>\<PidTagGivenName\>\<空间\>\<PidTagMiddleName\>\<空间\>\<PidTagGeneration\>"  <br/> |
|0xfffffffd  <br/> |指定，显示该联系人时, 应用程序应尝试使用**dispidFileUnder**和其他联系人属性的当前值的"最佳匹配"查找**dispidFileUnderId**此表中，以前的值之一。  <br/> |
|0xfffffffe  <br/> |指定时显示该联系人，应用程序应为**dispidFileUnderId**选择适当的默认值 （根据语言区域设置） 并更新**dispidFileUnder**匹配选项。  <br/> |
|0xffffffff  <br/> |**dispidFileUnder**为用户提供 PT_UNICODE，并另一个联系人姓名属性更改时不应被更改。  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
[[MS OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)
  
> 指定的属性和操作所允许的联系人和个人通讯组列表。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

