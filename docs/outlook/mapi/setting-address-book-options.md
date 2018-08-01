---
title: 设置通讯簿选项
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 9bd31233-fc8d-4e0a-9f1b-218c5ecb6d1b
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: c64f84da6bece809176bf67985b6f55ce92414a2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778758"
---
# <a name="setting-address-book-options"></a>设置通讯簿选项

  
  
**适用于**： Outlook 
  
您可以设置介绍了使用通讯簿选项的三个属性：
  
- **PR_AB_SEARCH_PATH**([PidTagAbSearchPath](pidtagabsearchpath-canonical-property.md))
    
    **PR_AB_SEARCH_PATH**属性是[IAddrBook::ResolveName](iaddrbook-resolvename.md)用于确定要名称解析和应所涉及的顺序中所涉及的容器。 对于每个容器中**PR_AB_SEARCH_PATH**， **IAddrBook::ResolveName**调用其[IABContainer::ResolveNames](iabcontainer-resolvenames.md)方法。 之前的**PR_AB_SEARCH_PATH**末尾的容器搜索**PR_AB_SEARCH_PATH**开头的容器。 
    
    使用[SRowSet](srowset.md)结构，用于表示表中的行的相同结构指定**PR_AB_SEARCH_PATH**中的搜索顺序。 您可以通过调用[IAddrBook::GetSearchPath](iaddrbook-getsearchpath.md)方法查看当前的搜索路径，并更改通过调用[IAddrBook::SetSearchPath](iaddrbook-setsearchpath.md)方法。 
    
- **PR_AB_DEFAULT_DIR**([PidTagAbDefaultDir](pidtagabdefaultdir-canonical-property.md))
    
    **PR_AB_DEFAULT_DIR**属性是通讯簿容器，以显示通讯簿时最初显示的项标识符。 默认目录设置保持有效，直到您更改通过调用[IAddrBook::SetDefaultDir](iaddrbook-setdefaultdir.md)方法。 您可以通过调用[IAddrBook::GetDefaultDir](iaddrbook-getdefaultdir.md)方法来查看默认目录。 
    
- **PR_AB_DEFAULT_PAB**([PidTagAbDefaultPab](pidtagabdefaultpab-canonical-property.md))
    
这三个属性是特殊的因为您无法使用它们使用标准**IMAPIProp**方法。 相反，您必须使用**IAddrBook**方法。 因为无这些属性可与**IMAPIProp::SetProps**更改，则无需调用**IMAPIProp::SaveChanges**进行永久更改。 通过**IAddrBook**方法所做的更改立即生效。 
  
## <a name="see-also"></a>另请参阅



[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)

