---
title: 处理 MAPI 属性错误
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 23d68d8b-b0b6-4c32-8404-6acd23802db0
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 82f37e2a6f6834c7a8553a3d9d364f7e657d81da
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579506"
---
# <a name="handling-mapi-property-errors"></a>处理 MAPI 属性错误

**适用于**： Outlook 2013 |Outlook 2016 
  
而不是完整故障或成功时，以下**IMAPIProp**方法报告部分成功： 
  
[GetProps](imapiprop-getprops.md)
  
[SetProps](imapiprop-setprops.md)
  
[DeleteProps](imapiprop-deleteprops.md)
  
[CopyTo](imapiprop-copyto.md)
  
[CopyProps](imapiprop-copyprops.md)
  
**GetProps**报告部分成功时能够检索在至少一个对象的请求属性。 **GetProps**指示部分成功返回警告 MAPI_W_ERRORS_RETURNED 和**lppPropArray**参数指向属性值数组中发出有关不可用的属性的信息。 该数组中的不可用属性条目包含 PT_ERROR **ulPropTag**成员和 MAPI_E_NOT_FOUND 或另一个相应的错误值中的属性类型的**值**成员。 例如，如果要检索三个属性的某个文件夹的**GetProps**方法在客户端调用和第三个不可用，消息存储提供程序 PT_ERROR 中放置属性值数组中的第三个属性类型和在第三 MAPI_E_NOT_FOUND属性值。 
  
其他**IMAPIProp**方法报告部分成功各不相同。 这些方法通过返回 S_OK 和[SPropProblemArray](spropproblemarray.md)结构中发出错误信息报告部分成功。 与**GetProps**包含数据，而不管方法成功还是失败，这些方法中的属性问题数组才会存在错误和仅当呼叫者已注册的兴趣了解中的属性值数组不同出现错误。 呼叫者必须指定一个有效的**SPropProblemArray**指针注册错误信息。 
  
从**SetProps**、 **DeleteProps**、 **CopyTo**或**CopyProps**返回错误值时，这表明失败而不是部分成功。 属性问题数组，如果可用，无效。 客户端不应尝试访问数据结构中保留也应尝试忙结构本身。 相应的响应是调用[IMAPIProp::GetLastError](imapiprop-getlasterror.md)。 
  
类似于 Windows SDK 中提供的相同名称的函数**时出错**。 同时提供更详细的有关错误的信息比可用的返回值。 都返回前面发生的错误有关的信息。 区别在于 Win32 **GetLastError**函数的调用线程生成错误报告和**IMAPIProp::GetLastError**方法报告当前对象生成一个错误。 也就是说，如果客户端上的邮件和 MAPI_E_NO_ACCESS 调用**DeleteProps**返回以指示邮件是只读的**GetLastError**返回提供的邮件数据。 
  
## <a name="see-also"></a>另请参阅

- [MAPI 属性概述](mapi-property-overview.md)

