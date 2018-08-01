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
ms.openlocfilehash: 6b344986989a47c4f1159fcf50c1d067ae716e98
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776974"
---
# <a name="pidlidpostaladdressid-canonical-property"></a>PidLidPostalAddressId 规范属性

  
  
**适用于**： Outlook 
  
指定联系人的通讯地址的物理地址。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidPostalAddressId  <br/> |
|属性进行设置：  <br/> |PSETID_Address  <br/> |
|长 ID （盖）：  <br/> |0x00008022  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |联系人  <br/> |
   
## <a name="remarks"></a>说明

如果存在此参数，此属性必须具有下表中或在[[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)中指定的值之一。 如果不设置，应用程序应假定的值是"0x00000000"。
  
|**值**|**说明**|
|:-----|:-----|
|0x00000000  <br/> |选择没有地址作为通讯地址。 **PR_STREET_ADDRESS**([PidTagStreetAddress](pidtagstreetaddress-canonical-property.md))， **PR_LOCALITY** ([PidTagLocality](pidtaglocality-canonical-property.md))、 **PR_STATE_OR_PROVINCE** ([PidTagStateOrProvince](pidtagstateorprovince-canonical-property.md))、 **PR_POSTAL_CODE** ([PidTagPostalCode](pidtagpostalcode-canonical-property.md))、 **PR_COUNTRY** ([PidTagCountry](pidtagcountry-canonical-property.md))， **dispidAddressCountryCode** ([PidLidAddressCountryCode](pidlidaddresscountrycode-canonical-property.md)) 和**PR_POSTAL_ADDRESS** ([PidTagPostalAddress](pidtagpostaladdress-canonical-property.md)) 都必须不设置。  <br/> |
|0x00000001  <br/> |住宅地址为通讯地址。 **PR_STREET_ADDRESS**、 **PR_LOCALITY**、 **PR_STATE_OR_PROVINCE**、 **PR_POSTAL_CODE**、 **PR_POST_OFFICE_BOX** ([PidTagPostOfficeBox](pidtagpostofficebox-canonical-property.md))、 **PR_COUNTRY**、 **dispidAddressCountryCode 值**，并且必须等于**PR_HOME_ADDRESS_STREET** ([PidTagHomeAddressStreet](pidtaghomeaddressstreet-canonical-property.md))， **PR_HOME_ADDRESS_CITY** ([PidTagHomeAddressCity](pidtaghomeaddresscity-canonical-property.md))， **PR_HOME_ 值**PR_POSTAL_ADDRESS**属性ADDRESS_STATE_OR_PROVINCE** ([PidTagHomeAddressStateOrProvince](pidtaghomeaddressstateorprovince-canonical-property.md))， **PR_HOME_ADDRESS_POSTAL_CODE** ([PidTagHomeAddressPostalCode](pidtaghomeaddresspostalcode-canonical-property.md))、 **PR_HOME_ADDRESS_POST_OFFICE_BOX** ([PidTagHomeAddressPostOfficeBox](pidtaghomeaddresspostofficebox-canonical-property.md))， **PR_HOME_ADDRESS_COUNTRY** ([PidTagHomeAddressCountry](pidtaghomeaddresscountry-canonical-property.md))、 **dispidHomeAddressCountryCode** ([PidLidHomeAddressCountryCode](pidlidhomeaddresscountrycode-canonical-property.md)) 和**dispidHomeAddress** （[PidLidHomeAddress](pidlidhomeaddress-canonical-property.md))属性，分别。  <br/> |
|0x00000002  <br/> |工作地址为通讯地址。 **PR_STREET_ADDRESS**、 **PR_LOCALITY**、 **PR_STATE_OR_PROVINCE**、 **PR_POSTAL_CODE**、 **PR_POST_OFFICE_BOX**、 **PR_COUNTRY**、 **dispidAddressCountryCode**和**PR_POSTAL_ADDRESS 的值**属性必须等于**dispidWorkAddressStreet** ([PidLidWorkAddressStreet](pidlidworkaddressstreet-canonical-property.md))， **dispidWorkAddressCity** ([PidLidWorkAddressCity](pidlidworkaddresscity-canonical-property.md))， **dispidWorkAddressState** ([的值PidLidWorkAddressState](pidlidworkaddressstate-canonical-property.md))， **dispidWorkAddressPostalCode** ([PidLidWorkAddressPostalCode](pidlidworkaddresspostalcode-canonical-property.md))， **dispidWorkAddressPostOfficeBox** ([PidLidWorkAddressPostOfficeBox](pidlidworkaddresspostofficebox-canonical-property.md))， **dispidWorkAddressCountry**([PidLidWorkAddressCountry](pidlidworkaddresscountry-canonical-property.md))， **dispidWorkAddressCountryCode** ([PidLidWorkAddressCountryCode](pidlidworkaddresscountrycode-canonical-property.md)) 和**dispidWorkAddress** ([PidLidWorkAddress](pidlidworkaddress-canonical-property.md)) 属性，分别。  <br/> |
|0x00000003  <br/> |其他地址为通讯地址。 值的**PR_STREET_ADDRESS**， **PR_LOCALITY**、 **PR_STATE_OR_PROVINCE**、 **PR_POSTAL_CODE**、 **PR_POST_OFFICE_BOX**、 **PR_COUNTRY**、 **dispidAddressCountryCode**和**PR_POSTAL_ADDRESS**属性必须等于**PR_OTHER_ADDRESS_STREET** ([PidTagOtherAddressStreet](pidtagotheraddressstreet-canonical-property.md))， **PR_OTHER_ADDRESS_CITY** ([PidTagOtherAddressCity](pidtagotheraddresscity-canonical-property.md))， **PR_OTHER_ADDRESS_STATE_OR_PROVINCE** (的值[PidTagOtherAddressStateOrProvince](pidtagotheraddressstateorprovince-canonical-property.md))， **PR_OTHER_ADDRESS_POSTAL_CODE** ([PidTagOtherAddressPostalCode](pidtagotheraddresspostalcode-canonical-property.md))、 **PR_OTHER_ADDRESS_POST_OFFICE_BOX** ([PidTagOtherAddressPostOfficeBox](pidtagotheraddresspostofficebox-canonical-property.md))、 **dispidOtherAddressCountryCode** ([PidLidOtherAddressCountryCode](pidlidotheraddresscountrycode-canonical-property.md)) 和**dispidOtherAddress** ([PidLidOtherAddress](pidlidotheraddress-canonical-property.md)) 属性，分别。  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
[[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)
  
> 指定的属性和操作所允许的联系人和个人通讯组列表。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

