---
title: 编写层次结构查看器
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4c939a8c-8148-4add-b181-5a12e6d32309
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 5f6ebd20afc3b8d029fa7c632c55982862664055
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421128"
---
# <a name="writing-a-hierarchy-viewer"></a>编写层次结构查看器

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
层次结构查看器是一个用户界面组件, 用于显示文件夹和通讯簿容器层次结构表。 层次结构查看者可以显示不同级别的层次结构成员, 根据需要展开和收缩每个级别。
  
container 属性**PR_DEPTH** ([PidTagDepth](pidtagdepth-canonical-property.md)) 控制层次结构成员的显示级别。 表示顶级通讯簿容器或文件夹的条目将其**PR_DEPTH**属性设置为零。 对于连续级别中的条目, 此属性的值按顺序递增。 也就是说, 当用户选择要展开的顶级容器时, 将显示 " **PR_DEPTH** " 设置为1的所有容器。 当用户展开这些子容器之一时, 将显示 " **PR_DEPTH** " 设置为2的容器, 依此类推。 
  
层次结构查看器支持不同的深度范围。 您可以将查看器限制为仅有一个或两个级别, 如果显示范围较广的层次结构, 则可以支持多个级别。 
  
通讯簿为通讯簿中的顶级容器提供了层次结构查看器。 
  
 **访问通讯簿层次结构表**
  
1. 调用[IAddrBook:: OpenEntry](iaddrbook-openentry.md), 传递一个 null 条目标识符, 以打开通讯簿的根容器。
    
2. 调用根容器的[IMAPIContainer:: GetHierarchyTable](imapicontainer-gethierarchytable.md)方法以访问 MAPI 通讯簿的层次结构表。 
    
 **访问默认邮件存储的层次结构表**
  
1. 调用[IMAPISession:: GetMsgStoresTable](imapisession-getmsgstorestable.md)以访问邮件存储库表。 
    
2. 使用[SPropertyRestriction](spropertyrestriction.md)结构生成限制, 将表限定为**PR_DEFAULT_STORE** ([PidTagDefaultStore](pidtagdefaultstore-canonical-property.md)) 属性设置为 TRUE 的那些行。 
    
3. 调用[IMAPITable:: FindRow](imapitable-findrow.md), 并将其传递给**SPropertyRestriction**, 以定位表示默认邮件存储的行。 
    
4. 调用[IMAPISession:: OpenEntry](imapisession-openentry.md), 从邮件存储库表中的默认邮件存储行传入**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性。
    
5. 调用邮件存储区的[IMAPIProp:: GetProps](imapiprop-getprops.md)方法以检索**PR_IPM_SUBTREE_ENTRYID** ([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md)) 属性。
    
6. 调用邮件存储区的[IMsgStore:: OpenEntry](imsgstore-openentry.md)方法, 并传递**PR_IPM_SUBTREE_ENTRYID**属性, 以打开邮件存储的 IPM 子树的根文件夹。 
    
7. 调用 IPM 根文件夹的[IMAPIContainer:: GetHierarchyTable](imapicontainer-gethierarchytable.md)方法以访问其层次结构表。 
    

