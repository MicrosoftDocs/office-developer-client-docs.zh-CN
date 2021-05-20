---
title: MAPI 属性类型概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b762f5fb-7c2c-4303-96f7-0b6e657146c9
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 58dd25f09b76d97fd6441915225756a19f4ec3cb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438195"
---
# <a name="mapi-property-type-overview"></a>MAPI 属性类型概述
  
**适用于**：Outlook 2013 | Outlook 2016 
  
属性类型是由 MAPI 在 MAPIDEFS 中定义的常量。指示属性值的基础数据类型 H 头文件。 所有属性（无论是由 MAPI、客户端应用程序还是由服务提供商定义）都使用其中一种类型。 
  
属性类型遵循与用于属性标记的命名约定类似的命名约定。 许多属性类型具有单值和多值版本。 单值属性包含其类型的一个值，例如单个整数或字符串。 用于表示单个值属性的常量有两个部分：前缀 PT_描述实际类型的字符串，如 LONG 或 STRING8。 
  
多值属性包含多个类型的值。 与 OLE 变量数组不同，多值属性中的每个值都具有相同的类型。 用于表示多值属性的常量是通过将 MV_FLAG 标志与表示基类型的对应单个值常量组合创建的。 有三个部分：前缀PT_后跟MV_后跟描述类型的字符串。 例如，包含多个整数的属性的类型是PT_MV_LONG，而对于多个字符串，则PT_MV_STRING8。
  
下图显示了 [SPropValue](spropvalue.md) 结构的结构，用于描述多值整数，即类型为 PT_MV_LONG。 Value 成员扩展为包括 属性中的整数值数以及指向这些值数组的指针。 
  
**多值属性**
  
![多值属性](media/amapi_12.gif "多值属性")
  
尽管支持多值属性是可选的，但 MAPI 建议客户端和服务提供商支持这两种类型的属性，因为这样做可以实现与 MAPI 兼容的组件之间的更大交互。
  
下图列出了所有不同的属性类型常量，显示它们在 **SPropValue** 结构中存储的位置。 **Value** 成员的大小取决于特定类型。 请注意，并非所有单值类型都有多值等效项。 
  
**属性类型常量**
  
![属性类型常量](media/amapi_11.gif "属性类型常量")
  
使用属性的客户端和服务提供商需要执行两个步骤：
  
1. 确定属性是可用还是不可用。
    
2. 如果可用，请检索属性的值。
    
有时，客户端或服务提供商只需检查属性是否存在;其他时候，需要检查特定值。 例如，传输提供程序有三种不同的操作过程，用于处理 **PR \_ SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) 属性，一个布尔值，指示是否应该传输带格式文本的邮件。 如果 **PR \_ SEND_RICH_INFO** 设置为 TRUE，传输提供程序将传输格式化的文本。 如果设置为 FALSE，则传输前将丢弃格式化的文本。 如果 **PR_SEND_RICH_INFO** 不可用，则传输提供程序将遵循其默认操作过程，无论特定提供程序执行何种操作。 
  
MAPI 定义一种特殊属性类型PT_UNSPECIFIED，当属性类型未知时，客户端或服务提供商可以使用该属性类型来检索该属性。为了在事先不知道属性的类型的情况下检索属性，客户端或服务提供商调用对象的 [IMAPIProp：：GetProps](imapiprop-getprops.md) 方法，并传递由属性标识符和 PT_UNSPECIFIED 属性类型所包含的属性标记。 **GetProps** 返回 [属性的 SPropValue](spropvalue.md) 结构，PT_UNSPECIFIED类型的值。 实现 **GetProps 的服务提供商** 需要支持PT_UNSPECIFIED。 
  
某些 MAPI 对象支持本身为对象的属性。 对象属性的类型为 PT_OBJECT。 客户端和服务提供商通常使用 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md)方法（指定适当的访问接口）或支持属性的对象上的方法，而不是使用 **IMAPIProp：：GetProps** 访问这些属性。 
  
由于访问对象属性的值涉及使用对象的其中一个接口， **因此 GetProps** 不合适。 使用 **GetProps**，调用方通过 **SPropValue** 结构访问属性的值。 使用 **IMAPIProp：：OpenProperty，** 调用方将检索指向可以访问该对象的接口的指针。 **OpenProperty** 始终可用于检索对象属性。 另一个选项（在对象上调用方法）并非可用于每个对象属性。 
  
例如，每个文件夹都支持两个表，一个层次结构表和一个内容表。 这些表是文件夹的属性;其属性 **标记PR_CONTAINER_HIERARCHY (** [PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) 和 **PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) 。 表是需要 **IMAPITable** 接口来访问的对象。 客户端可以调用文件夹的 [IMAPIContainer：：GetHierarchyTable](imapicontainer-gethierarchytable.md) 方法来访问层次结构表、文件夹的 [IMAPIContainer：：GetContentsTable](imapicontainer-getcontentstable.md) 方法以访问内容表，或者文件夹的 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md) 方法访问任一表。 为了调用 **OpenProperty，** 客户端将属性的属性标记作为第一个参数传递，为要用作访问的接口传递接口标识符作为第二个参数。 这些参数 **将PR_CONTAINER_HIERARCHY或** PR_CONTAINER_CONTENTS IID_IMAPITable 。 
  
有关单值和多值属性类型的完整列表，请参阅 [属性类型](property-types.md)。 
  
## <a name="see-also"></a>另请参阅

- [MAPI 属性概述](mapi-property-overview.md)

