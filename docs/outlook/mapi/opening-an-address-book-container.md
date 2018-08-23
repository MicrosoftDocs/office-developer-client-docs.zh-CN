---
title: 打开通讯簿容器
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 89383b27-618c-4ccb-9e16-f66235c98bfe
description: 上次修改时间： 2011 年 11 月 8 日
ms.openlocfilehash: 79f1f9254e69e1871e886fa0bb3fbb66e2aab128
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22590454"
---
# <a name="opening-an-address-book-container"></a>打开通讯簿容器

**适用于**： Outlook 2013 |Outlook 2016 
  
打开 MAPI 集成通讯簿后，打开要访问其中的收件人的一个或多个地址簿容器。
  
若要打开通讯簿的顶级容器，调用[IAddrBook::OpenEntry](iaddrbook-openentry.md) NULL 条目标识符。 
  
通讯簿容器可在只读实施或读/写访问。 只读容器仅用于浏览。 读/写容器可以进行修改，允许客户端以创建新条目并删除和修改现有的条目。 所有个人通讯簿 (PAB) 的容器实现为读/写容器。 
  
若要打开任何较低级别的容器，调用**OpenEntry** ，并指定要在打开的容器的项标识符。 
  
## <a name="open-the-container-designated-as-the-pab"></a>打开指定为 PAB 容器
  
1. 调用[IAddrBook::GetPAB](iaddrbook-getpab.md)检索 PAB 的项标识符。 
    
2. 传递给[IAddrBook::OpenEntry](iaddrbook-openentry.md)此条目标识符。
    
## <a name="open-a-container-that-is-not-the-pab"></a>打开不是 PAB 容器
  
1. 要打开通讯簿的根容器 NULL 条目标识符调用[IAddrBook::OpenEntry](iaddrbook-openentry.md) 。 
    
2. 调用根容器[IMAPIContainer::GetHierarchyTable](imapicontainer-gethierarchytable.md)方法来检索其层次结构表 — 所有通讯簿中的顶级容器的列表。 
    
3. 如果容器来打开特定类型的：
    
   - 属性标记、 对该属性值，容器的类型和关系 RELOP_EQ 使用**PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) 创建**SPropertyRestriction**结构。 **PR_DISPLAY_TYPE**可以将多个值，它们之间设置： 
    
   - DT_GLOBAL 来限制在全局地址列表所属的容器层次结构表。
    
   - DT_LOCAL 限制属于本地通讯簿容器表。
    
   - DT_MODIFIABLE 以限制可以修改的容器的表。
    
   - 创建包含**PR_ENTRYID**、 **PR_DISPLAY_TYPE**和感兴趣的任何其他列[SPropTagArray](sproptagarray.md)结构。 
    
   - 调用[HrQueryAllRows](hrqueryallrows.md)，传递在属性限制和属性标记数组。 **HrQueryAllRows**将返回零个或多行，对每个容器属于指定类型的一行。 准备处理返回的任意数量的行。 
    
   - 调用**IAddrBook::OpenEntry**表示感兴趣的容器的行的**PR_ENTRYID**列中的项标识符。 
    
4. 如果要在打开的容器属于特定地址簿提供程序：
    
   - 为属性标记，属性值，提供程序特定值 RELOP_EQ 关系与**PR_AB_PROVIDERS** ([PidTagAbProviders](pidtagabproviders-canonical-property.md)) 创建[SPropertyRestriction](spropertyrestriction.md)结构。 通常的特定于提供程序的值为的全局唯一标识符或 GUID。 您可以找到该值发布在某个通讯簿提供程序的标头文件。 
    
   - 创建包含**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))、 **PR_AB_PROVIDERS**和感兴趣的任何其他列[SPropTagArray](sproptagarray.md)结构。 
    
   - 调用[HrQueryAllRows](hrqueryallrows.md)，传递在属性限制和属性标记数组。 如果指定的地址簿提供程序不是配置文件中， **HrQueryAllRows**将返回零行。 它可以返回一个或多个行的提供程序的顶级容器，具体取决于提供程序的组织方式。 
    
   - 调用[IAddrBook::OpenEntry](iaddrbook-openentry.md)表示感兴趣的容器的行的**PR_ENTRYID**列中的项标识符。 如果您感兴趣的容器不是顶级容器，查找的顶级容器和遍历层次结构。 
    

