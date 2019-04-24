---
title: PidLidPostalAddressId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidPostalAddressId
api_type:
- COM
ms.assetid: 30fdfb20-1e12-442a-bfa0-8c18c15fa5c3
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 83f3c0559a3317de3789f8c93d024f08ada3e735
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315993"
---
# <a name="pidlidpostaladdressid-canonical-property"></a>PidLidPostalAddressId 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定联系人的通讯地址的实际地址。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidPostalAddressId  <br/> |
|属性集:  <br/> |PSETID_Address  <br/> |
|长 ID (盖子):  <br/> |0x00008022  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |Contact  <br/> |
   
## <a name="remarks"></a>注解

如果存在, 则此属性必须具有下表中或[[毫秒-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)中指定的值之一。 如果未设置, 则应用程序应假定值为 "0x00000000"。
  
|**Value**|**说明**|
|:-----|:-----|
|0x00000000  <br/> |没有选择地址作为通讯地址。 **PR_STREET_ADDRESS**([PidTagStreetAddress](pidtagstreetaddress-canonical-property.md))、 **PR_LOCALITY** ([PidTagLocality](pidtaglocality-canonical-property.md))、 **PR_STATE_OR_PROVINCE** ([PidTagStateOrProvince](pidtagstateorprovince-canonical-property.md))、 **PR_POSTAL_CODE** ([PidTagPostalCode](pidtagpostalcode-canonical-property.md))、 **PR_COUNTRY** ([PidTagCountry](pidtagcountry-canonical-property.md))、 **dispidAddressCountryCode** ([PidLidAddressCountryCode](pidlidaddresscountrycode-canonical-property.md)) 和**PR_POSTAL_ADDRESS** ([PidTagPostalAddress](pidtagpostaladdress-canonical-property.md)) all 不得设置。  <br/> |
|0x00000001  <br/> |住宅地址是通讯地址。 **PR_STREET_ADDRESS**、 **PR_LOCALITY**、 **PR_STATE_OR_PROVINCE**、 **PR_POSTAL_CODE**、 **PR_POST_OFFICE_BOX** ([PidTagPostOfficeBox](pidtagpostofficebox-canonical-property.md))、 **PR_COUNTRY**、dispidAddressCountryCode 的值**** 和**PR_POSTAL_ADDRESS**属性必须等于**PR_HOME_ADDRESS_STREET** ([PidTagHomeAddressStreet](pidtaghomeaddressstreet-canonical-property.md))、 **PR_HOME_ADDRESS_CITY** ([PidTagHomeAddressCity](pidtaghomeaddresscity-canonical-property.md))、PR_HOME_ 的值**ADDRESS_STATE_OR_PROVINCE** ([PidTagHomeAddressStateOrProvince](pidtaghomeaddressstateorprovince-canonical-property.md))、 **PR_HOME_ADDRESS_POSTAL_CODE** ([PidTagHomeAddressPostalCode](pidtaghomeaddresspostalcode-canonical-property.md))、 **PR_HOME_ADDRESS_POST_OFFICE_BOX** ([PidTagHomeAddressPostOfficeBox](pidtaghomeaddresspostofficebox-canonical-property.md))、 **PR_HOME_ADDRESS_COUNTRY** ([PidTagHomeAddressCountry](pidtaghomeaddresscountry-canonical-property.md))、 **dispidHomeAddressCountryCode** ([PidLidHomeAddressCountryCode](pidlidhomeaddresscountrycode-canonical-property.md)) 和**dispidHomeAddress** ([PidLidHomeAddress](pidlidhomeaddress-canonical-property.md))属性。  <br/> |
|0x00000002  <br/> |工作地址为邮件地址。 **PR_STREET_ADDRESS**、 **PR_LOCALITY**、 **PR_STATE_OR_PROVINCE**、 **PR_POSTAL_CODE**、 **PR_POST_OFFICE_BOX**、 **PR_COUNTRY**、 **dispidAddressCountryCode**和 PR_POSTAL_ADDRESS 的值**** 属性必须等于**dispidWorkAddressStreet** ([PidLidWorkAddressStreet](pidlidworkaddressstreet-canonical-property.md))、 **dispidWorkAddressCity** ([PidLidWorkAddressCity](pidlidworkaddresscity-canonical-property.md))、 **dispidWorkAddressState**的值 ([PidLidWorkAddressState](pidlidworkaddressstate-canonical-property.md))、 **dispidWorkAddressPostalCode** ([PidLidWorkAddressPostalCode](pidlidworkaddresspostalcode-canonical-property.md))、 **dispidWorkAddressPostOfficeBox** ([PidLidWorkAddressPostOfficeBox](pidlidworkaddresspostofficebox-canonical-property.md))、 **dispidWorkAddressCountry**([PidLidWorkAddressCountry](pidlidworkaddresscountry-canonical-property.md))、 **dispidWorkAddressCountryCode** ([PidLidWorkAddressCountryCode](pidlidworkaddresscountrycode-canonical-property.md)) 和**dispidWorkAddress** ([PidLidWorkAddress](pidlidworkaddress-canonical-property.md)) 属性。  <br/> |
|0x00000003  <br/> |另一个地址是邮件地址。 、 **PR_STREET_ADDRESS**、 **PR_LOCALITY**、 **PR_STATE_OR_PROVINCE**、 **PR_POSTAL_CODE**、 **PR_POST_OFFICE_BOX**、 **PR_COUNTRY**、 **dispidAddressCountryCode**和 PR_POSTAL_ADDRESS 的值**** 属性必须等于**PR_OTHER_ADDRESS_STREET** ([PidTagOtherAddressStreet](pidtagotheraddressstreet-canonical-property.md))、 **PR_OTHER_ADDRESS_CITY** ([PidTagOtherAddressCity](pidtagotheraddresscity-canonical-property.md))、 **PR_OTHER_ADDRESS_STATE_OR_PROVINCE**的值 ([PidTagOtherAddressStateOrProvince](pidtagotheraddressstateorprovince-canonical-property.md))、 **PR_OTHER_ADDRESS_POSTAL_CODE** ([PidTagOtherAddressPostalCode](pidtagotheraddresspostalcode-canonical-property.md))、 **PR_OTHER_ADDRESS_POST_OFFICE_BOX** ([PidTagOtherAddressPostOfficeBox](pidtagotheraddresspostofficebox-canonical-property.md))、 **** 分别是 dispidOtherAddressCountryCode ([PidLidOtherAddressCountryCode](pidlidotheraddresscountrycode-canonical-property.md)) 和**dispidOtherAddress** ([PidLidOtherAddress](pidlidotheraddress-canonical-property.md)) 属性。  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)
  
> 指定允许用于联系人和个人通讯组列表的属性和操作。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

