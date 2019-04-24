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
  
提供对通讯簿容器的访问权限。 MAPI 和客户端应用程序调用**IABContainer**方法来执行名称解析以及创建、复制和删除收件人。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|公开者:  <br/> |通讯簿容器对象  <br/> |
|实现者：  <br/> |通讯簿提供程序  <br/> |
|调用者：  <br/> |MAPI 和客户端应用程序  <br/> |
|接口标识符:  <br/> |IID_IABContainer  <br/> |
|指针类型:  <br/> |LPABCONT  <br/> |
|事务模型:  <br/> |事务  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[CreateEntry](iabcontainer-createentry.md) <br/> |创建一个新的条目, 该条目可以是邮件用户、通讯组列表或其他容器。  <br/> |
|[CopyEntries](iabcontainer-copyentries.md) <br/> |复制一个或多个条目, 通常是邮件用户或通讯组列表。  <br/> |
|[DeleteEntries](iabcontainer-deleteentries.md) <br/> |删除一个或多个条目, 通常是邮件用户、通讯组列表或其他容器。  <br/> |
|[ResolveNames](iabcontainer-resolvenames.md) <br/> |为一个或多个收件人条目执行名称解析。  <br/> |
   
|**必需属性**|**Access**|
|:-----|:-----|
|**PR_CONTAINER_FLAGS**([PidTagContainerFlags](pidtagcontainerflags-canonical-property.md))  <br/> |读/写  <br/> |
|**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))  <br/> |读/写  <br/> |
|**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))  <br/> |只读  <br/> |
|**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))  <br/> |只读  <br/> |
|**PR_RECORD_KEY**([PidTagRecordKey](pidtagrecordkey-canonical-property.md))  <br/> |只读  <br/> |
   
|**可选属性**|**Access**|
|:-----|:-----|
|**PR_CONTAINER_CONTENTS**([PidTagContainerContents](pidtagcontainercontents-canonical-property.md))  <br/> |只读  <br/> |
|**PR_CONTAINER_HIERARCHY**([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md))  <br/> |只读  <br/> |
|**PR_DEF_CREATE_DL**([PidTagDefCreateDl](pidtagdefcreatedl-canonical-property.md))  <br/> |只读  <br/> |
|**PR_DEF_CREATE_MAILUSER**([PidTagDefCreateMailuser](pidtagdefcreatemailuser-canonical-property.md))  <br/> |只读  <br/> |
|**PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))  <br/> |只读  <br/> |
   
## <a name="remarks"></a>注解

**IABContainer**接口通过[IMAPIContainer: IMAPIProp](imapicontainerimapiprop.md)和[IMAPIProp: IUnknown](imapipropiunknown.md)接口间接继承自[IUnknown](https://msdn.microsoft.com/library/ms680509%28VS.85%29.aspx)接口。 通讯簿提供程序实现**IABContainer**接口。 
  
通讯簿容器中可以存在任意数量的邮件用户对象、通讯组列表和其他通讯簿容器。 与任何容器一样, 客户端或服务提供程序可以使用通讯簿容器打开其中一个条目或检索层次结构表或内容表。 通讯簿容器还提供名称解析, 具体取决于提供程序、添加、删除或修改条目的功能。
  
MAPI 定义了一个名为 "个人通讯簿 (PAB)" 的特殊通讯簿容器, 该容器保留从其他容器复制的条目。 PAB 始终是可修改的。 用户通常用其自己的 PAB 填充其 PAB, 以指定他们最常与之通信的收件人。 PAB 也可以保留一次性地址和新的收件人, 而不是任何通讯簿容器的一部分。
  
## <a name="see-also"></a>另请参阅

- [MAPI 接口](mapi-interfaces.md)

