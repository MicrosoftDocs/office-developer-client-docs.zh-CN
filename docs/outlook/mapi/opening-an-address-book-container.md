---
title: 打开通讯簿容器
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 89383b27-618c-4ccb-9e16-f66235c98bfe
description: 上次修改时间：2011 年 11 月 8 日
ms.openlocfilehash: 97fa9f9750174c112c431c62f6171f674856fa86
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436739"
---
# <a name="opening-an-address-book-container"></a>打开通讯簿容器

**适用于**：Outlook 2013 | Outlook 2016 
  
打开 MAPI 集成通讯簿后，打开一个或多个通讯簿容器以访问其中的收件人。
  
要打开通讯簿的顶级容器，请调用具有 NULL 条目标识符的[IAddrBook：：OpenEntry。](iaddrbook-openentry.md) 
  
通讯簿容器可通过只读或读/写访问权限实现。 只读容器仅用于浏览。 可修改读/写容器，允许客户端创建新条目以及删除和修改现有条目。 PAB 容器 (个人通讯簿) 读/写容器实现。 
  
若要打开任何较低级别的容器，请调用 **OpenEntry** 并指定要打开的容器的条目标识符。 
  
## <a name="open-the-container-designated-as-the-pab"></a>打开指定为 PAB 的容器
  
1. 调用 [IAddrBook：：GetPAB](iaddrbook-getpab.md) 检索 PAB 的条目标识符。 
    
2. 将此项标识符传递到 [IAddrBook：：OpenEntry](iaddrbook-openentry.md)。
    
## <a name="open-a-container-that-is-not-the-pab"></a>打开不是 PAB 的容器
  
1. 使用 [NULL 条目标识符调用 IAddrBook：：OpenEntry](iaddrbook-openentry.md) 以打开通讯簿的根容器。 
    
2. 调用根容器的 [IMAPIContainer：：GetHierarchyTable](imapicontainer-gethierarchytable.md) 方法以检索其层次结构表 — 通讯簿中所有顶级容器的列表。 
    
3. 如果要打开的容器是特定类型：
    
   - 为属性标记创建具有 **PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) 的 **SPropertyRestriction** 结构，为属性值创建容器的类型，为关系创建 RELOP_EQ。 **PR_DISPLAY_TYPE** 可设置为多个值，其中包括： 
    
   - DT_GLOBAL将层次结构表限制为属于全局地址列表的容器。
    
   - DT_LOCAL将表限制为属于本地通讯簿的容器。
    
   - DT_MODIFIABLE将表限制为可修改的容器。
    
   - 创建一 [个 SPropTagArray](sproptagarray.md) **结构**，其中包含 **PR_ENTRYID、PR_DISPLAY_TYPE** 和任何其他关注列。 
    
   - 调用 [HrQueryAllRows，](hrqueryallrows.md)传递属性限制和属性标记数组。 **HrQueryAllRows** 将返回零行或多行，对于属于指定类型的每个容器，返回一行。 准备处理任意数目的行的返回。 
    
   - 调用 **IAddrBook：：OpenEntry，** 其中条目标识符来自PR_ENTRYID关注容器的行的列。 
    
4. 如果要打开的容器属于特定的通讯簿提供程序：
    
   - 为属性标记创建具有 **PR_AB_PROVIDERS** ([PidTagAbProviders](pidtagabproviders-canonical-property.md)) 的 [SPropertyRestriction](spropertyrestriction.md)结构，为属性值创建提供程序特定的值，为关系创建 RELOP_EQ。 通常，提供程序特定的值是全局唯一标识符或 GUID。 您将在通讯簿提供程序的一个头文件中找到已发布的此值。 
    
   - 创建[一个 SPropTagArray](sproptagarray.md) 结构，其中包含 PR_ENTRYID ([PidTagEntryId](pidtagentryid-canonical-property.md)) 、PR_AB_PROVIDERS和任何其他关注列。 
    
   - 调用 [HrQueryAllRows，](hrqueryallrows.md)传递属性限制和属性标记数组。 **如果指定的通讯簿提供程序不在配置文件中，HrQueryAllRows** 将返回零行。 它可返回提供程序的顶级容器的一行或多行，具体取决于提供程序的组织方式。 
    
   - 调用[IAddrBook：：OpenEntry，](iaddrbook-openentry.md)其中条目标识符来自PR_ENTRYID关注容器的行的列。 如果你感兴趣的容器不是顶级容器，请查找顶级容器并遍历层次结构。 
    

