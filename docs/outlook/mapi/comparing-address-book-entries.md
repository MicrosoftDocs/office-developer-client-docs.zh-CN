---
title: 比较通讯簿条目
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e375367b-d107-4768-95de-00b8b9dc3511
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 808d5f4bfca15cae4ca7aab6758d3b5361813bd4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774666"
---
# <a name="comparing-address-book-entries"></a>比较通讯簿条目

  
  
**适用于**： Outlook 
  
您的提供商[IABLogon::CompareEntryIDs](iablogon-compareentryids.md)实现提供程序的对象中的两个比较的项标识符。 确定两个条目标识符包含您的提供商注册[MAPIUID](mapiuid.md)后，MAPI 调用此方法。 因此，您**CompareEntryIDs**方法需要检查对于_lpEntryID1_和_lpEntryID2_参数中传递的项标识符属于您的提供商。 
  
调用**IABLogon::CompareEntryIDs**等效于两个对象的每个检索**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 属性，并直接进行比较。
  
 **若要实现 CompareEntryIds**
  
1. 检查传递中，如果您的提供商将该信息存储的项标识符的类型。 例如，一个条目标识符可能属于邮件用户时其他可能属于通讯组列表。 如果类型不匹配，则设置为 FALSE 和返回_lpulResult_参数的内容。 
    
2. 比较两个条目标识符的大小。 如果不是相同，设置为 FALSE，并返回_lpulResult_参数的内容。 
    
3. 检查的项标识符的大小是正确的大小为其类型。 否则，将_lpulResult_参数的内容设置为 FALSE，并返回错误值 MAPI_E_UNKNOWN_ENTRYID。 
    
4. 检查条目标识符是否相同。 如果它们同样比较，设置为 TRUE 和返回_lpulResult_参数的内容。 否则，将其设置为 FALSE 返回之前。 
    
5. 如果您的提供商比较具有长期标识符的短期条目标识符，他们应同样比较。
    

