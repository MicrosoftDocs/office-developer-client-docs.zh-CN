---
title: 比较通讯簿条目
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e375367b-d107-4768-95de-00b8b9dc3511
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 6ccd7a55c195b45b1fa83db6180efeacd41b968d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415353"
---
# <a name="comparing-address-book-entries"></a>比较通讯簿条目

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供程序的 [IABLogon：：CompareEntryIDs](iablogon-compareentryids.md) 实现将两个提供程序对象的条目标识符进行比较。 MAPI 在确定两个条目标识符包含提供程序的注册 [MAPIUID](mapiuid.md)后调用此方法。 因此 **，CompareEntryIDs** 方法无需检查 _为 lpEntryID1 和 lpEntryID2_ 参数传入的条目标识符是否属于您的提供程序。  
  
调用 **IABLogon：：CompareEntryIDs** 等效于检索这两个对象的 **PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 属性并直接进行比较。
  
 **实现 CompareEntryIds**
  
1. 如果您的提供程序存储该信息，请检查传入的条目标识符的类型。 例如，一个条目标识符可能属于邮件用户，而另一个可能属于通讯组列表。 如果类型不匹配，将  _lpulResult_ 参数的内容设置为 FALSE 并返回。 
    
2. 比较两个条目标识符的大小。 如果二者不相同，将  _lpulResult_ 参数的内容设置为 FALSE 并返回。 
    
3. 检查条目标识符的大小是否适合其类型。 如果没有，将  _lpulResult_ 参数的内容设置为 FALSE，并返回错误值MAPI_E_UNKNOWN_ENTRYID。 
    
4. 检查条目标识符是否相同。 如果二者相等，请将  _lpulResult_ 参数的内容设置为 TRUE 并返回。 否则，在返回之前，请设置为 FALSE。 
    
5. 如果您的提供程序将短期条目标识符与长期标识符进行比较，则它们应进行同等比较。
    

