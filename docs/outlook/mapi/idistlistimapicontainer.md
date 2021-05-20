---
title: IDistList IMAPIContainer
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IDistList
api_type:
- COM
ms.assetid: bd8e1ddb-3027-428b-8964-81614f80282d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 463d81a6692b6071cada0ad22e7343020563e41c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431545"
---
# <a name="idistlist--imapicontainer"></a>IDistList : IMAPIContainer

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供对可修改通讯簿容器中的通讯组列表的访问。 **除了执行名称解析之外，IDistList** 还可以创建、复制和删除通讯组列表。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
|公开者：  <br/> |通讯组列表对象  <br/> |
|实现者：  <br/> |通讯簿提供程序  <br/> |
|调用者：  <br/> |客户端应用程序  <br/> |
|接口标识符：  <br/> |IID_IDistList  <br/> |
|指针类型：  <br/> |LPDISTLIST  <br/> |
|事务模型：  <br/> |Transacted  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

此接口没有任何唯一的方法。
  
|**必需属性**|**Access**|
|:-----|:-----|
|**PR_ADDRTYPE (** [PidTagAddressType](pidtagaddresstype-canonical-property.md))   <br/> |读/写  <br/> |
|**PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md))   <br/> |读/写  <br/> |
|**PR_ENTRYID (** [PidTagEntryId](pidtagentryid-canonical-property.md))   <br/> |只读  <br/> |
|**PR_OBJECT_TYPE (** [PidTagObjectType](pidtagobjecttype-canonical-property.md))   <br/> |只读  <br/> |
|**PR_RECORD_KEY (** [PidTagRecordKey)](pidtagrecordkey-canonical-property.md)  <br/> |只读  <br/> |
   
## <a name="remarks"></a>备注

**IDistList** 接口继承自 [IMAPIContainer，](imapicontainerimapiprop.md)并包含与通讯簿容器相同的方法。 因此，由于 **IDistList** 接口的方法与 [IABContainer](iabcontainerimapicontainer.md) 接口的方法相同，因此此处不会重复这些方法。 
  
实现 **IDistList** 的通讯组列表或对象是邮件用户对象或单个收件人的集合。 通讯组列表可以包含所有邮件用户对象，或某些邮件用户和一些通讯组列表。 
  
通常有两种类型的通讯组列表：
  
- 由基础邮件系统展开的通讯组列表。 此类型的列表具有一个地址PR_EMAIL_ADDRESS ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) ，并且被视为一个单独收件人。  
    
- 存在于本地容器中且由客户端应用程序展开的通讯组列表。
    
可选的通讯组列表属性包括：
  
- **PR_LAST_MODIFICATION_TIME (** [PidTagLastModificationTime](pidtaglastmodificationtime-canonical-property.md)) 
    
- **PR_DISPLAY_TYPE (** [PidTagDisplayType](pidtagdisplaytype-canonical-property.md))  
    
- **PR_DETAILS_TABLE (** [PidTagDetailsTable)](pidtagdetailstable-canonical-property.md) 
    
请注意 **，PR_ADDRTYPE** 是必需的，PR_EMAIL_ADDRESS ([PidTagEmailAddress) PidTagEmailAddress。](pidtagemailaddress-canonical-property.md)  这是因为没有电子邮件地址的通讯组列表仍可接收邮件，但必须展开其成员列表。 如果 **PR_ADDRTYPE** 属性设置为 MAPIPDL，MAPI 将执行扩展。 如果 **PR_ADDRTYPE** 值不是 MAPIPDL，则传输提供程序将执行扩展。 
  
有关如何使用 **IDistList** 方法的其他信息，请参阅 **IABContainer** 的并行方法的引用条目。
  
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

