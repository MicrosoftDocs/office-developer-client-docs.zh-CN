---
title: 实施高级搜索
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 08cc60d4-cac8-4ba5-bd7f-a56e63697be3
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 35d41ff903c5ed22c5210adf6448dfded0afe4b6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332814"
---
# <a name="implementing-advanced-searching"></a>实施高级搜索

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
某些通讯簿容器支持高级搜索功能, 使客户端可以搜索除**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 以外的属性。 若要支持高级搜索, 提供程序必须实现可通过其他容器的**PR_SEARCH** ([PidTagSearch](pidtagsearch-canonical-property.md)) 属性访问的特殊容器。 **PR_SEARCH**包含一个 container 对象, 该对象提供对显示表的访问, 该对象描述用于输入和编辑高级搜索条件的对话框。 
  
 **支持高级搜索**
  
1. 为每个搜索条件定义属性。
    
2. 在容器的[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法中处理**PR_SEARCH**属性的代码部分: 
    
1. 检查客户端是否正在请求**IMAPIContainer**接口。 如果请求的接口不正确, 将失败并返回 MAPI_E_INTERFACE_NOT_SUPPORTED。 
    
2. 创建支持**IMAPIContainer**接口的新搜索对象。 
    
3. 此时, 将对您的搜索容器的**IMAPIProp:: OpenProperty**方法进行调用, 以检索其**PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性。 提供程序必须提供一个显示表 (通常通过调用[BuildDisplayTable](builddisplaytable.md)) 来描述容器的 "高级搜索" 对话框。
    
4. MAPI 显示 "搜索" 对话框, 允许用户输入相应的条件。 当用户完成时, MAPI 将调用容器的[IMAPIProp:: SetProps](imapiprop-setprops.md)方法来存储搜索条件。 
    
5. 将发出调用以请求搜索容器的内容表。 使用容器中与条件匹配的所有条目填充 "内容" 表。
    

