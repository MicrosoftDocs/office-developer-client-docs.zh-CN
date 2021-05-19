---
title: IABContainer IMAPIContainer
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IABContainer
api_type:
- COM
ms.assetid: 1f5ce6e0-b79a-4da2-b014-8c00cd72912e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0905fbe2ba584aef49c50152aaf448267d477c10
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348956"
---
# <a name="iabcontainer--imapicontainer"></a>IABContainer : IMAPIContainer

**适用于**：Outlook 2013 | Outlook 2016 
  
提供对通讯簿容器的访问。 MAPI 和客户端应用程序调用 **IABContainer** 方法来执行名称解析以及创建、复制和删除收件人。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
|公开者：  <br/> |通讯簿容器对象  <br/> |
|实现者：  <br/> |通讯簿提供程序  <br/> |
|调用者：  <br/> |MAPI 和客户端应用程序  <br/> |
|接口标识符：  <br/> |IID_IABContainer  <br/> |
|指针类型：  <br/> |LPABCONT  <br/> |
|事务模型：  <br/> |Transacted  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[CreateEntry](iabcontainer-createentry.md) <br/> |创建一个新条目，该条目可以是邮件用户、通讯组列表或其他容器。  <br/> |
|[CopyEntries](iabcontainer-copyentries.md) <br/> |复制一个或多个条目，通常为邮件用户或通讯组列表。  <br/> |
|[DeleteEntries](iabcontainer-deleteentries.md) <br/> |删除一个或多个条目，通常为邮件用户、通讯组列表或其他容器。  <br/> |
|[ResolveNames](iabcontainer-resolvenames.md) <br/> |对一个或多个收件人条目执行名称解析。  <br/> |
   
|**必需属性**|**Access**|
|:-----|:-----|
|**PR_CONTAINER_FLAGS (** [PidTagContainerFlags](pidtagcontainerflags-canonical-property.md))   <br/> |读/写  <br/> |
|**PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md))   <br/> |读/写  <br/> |
|**PR_ENTRYID (** [PidTagEntryId](pidtagentryid-canonical-property.md))   <br/> |只读  <br/> |
|**PR_OBJECT_TYPE (** [PidTagObjectType](pidtagobjecttype-canonical-property.md))   <br/> |只读  <br/> |
|**PR_RECORD_KEY (** [PidTagRecordKey)](pidtagrecordkey-canonical-property.md)  <br/> |只读  <br/> |
   
|**可选属性**|**Access**|
|:-----|:-----|
|**PR_CONTAINER_CONTENTS (** [PidTagContainerContents)](pidtagcontainercontents-canonical-property.md)  <br/> |只读  <br/> |
|**PR_CONTAINER_HIERARCHY (** [PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md))   <br/> |只读  <br/> |
|**PR_DEF_CREATE_DL (** [PidTagDefCreateDl](pidtagdefcreatedl-canonical-property.md))   <br/> |只读  <br/> |
|**PR_DEF_CREATE_MAILUSER (** [PidTagDefCreateMailuser)](pidtagdefcreatemailuser-canonical-property.md)  <br/> |只读  <br/> |
|**PR_DISPLAY_TYPE (** [PidTagDisplayType](pidtagdisplaytype-canonical-property.md))   <br/> |只读  <br/> |
   
## <a name="remarks"></a>备注

**IABContainer** 接口通过 [IMAPIContainer ： IMAPIProp 和 IMAPIProp ：](imapicontainerimapiprop.md) [IUnknown](imapipropiunknown.md)接口间接继承自 IUnknown 接口。 [](https://msdn.microsoft.com/library/ms680509%28VS.85%29.aspx) 通讯簿提供程序实现 **IABContainer** 接口。 
  
通讯簿容器中可以存在任意数目的邮件用户对象、通讯组列表和其他通讯簿容器。 与任何容器一样，客户端或服务提供商可以使用通讯簿容器打开其条目之一或检索层次结构表或内容表。 通讯簿容器还提供名称解析以及添加、删除或修改条目的能力，具体取决于提供程序。
  
MAPI 定义一个称为个人通讯簿的特殊通讯簿容器 (PAB) 保存从其他容器复制的条目。 PAB 始终可修改。 用户通常使用指定其最经常通信的收件人的条目填充其 PAB。 PAB 还可以保留一次地址，并且新收件人尚不是任何通讯簿容器的一部分。
  
## <a name="see-also"></a>另请参阅

- [MAPI 接口](mapi-interfaces.md)

