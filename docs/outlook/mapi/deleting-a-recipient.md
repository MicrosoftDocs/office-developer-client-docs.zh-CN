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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316812"
---
# <a name="deleting-a-recipient"></a>删除收件人

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 **从可修改的容器中删除一个或多个通讯簿条目**
  
- 调用[IABContainer::D eleteentries](iabcontainer-deleteentries.md)方法, 传递表示要删除的通讯簿条目的条目标识符的数组。 **DeleteEntries**可以返回一个警告 MAPI_W_PARTIAL_COMPLETION, 以指示它无法删除一个或多个条目。 如果需要有关该问题的详细信息, 请使用**HR_FAILED**宏测试此返回值并调用容器的[IMAPIProp:: GetLastError](imapiprop-getlasterror.md)方法。 
    
当您将指向已删除项的[ADRENTRY](adrentry.md)结构的指针保存在缓存中时, 您仍可以使用其条目标识符检索属性。 这是因为该条目仅标记为删除。 MAPI 通过设计维护对这些标记的项的访问级别。 
  

