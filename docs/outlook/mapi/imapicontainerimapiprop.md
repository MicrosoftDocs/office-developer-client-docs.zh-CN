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
ms.openlocfilehash: e24f5ebd73a4652876282099f1460762c150b94d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775324"
---
# <a name="imapicontainer--imapiprop"></a>IMAPIContainer : IMAPIProp

  
  
**适用于**： Outlook 
  
管理高级操作，如通讯簿、 通讯组列表和文件夹的容器对象。 [IMAPIFolder: IMAPIContainer](imapifolderimapicontainer.md)， [IABContainer: IMAPIContainer](iabcontainerimapicontainer.md)，和[IDistList: IMAPIContainer](idistlistimapicontainer.md)接口派生**IMAPIContainer**。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|由公开：  <br/> |文件夹、 通讯簿容器和通讯组列表对象  <br/> |
|通过实现：  <br/> |消息存储、 通讯簿和远程传输提供程序  <br/> |
|调用：  <br/> |客户端应用程序  <br/> |
|接口标识符：  <br/> |IID_IMAPIContainer  <br/> |
|指针类型：  <br/> |LPMAPICONTAINER  <br/> |
|事务模型：  <br/> |从不实现抽象类  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[GetContentsTable](imapicontainer-getcontentstable.md) <br/> |返回到容器的内容表的指针。  <br/> |
|[通讯](imapicontainer-gethierarchytable.md) <br/> |返回到容器的层次结构表的指针。  <br/> |
|[OpenEntry](imapicontainer-openentry.md) <br/> |在该容器，返回进一步访问的接口指针中打开一个对象。  <br/> |
|[SetSearchCriteria](imapicontainer-setsearchcriteria.md) <br/> |建立容器的搜索条件。  <br/> |
|[GetSearchCriteria](imapicontainer-getsearchcriteria.md) <br/> |获取容器的搜索条件。  <br/> |
   
|**必需属性**|**Access**|
|:-----|:-----|
|**PR_CONTAINER_HIERARCHY**([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md))  <br/> |只读  <br/> |
|**PR_CONTAINER_CONTENTS**([PidTagContainerContents](pidtagcontainercontents-canonical-property.md))  <br/> |只读  <br/> |
|**PR_CONTAINER_FLAGS**([PidTagContainerFlags](pidtagcontainerflags-canonical-property.md))  <br/> |读/写  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

