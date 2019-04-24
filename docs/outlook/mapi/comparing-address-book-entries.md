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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335530"
---
# <a name="comparing-address-book-entries"></a>比较通讯簿条目

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供程序的[IABLogon:: CompareEntryIDs](iablogon-compareentryids.md)实现将比较两个提供程序对象的条目标识符。 MAPI 在确定这两个条目标识符是否包含提供程序的注册[MAPIUID](mapiuid.md)之后, 将调用此方法。 因此, **CompareEntryIDs**方法无需检查为_lpEntryID1_和_lpEntryID2_参数传入的条目标识符是否属于您的提供程序。 
  
调用**IABLogon:: CompareEntryIDs**等效于检索两个对象中的每个对象的**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 属性, 并直接对它们进行比较。
  
 **实现 CompareEntryIds**
  
1. 如果提供程序存储了这些信息, 请检查传入的条目标识符的类型。 例如, 一个条目标识符可能属于邮件用户, 而另一个条目标识符可能属于通讯组列表。 如果类型不匹配, 请将_lpulResult_参数的内容设置为 FALSE 并返回。 
    
2. 比较两个条目标识符的大小。 如果它们不相同, 请将_lpulResult_参数的内容设置为 FALSE 并返回。 
    
3. 检查条目标识符的大小是否为其类型的正确大小。 如果不是, 请将_lpulResult_参数的内容设置为 FALSE, 并返回错误值 MAPI_E_UNKNOWN_ENTRYID。 
    
4. 检查条目标识符是否相同。 如果比较相等, 请将_lpulResult_参数的内容设置为 TRUE 并返回。 否则, 在返回之前将其设置为 FALSE。 
    
5. 如果提供程序正在将短期条目标识符与长期标识符进行比较, 则这些标识符应相等比较。
    

