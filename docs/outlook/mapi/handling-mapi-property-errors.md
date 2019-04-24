---
title: 处理 MAPI 属性错误
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 23d68d8b-b0b6-4c32-8404-6acd23802db0
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 1dc676101d4c39544c9dd1fae94000db9963ea02
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32299384"
---
# <a name="handling-mapi-property-errors"></a>处理 MAPI 属性错误

**适用于**：Outlook 2013 | Outlook 2016 
  
以下**IMAPIProp**方法报告部分成功, 而不是完全失败或成功: 
  
[GetProps](imapiprop-getprops.md)
  
[SetProps](imapiprop-setprops.md)
  
[DeleteProps](imapiprop-deleteprops.md)
  
[CopyTo](imapiprop-copyto.md)
  
[CopyProps](imapiprop-copyprops.md)
  
**GetProps**报告在至少能够检索到某个对象的请求属性之一时, 这是完全成功的。 **GetProps**通过返回警告 MAPI_W_ERRORS_RETURNED 并在由**lppPropArray**参数指向的属性值数组中放置有关不可用属性的信息, 来指示部分成功。 此数组中不可用的属性条目包含**ulPropTag**成员中的属性类型的 PT_ERROR, 以及**值**成员的其他适当的错误值。 例如, 如果客户端调用文件夹的**GetProps**方法来检索三个属性, 而第三个属性不可用, 则邮件存储提供程序会将 PT_ERROR 放在属性值数组中的第三个属性类型中, 并在第三个属性中放置 MAPI_E_NOT_FOUND属性值。 
  
其他**IMAPIProp**方法以不同的方式报告部分成功。 这些方法通过返回 S_OK 并将错误信息放在[SPropProblemArray](spropproblemarray.md)结构中来报告部分成功。 与包含数据的**GetProps**中的属性值数组 (无论方法是成功还是失败) 不同, 这些方法中的属性问题数组仅在出现错误时才存在, 并且只有当调用方已注册相关知识时才存在。错误。 调用方必须指定有效的**SPropProblemArray**指针以注册错误消息。 
  
当**SetProps**、 **DeleteProps**、 **CopyTo**或**CopyProps**返回错误值时, 这表示失败而不是部分成功。 属性问题数组 (如果可用) 无效。 客户端不应尝试访问结构中保留的数据, 也不应尝试释放结构本身。 相应的响应是调用[IMAPIProp:: GetLastError](imapiprop-getlasterror.md)。 
  
**GetLastError**类似于 Windows SDK 中提供的相同名称的函数。 同时提供了有关错误的详细信息, 而不是返回值中提供的值。 它们都返回有关以前发生的错误的信息。 区别在于, Win32 **GetLastError**函数报告由调用线程生成的错误和**IMAPIProp:: GetLastError**方法报告由当前对象生成的错误。 也就是说, 如果客户端对邮件调用**DeleteProps** , 并返回 MAPI_E_NO_ACCESS 以指示该邮件是只读的, 则**GetLastError**将返回该邮件提供的数据。 
  
## <a name="see-also"></a>另请参阅

- [MAPI 属性概述](mapi-property-overview.md)

