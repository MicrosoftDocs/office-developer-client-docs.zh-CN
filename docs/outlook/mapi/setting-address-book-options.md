---
title: 设置通讯簿选项
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 9bd31233-fc8d-4e0a-9f1b-218c5ecb6d1b
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: f72c916e917543b11089f8f5ef1aa4b9552a1b6a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417341"
---
# <a name="setting-address-book-options"></a>设置通讯簿选项

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
您可以设置三个属性来描述使用通讯簿的选项:
  
- **PR_AB_SEARCH_PATH**([PidTagAbSearchPath](pidtagabsearchpath-canonical-property.md))
    
    [IAddrBook:: ResolveName](iaddrbook-resolvename.md)使用**PR_AB_SEARCH_PATH**属性来确定要加入名称解析的容器以及应涉及的顺序。 对于**PR_AB_SEARCH_PATH**中的每个容器, **IAddrBook:: ResolveName**调用其[IABContainer:: ResolveNames](iabcontainer-resolvenames.md)方法。 在**PR_AB_SEARCH_PATH**开头的容器中搜索位于**PR_AB_SEARCH_PATH**末尾的容器。 
    
    **PR_AB_SEARCH_PATH**中的搜索顺序是使用[SRowSet](srowset.md)结构指定的, 这是用于表示表中的行的相同结构。 您可以通过调用[IAddrBook:: GetSearchPath](iaddrbook-getsearchpath.md)方法并通过调用[IAddrBook:: SetSearchPath](iaddrbook-setsearchpath.md)方法来更改当前搜索路径, 从而查看该路径。 
    
- **PR_AB_DEFAULT_DIR**([PidTagAbDefaultDir](pidtagabdefaultdir-canonical-property.md))
    
    **PR_AB_DEFAULT_DIR**属性是在显示通讯簿时最初显示的通讯簿容器的条目标识符。 默认目录设置将一直保持有效, 直到您通过调用[IAddrBook:: SetDefaultDir](iaddrbook-setdefaultdir.md)方法对其进行更改。 您可以通过调用[IAddrBook:: GetDefaultDir](iaddrbook-getdefaultdir.md)方法来查看默认目录。 
    
- **PR_AB_DEFAULT_PAB**([PidTagAbDefaultPab](pidtagabdefaultpab-canonical-property.md))
    
这三个属性是特殊的, 因为您无法使用标准的**IMAPIProp**方法来处理它们。 相反, 您必须使用**IAddrBook**方法。 由于无法使用**IMAPIProp:: SetProps**更改这些属性中的任何一个, 因此无需调用**IMAPIProp:: SaveChanges**以使更改永久生效。 通过**IAddrBook**方法所做的修改会立即生效。 
  
## <a name="see-also"></a>另请参阅



[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)

