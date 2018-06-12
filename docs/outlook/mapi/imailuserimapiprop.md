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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 0c70d16d294426d30f3ac5f00b6bc46992386a86
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775316"
---
# <a name="imailuser--imapiprop"></a>IMailUser: IMAPIProp

  
  
**适用于**： Outlook 
  
提供了许多属性与邮件用户关联的访问权限。 **IMailUser**接口实现消息用户对象。 继承自**IMailUser** [IMAPIProp: IUnknown](imapipropiunknown.md)接口，并具有其自己的方法都不唯一。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|由公开：  <br/> |消息的用户对象  <br/> |
|通过实现：  <br/> |通讯簿提供程序  <br/> |
|调用：  <br/> |客户端应用程序  <br/> |
|接口标识符：  <br/> |IID_IMailUser  <br/> |
|指针类型：  <br/> |LPMAILUSER  <br/> |
|事务模型：  <br/> |事务处理  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

此接口不具有任何唯一的方法。
  
|**必需的属性**|**访问**|
|:-----|:-----|
|**PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))  <br/> |读/写  <br/> |
|**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))  <br/> |读/写  <br/> |
|**PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))  <br/> |只读  <br/> |
|**PR_EMAIL_ADDRESS**([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))  <br/> |读/写  <br/> |
|**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))  <br/> |只读  <br/> |
|**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))  <br/> |只读  <br/> |
|**PR_RECORD_KEY**([PidTagRecordKey](pidtagrecordkey-canonical-property.md))  <br/> |只读  <br/> |
|**PR_SEARCH_KEY**([PidTagSearchKey](pidtagsearchkey-canonical-property.md))  <br/> |只读  <br/> |
   
## <a name="remarks"></a>备注

必需的属性的第五个称为基址属性的收件人：
  
- **PR_ADDRTYPE**
    
- **PR_DISPLAY_NAME**
    
- **PR_EMAIL_ADDRESS**
    
- **PR_ENTRYID**
    
- **PR_SEARCH_KEY**
    
因为相似属性的许多其他组建立在此基本组，这些属性被视为特殊。 其他组用于描述的收件人的各种角色，如一条消息的原始或委派发件人。 有关这些属性以及如何使用它们的详细信息，请参阅[MAPI 地址类型](mapi-address-types.md)。
  
消息用户可以通过支持**PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性中显示其属性的集合。 **PR_DETAILS_TABLE**是一个显示表，描述布局的详细信息对话框或选项卡式的属性页，显示收件人的属性信息。 客户端呼叫[IAddrBook::Details](iaddrbook-details.md)方法时，MAPI 创建详细信息对话框。 
  
消息用户对象可以具有与其相关的其他可选属性。 MAPI 定义许多属性提供有关邮件用户的其他寻址信息。 所有这些属性是字符串。 以下列表显示了多种常用的属性：
  
- **PR_ACCOUNT**([PidTagAccount](pidtagaccount-canonical-property.md)) 
    
- **PR_ASSISTANT**([PidTagAssistant](pidtagassistant-canonical-property.md)) 
    
- **PR_BUSINESS_TELEPHONE_NUMBER**([PidTagBusinessTelephoneNumber](pidtagbusinesstelephonenumber-canonical-property.md)) 
    
- **PR_GIVEN_NAME**([PidTagGivenName](pidtaggivenname-canonical-property.md)) 
    
- **PR_GOVERNMENT_ID_NUMBER**([PidTagGovernmentIdNumber](pidtaggovernmentidnumber-canonical-property.md)) 
    
- **PR_LOCALITY**([PidTagLocality](pidtaglocality-canonical-property.md)) 
    
- **PR_POSTAL_ADDRESS**([PidTagPostalAddress](pidtagpostaladdress-canonical-property.md)) 
    
属性的完整列表，请参阅[到 MAPI 名称映射规范属性名称](mapping-canonical-property-names-to-mapi-names.md)。
  
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

