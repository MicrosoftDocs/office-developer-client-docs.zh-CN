---
title: IMailUser IMAPIProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMailUser
api_type:
- COM
ms.assetid: 74c25870-62d9-484a-9a99-4dc35c52479e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a0e109fe95120483e700bab5b82f6d7cb75e2e28
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436592"
---
# <a name="imailuser--imapiprop"></a>IMailUser : IMAPIProp

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供对与邮件用户关联的许多属性的访问权限。 **IMailUser**接口由邮件用户对象实现。 **IMailUser**继承自[IMAPIProp: IUnknown](imapipropiunknown.md)接口, 并且没有其自己的唯一方法。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|公开者:  <br/> |邮件用户对象  <br/> |
|实现者：  <br/> |通讯簿提供程序  <br/> |
|调用者：  <br/> |客户端应用程序  <br/> |
|接口标识符:  <br/> |IID_IMailUser  <br/> |
|指针类型:  <br/> |LPMAILUSER  <br/> |
|事务模型:  <br/> |事务  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

此接口没有任何唯一的方法。
  
|**必需属性**|**访问**|
|:-----|:-----|
|**PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))  <br/> |读/写  <br/> |
|**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))  <br/> |读/写  <br/> |
|**PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))  <br/> |只读  <br/> |
|**PR_EMAIL_ADDRESS**([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))  <br/> |读/写  <br/> |
|**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))  <br/> |只读  <br/> |
|**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))  <br/> |只读  <br/> |
|**PR_RECORD_KEY**([PidTagRecordKey](pidtagrecordkey-canonical-property.md))  <br/> |只读  <br/> |
|**PR_SEARCH_KEY**([PidTagSearchKey](pidtagsearchkey-canonical-property.md))  <br/> |只读  <br/> |
   
## <a name="remarks"></a>说明

5个必需属性称为收件人的基本地址属性:
  
- **PR_ADDRTYPE**
    
- **PR_DISPLAY_NAME**
    
- **PR_EMAIL_ADDRESS**
    
- **PR_ENTRYID**
    
- **PR_SEARCH_KEY**
    
这些属性被视为特殊属性, 因为在此基础组上建立了许多其他类似属性的组。 其他组用于描述不同角色中的收件人, 如邮件的原始发件人或委派发件人。 有关这些属性以及如何使用它们的详细信息, 请参阅[MAPI 地址类型](mapi-address-types.md)。
  
邮件传递用户可以通过支持**PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性来显示其属性的集合。 **PR_DETAILS_TABLE**是一个显示表, 该表格描述了显示收件人属性信息的详细信息对话框或选项卡式属性页的布局。 当客户端调用 IAddrBook 时, MAPI 会创建详细信息对话框[::D etails](iaddrbook-details.md)方法。 
  
邮件传递用户对象可以具有与之关联的其他可选属性。 MAPI 定义了许多可提供有关邮件用户的其他寻址信息的属性。 所有这些属性都是字符串。 下面的列表显示了更为常用的属性:
  
- **PR_ACCOUNT**([PidTagAccount](pidtagaccount-canonical-property.md)) 
    
- **PR_ASSISTANT**([PidTagAssistant](pidtagassistant-canonical-property.md)) 
    
- **PR_BUSINESS_TELEPHONE_NUMBER**([PidTagBusinessTelephoneNumber](pidtagbusinesstelephonenumber-canonical-property.md)) 
    
- **PR_GIVEN_NAME**([PidTagGivenName](pidtaggivenname-canonical-property.md)) 
    
- **PR_GOVERNMENT_ID_NUMBER**([PidTagGovernmentIdNumber](pidtaggovernmentidnumber-canonical-property.md)) 
    
- **PR_LOCALITY**([PidTagLocality](pidtaglocality-canonical-property.md)) 
    
- **PR_POSTAL_ADDRESS**([PidTagPostalAddress](pidtagpostaladdress-canonical-property.md)) 
    
有关属性的完整列表, 请参阅[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)。
  
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

