---
title: 删除收件人
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f7495030-e3b8-4c7c-9e19-284ba820e846
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: bd01c66d9fff7c94ffb1ce9f956f1951bc482020
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421044"
---
# <a name="deleting-a-recipient"></a>删除收件人

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 **从可修改容器中删除一个或多个通讯簿条目**
  
- 调用 [IABContainer：:D eleteEntries](iabcontainer-deleteentries.md) 方法，传递表示要删除的通讯簿条目的条目标识符数组。 **DeleteEntries** 可以返回警告MAPI_W_PARTIAL_COMPLETION，以指示无法删除一个或多个条目。 使用 HR_FAILED 宏测试此返回值，如果需要有关问题详细信息，请调用容器的[IMAPIProp：：GetLastError](imapiprop-getlasterror.md)方法。 
    
在缓存中保留指向已删除条目 [的 ADRENTRY](adrentry.md) 结构的指针时，仍可以使用其条目标识符检索属性。 这是因为条目仅标记为删除。 MAPI 按设计维护对这些标记条目的访问级别。 
  

