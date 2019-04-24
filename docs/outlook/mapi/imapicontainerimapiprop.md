---
title: IMAPIContainer IMAPIProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIContainer
api_type:
- COM
ms.assetid: d83fdd83-3e86-43c8-a73f-8e9e01b53371
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8be3b1857d539f81e42d2ac3e5813afa73513a16
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286718"
---
# <a name="imapicontainer--imapiprop"></a>IMAPIContainer : IMAPIProp

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
管理容器对象 (如通讯簿、通讯组列表和文件夹) 的高级操作。 [IMAPIFolder: IMAPIContainer](imapifolderimapicontainer.md)、 [IABContainer: IMAPIContainer](iabcontainerimapicontainer.md)和[IDistList: IMAPIContainer](idistlistimapicontainer.md)接口派生自**IMAPIContainer**。
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|公开者:  <br/> |文件夹、通讯簿容器和通讯组列表对象  <br/> |
|实现者：  <br/> |邮件存储、通讯簿和远程传输提供程序  <br/> |
|调用者：  <br/> |客户端应用程序  <br/> |
|接口标识符:  <br/> |IID_IMAPIContainer  <br/> |
|指针类型:  <br/> |LPMAPICONTAINER  <br/> |
|事务模型:  <br/> |抽象类, 从未实现  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[GetContentsTable](imapicontainer-getcontentstable.md) <br/> |返回指向容器的内容表的指针。  <br/> |
|[GetHierarchyTable](imapicontainer-gethierarchytable.md) <br/> |返回指向容器的层次结构表的指针。  <br/> |
|[OpenEntry](imapicontainer-openentry.md) <br/> |打开容器中的一个对象, 返回一个接口指针以供进一步访问。  <br/> |
|[SetSearchCriteria](imapicontainer-setsearchcriteria.md) <br/> |建立容器的搜索条件。  <br/> |
|[GetSearchCriteria](imapicontainer-getsearchcriteria.md) <br/> |获取容器的搜索条件。  <br/> |
   
|**必需属性**|**Access**|
|:-----|:-----|
|**PR_CONTAINER_HIERARCHY**([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md))  <br/> |只读  <br/> |
|**PR_CONTAINER_CONTENTS**([PidTagContainerContents](pidtagcontainercontents-canonical-property.md))  <br/> |只读  <br/> |
|**PR_CONTAINER_FLAGS**([PidTagContainerFlags](pidtagcontainerflags-canonical-property.md))  <br/> |读/写  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

