---
title: 打开通讯簿容器
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 89383b27-618c-4ccb-9e16-f66235c98bfe
description: '上次修改时间: 2011 年11月8日'
ms.openlocfilehash: 97fa9f9750174c112c431c62f6171f674856fa86
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436739"
---
# <a name="opening-an-address-book-container"></a>打开通讯簿容器

**适用于**：Outlook 2013 | Outlook 2016 
  
打开 MAPI 集成通讯簿后, 打开一个或多个通讯簿容器以访问其中的收件人。
  
若要打开通讯簿的顶级容器, 请使用 NULL 条目标识符调用[IAddrBook:: OpenEntry](iaddrbook-openentry.md) 。 
  
可以使用只读或读/写访问权限来实现通讯簿容器。 只读容器仅用于浏览。 可以修改读/写容器, 允许客户端创建新的条目, 并删除和修改现有条目。 所有个人通讯簿 (PAB) 容器都实现为读/写容器。 
  
若要打开任何较低级别的容器, 请调用**OpenEntry**并指定要打开的容器的条目标识符。 
  
## <a name="open-the-container-designated-as-the-pab"></a>打开指定为 PAB 的容器
  
1. 调用[IAddrBook:: GetPAB](iaddrbook-getpab.md)以检索 PAB 的条目标识符。 
    
2. 将此项标识符传递给[IAddrBook:: OpenEntry](iaddrbook-openentry.md)。
    
## <a name="open-a-container-that-is-not-the-pab"></a>打开不是 PAB 的容器
  
1. 使用 NULL 条目标识符调用[IAddrBook:: OpenEntry](iaddrbook-openentry.md) , 以打开通讯簿的根容器。 
    
2. 调用根容器的[IMAPIContainer:: GetHierarchyTable](imapicontainer-gethierarchytable.md)方法以检索其层次结构表—通讯簿中所有顶级容器的列表。 
    
3. 如果要打开的容器为特定类型:
    
   - 使用**PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) 为属性标记创建**SPropertyRestriction**结构, 为属性值创建容器的类型, 并为该关系创建 RELOP_EQ。 **PR_DISPLAY_TYPE**可设置为多个值, 其中包括: 
    
   - DT_GLOBAL 将层次结构表限制为属于全局地址列表的容器。
    
   - DT_LOCAL 将表限制为属于本地通讯簿的容器。
    
   - DT_MODIFIABLE 将表限制为可修改的容器。
    
   - 创建一个[SPropTagArray](sproptagarray.md)结构, 其中包括**PR_ENTRYID**、 **PR_DISPLAY_TYPE**和其他感兴趣的列。 
    
   - 调用[HrQueryAllRows](hrqueryallrows.md), 并传递属性限制和属性标记数组。 **HrQueryAllRows**将返回零个或多个行, 属于指定类型的每个容器一行。 准备好处理任意数量的行的返回。 
    
   - 使用表示感兴趣的容器的行的**PR_ENTRYID**列中的条目标识符调用**IAddrBook:: OpenEntry** 。 
    
4. 如果要打开的容器属于特定的通讯簿提供程序:
    
   - 创建一个[SPropertyRestriction](spropertyrestriction.md)结构, 其中包含**PR_AB_PROVIDERS** ([PidTagAbProviders](pidtagabproviders-canonical-property.md)) 的属性标记、特定于提供程序的属性值值和 RELOP_EQ 的关系。 通常, 提供程序特定的值是全局唯一的标识符或 GUID。 您将在某个通讯簿提供程序的头文件中找到发布的此值。 
    
   - 创建一个包含**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))、 **PR_AB_PROVIDERS**和任何其他感兴趣的列的[SPropTagArray](sproptagarray.md)结构。 
    
   - 调用[HrQueryAllRows](hrqueryallrows.md), 并传递属性限制和属性标记数组。 如果指定的通讯簿提供程序不在配置文件中, **HrQueryAllRows**将返回零行。 它可以返回提供程序的顶级容器的一个或多个行, 具体取决于提供程序的组织方式。 
    
   - 使用表示感兴趣的容器的行的**PR_ENTRYID**列中的条目标识符调用[IAddrBook:: OpenEntry](iaddrbook-openentry.md) 。 如果您感兴趣的容器不是顶级容器, 请查找顶级容器并遍历层次结构。 
    

