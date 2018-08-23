---
title: 处理名为属性错误
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f56c56d8-db46-4c69-876f-2bbb4a5c1185
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: f6c12973a3ee2f9842e74f6f01b94553659dc1ad
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22583307"
---
# <a name="handling-named-property-errors"></a>处理名为属性错误
  
**适用于**： Outlook 2013 |Outlook 2016 
  
当[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)或[IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md)太大的实施者处理的请求时，则返回错误值为 MAPI_E_TOO_BIG 呼叫者必须将其请求分为几个请求循环调用相应的方法。 
  
时找不到导致部分成功，如请求时将映射到特定的标识符的名称和一个或多个名称之间的呼叫， **GetNamesFromIDs**返回 MAPI_W_ERRORS_RETURNED，并将 PT_ERROR 属性类型放缺少该属性标记数组中的属性。 
  
有时，客户端到结果中要返回，例如没有属性的**GetNamesFromIDs**调用中指定的属性集，没有任何属性或由标志排除类型的所有命名的属性时。 客户端可以预期到服务提供商： 
  
- 返回 S_OK。
    
- 设置为新分配的属性标记数组与它设置为零的**cValues**成员属性标记数组指针的内容。 
    
- 设置为 NULL [MAPINAMEID](mapinameid.md)结构数组的内容。 
    
- 设置的计数**MAPINAMEID**结构为零的内容。 
    
## <a name="see-also"></a>另请参阅

- [MAPI 命名属性](mapi-named-properties.md)

