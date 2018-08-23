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
ms.openlocfilehash: d5b9fb9bf8c84433ee5000cc8832c2f09bfc5fe3
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22590622"
---
# <a name="idistlist--imapicontainer"></a>IDistList : IMAPIContainer

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
提供对通讯组列表，在地址可修改访问簿容器。 **IDistList**可以创建、 复制和删除通讯组列表，除了执行名称解析。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|由公开：  <br/> |通讯组列表对象  <br/> |
|通过实现：  <br/> |通讯簿提供程序  <br/> |
|调用：  <br/> |客户端应用程序  <br/> |
|接口标识符：  <br/> |IID_IDistList  <br/> |
|指针类型：  <br/> |LPDISTLIST  <br/> |
|事务模型：  <br/> |事务处理  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

此接口不具有任何唯一的方法。
  
|**必需属性**|**Access**|
|:-----|:-----|
|**PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))  <br/> |读/写  <br/> |
|**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))  <br/> |读/写  <br/> |
|**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))  <br/> |只读  <br/> |
|**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))  <br/> |只读  <br/> |
|**PR_RECORD_KEY**([PidTagRecordKey](pidtagrecordkey-canonical-property.md))  <br/> |只读  <br/> |
   
## <a name="remarks"></a>注解

**IDistList**接口继承[IMAPIContainer](imapicontainerimapiprop.md) ，并包括作为通讯簿容器相同的方法。 因此，因为**IDistList**接口的方法是那些[IABContainer](iabcontainerimapicontainer.md)接口的完全相同，它们不会复制此处。 
  
通讯组列表或实现**IDistList**对象的消息的用户对象或单个收件人集合。 通讯组列表可以包含所有邮件用户对象，或某些消息的用户和一些通讯组列表。 
  
通常有两种类型的通讯组列表：
  
- 扩展基础消息系统的通讯组列表。 此类型的列表具有地址， **PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))，并且视为相同好像它是单独的收件人。 
    
- 本地容器中存在的且由客户端应用程序扩展的通讯组列表。
    
可选的通讯组列表属性包括：
  
- **操作**([PidTagLastModificationTime](pidtaglastmodificationtime-canonical-property.md))
    
- **PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) 
    
- **PR_DETAILS_TABLE**([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 
    
注意**PR_ADDRTYPE**是必需的而不是**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))。 这是因为通讯组列表的电子邮件地址不仍可以接收邮件，但必须扩展其成员列表。 如果**PR_ADDRTYPE**属性设置为 MAPIPDL，MAPI 执行扩展。 **PR_ADDRTYPE**是 MAPIPDL 之外的一个值，则传输提供程序执行扩展。 
  
有关如何使用**IDistList**方法的其他信息，请参阅**IABContainer**的并行方法的引用条目。
  
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

