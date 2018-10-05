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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25392184"
---
# <a name="iabcontainer--imapicontainer"></a>IABContainer : IMAPIContainer

**适用于**：Outlook 2013 | Outlook 2016 
  
提供对通讯簿容器的访问。 MAPI 和客户端应用程序调用**IABContainer**执行名称解析和创建、 复制方法，并删除收件人。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
|由公开：  <br/> |通讯簿容器对象  <br/> |
|实现者：  <br/> |通讯簿提供程序  <br/> |
|调用者：  <br/> |MAPI 和客户端应用程序  <br/> |
|接口标识符：  <br/> |IID_IABContainer  <br/> |
|指针类型：  <br/> |LPABCONT  <br/> |
|事务模型：  <br/> |事务处理  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[CreateEntry](iabcontainer-createentry.md) <br/> |创建一个新项，可以是邮件用户、 通讯组列表或其他容器。  <br/> |
|[CopyEntries](iabcontainer-copyentries.md) <br/> |复制一个或多个条目，通常消息的用户或通讯组列表。  <br/> |
|[DeleteEntries](iabcontainer-deleteentries.md) <br/> |删除一个或多个条目，通常消息的用户、 通讯组列表或其他容器。  <br/> |
|[ResolveNames](iabcontainer-resolvenames.md) <br/> |执行一个或多个收件人的条目的名称解析。  <br/> |
   
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
   
## <a name="remarks"></a>说明

**IABContainer**接口从[IUnknown](https://msdn.microsoft.com/library/ms680509%28VS.85%29.aspx)接口通过间接继承[IMAPIContainer: IMAPIProp](imapicontainerimapiprop.md)和[IMAPIProp: IUnknown](imapipropiunknown.md)接口。 通讯簿提供程序实现**IABContainer**接口。 
  
通讯簿容器中存在可以任意数量的消息的用户对象、 通讯组列表和其他通讯簿容器。 与任何容器，客户端或服务提供商可以使用通讯簿容器来打开其项之一或检索层次结构表或内容表。 通讯的簿容器还提供名称解析，取决于提供程序，可以添加、 删除或修改条目。
  
MAPI 定义名为容纳从其他容器复制的项的个人通讯簿 (PAB) 特殊通讯簿容器。 PAB 始终是修改的。 用户通常填充其 PAB 指定与他们通常通信的收件人的条目。 PAB 也可以容纳一次性地址和新的收件人尚未任何通讯簿容器的一部分。
  
## <a name="see-also"></a>另请参阅

- [MAPI 接口](mapi-interfaces.md)

