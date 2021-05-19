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
  
您可以设置三个描述通讯簿使用选项的属性：
  
- **PR_AB_SEARCH_PATH (** [PidTagAbSearchPath](pidtagabsearchpath-canonical-property.md)) 
    
    [IAddrBook：：ResolveName](iaddrbook-resolvename.md)使用 **PR_AB_SEARCH_PATH** 属性来确定名称解析中涉及的容器及其参与顺序。 对于每个容器 **，PR_AB_SEARCH_PATH IAddrBook：：ResolveName** 调用其 [IABContainer：：ResolveNames](iabcontainer-resolvenames.md)方法。  在容器末尾 **PR_AB_SEARCH_PATH** 在容器之前搜索位于 **PR_AB_SEARCH_PATH。** 
    
    使用 [SRowSet](srowset.md) **PR_AB_SEARCH_PATH** 指定搜索顺序，该结构与用于表示表格中的行的结构相同。 可以通过调用 [IAddrBook：：GetSearchPath](iaddrbook-getsearchpath.md) 方法查看当前搜索路径，然后通过调用 [IAddrBook：：SetSearchPath](iaddrbook-setsearchpath.md) 方法更改它。 
    
- **PR_AB_DEFAULT_DIR (** [PidTagAbDefaultDir](pidtagabdefaultdir-canonical-property.md)) 
    
    the **PR_AB_DEFAULT_DIR** property is the entry identifier of the address book container to be displayed initially when the address book is displayed. 默认目录设置将一直有效，直到通过调用 [IAddrBook：：SetDefaultDir](iaddrbook-setdefaultdir.md) 方法更改它。 可以通过调用 [IAddrBook：：GetDefaultDir 方法来查看默认](iaddrbook-getdefaultdir.md) 目录。 
    
- **PR_AB_DEFAULT_PAB (** [PidTagAbDefaultPab](pidtagabdefaultpab-canonical-property.md)) 
    
这三个属性很特殊，因为您无法使用标准 **IMAPIProp** 方法使用它们。 相反，必须使用 **IAddrBook** 方法。 由于这些属性都不是使用 **IMAPIProp：：SetProps** 更改的，因此无需调用 **IMAPIProp：：SaveChanges** 来永久进行更改。 通过 **IAddrBook** 方法所做的修改会立即生效。 
  
## <a name="see-also"></a>另请参阅



[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)

