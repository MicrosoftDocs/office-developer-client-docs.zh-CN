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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419077"
---
# <a name="handling-mapi-property-errors"></a>处理 MAPI 属性错误

**适用于**：Outlook 2013 | Outlook 2016 
  
以下 **IMAPIProp** 方法报告部分成功，而不是完全失败或成功： 
  
[GetProps](imapiprop-getprops.md)
  
[SetProps](imapiprop-setprops.md)
  
[DeleteProps](imapiprop-deleteprops.md)
  
[CopyTo](imapiprop-copyto.md)
  
[CopyProps](imapiprop-copyprops.md)
  
**GetProps** 报告在可以检索对象的至少一个请求的属性时部分成功。 **GetProps** 指示部分成功，方法为返回警告MAPI_W_ERRORS_RETURNED将有关不可用属性的信息放在 **lppPropArray** 参数指向的属性值数组中。 此数组中不可用属性的条目包含 **PT_ERROR ulPropTag** 成员中的属性类型的值，MAPI_E_NOT_FOUND Value 成员的另一个相应 **错误** 值。 例如，如果客户端调用文件夹 **的 GetProps** 方法来检索三个属性，而第三个属性不可用，则邮件存储提供程序将 PT_ERROR 作为属性值数组的第三个属性类型，而将 MAPI_E_NOT_FOUND 第三个属性值。 
  
其他 **IMAPIProp 方法** 报告部分成功的方式有所不同。 这些方法通过返回错误值S_OK将错误信息置于 [SPropProblemArray](spropproblemarray.md) 结构中来报告部分成功。 与包含数据的 **GetProps** 中的属性值数组不同，无论该方法是成功还是失败，这些方法中的属性问题数组仅在存在错误且调用方已注册有兴趣了解错误时存在。 调用方必须指定有效的 **SPropProblemArray** 指针以注册错误信息。 
  
从 **SetProps、DeleteProps、CopyTo** 或 **CopyProps** 返回错误值时，这表示失败而不是部分成功。  属性问题数组（如果可用）无效。 客户端不应尝试访问结构中存储的数据，也不应尝试释放结构本身。 相应的响应是调用 [IMAPIProp：：GetLastError](imapiprop-getlasterror.md)。 
  
**GetLastError** 与 Windows SDK 中提供的相同名称的函数类似。 与返回值一样，二者都提供有关错误的详细信息。 它们都返回有关之前发生的错误的信息。 区别在于 Win32 **GetLastError** 函数报告调用线程生成的错误 **，IMAPIProp：：GetLastError** 方法报告当前对象生成的错误。 也就是说，如果客户端对邮件调用 **DeleteProps** 并返回 MAPI_E_NO_ACCESS以指示邮件是只读的， **则 GetLastError** 将返回邮件提供的数据。 
  
## <a name="see-also"></a>另请参阅

- [MAPI 属性概述](mapi-property-overview.md)

