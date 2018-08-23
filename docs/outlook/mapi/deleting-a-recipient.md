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
ms.openlocfilehash: 03917ad52f1dc1ce4d0b59cd54fe33f58f352061
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22582943"
---
# <a name="deleting-a-recipient"></a>删除收件人

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
 **若要从可修改容器中删除一个或多个通讯簿条目**
  
- 调用[IABContainer::DeleteEntries](iabcontainer-deleteentries.md)方法，传递表示通讯簿条目，要删除的项标识符的数组。 **DeleteEntries**可以返回一个警告，MAPI_W_PARTIAL_COMPLETION，以指明它无法删除一个或多个条目。 测试此返回值与**HR_FAILED**宏，并调用容器的[IMAPIProp::GetLastError](imapiprop-getlasterror.md)方法，如果需要有关问题的详细信息。 
    
当您在缓存中已删除的条目[ADRENTRY](adrentry.md)结构容纳的指针时，您仍然能够检索使用其项标识符的属性。 这是因为该条目仅标记为删除。 MAPI 设计维护对这些标记的项的访问级别。 
  

