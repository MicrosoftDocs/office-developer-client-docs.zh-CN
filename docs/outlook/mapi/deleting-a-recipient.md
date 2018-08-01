---
title: 删除收件人
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f7495030-e3b8-4c7c-9e19-284ba820e846
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 9a3006b43eb9f210603ff3a3d890118e7fd61d7a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774760"
---
# <a name="deleting-a-recipient"></a>删除收件人

  
  
**适用于**： Outlook 
  
 **若要从可修改容器中删除一个或多个通讯簿条目**
  
- 调用[IABContainer::DeleteEntries](iabcontainer-deleteentries.md)方法，传递表示通讯簿条目，要删除的项标识符的数组。 **DeleteEntries**可以返回一个警告，MAPI_W_PARTIAL_COMPLETION，以指明它无法删除一个或多个条目。 测试此返回值与**HR_FAILED**宏，并调用容器的[IMAPIProp::GetLastError](imapiprop-getlasterror.md)方法，如果需要有关问题的详细信息。 
    
当您在缓存中已删除的条目[ADRENTRY](adrentry.md)结构容纳的指针时，您仍然能够检索使用其项标识符的属性。 这是因为该条目仅标记为删除。 MAPI 设计维护对这些标记的项的访问级别。 
  

