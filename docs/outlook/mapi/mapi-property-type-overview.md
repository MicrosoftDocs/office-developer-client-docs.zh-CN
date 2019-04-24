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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328254"
---
# <a name="mapi-property-type-overview"></a>MAPI 属性类型概述
  
**适用于**：Outlook 2013 | Outlook 2016 
  
属性类型是由 MAPI 在 mapidefs.h 中定义的常量。H 头文件, 指示属性值的基础数据类型。 所有属性, 无论是由 MAPI、客户端应用程序还是服务提供商定义的, 都可以使用其中一种类型。 
  
属性类型遵循与用于属性标记的命名约定相似的命名约定。 许多属性类型都有一个单值版本和多值版本。 单值属性包含其类型的一个值, 例如单个整数或字符串。 用于表示单个值属性的常量有两个部分: 前缀 PT_ 和描述实际类型的字符串, 如 LONG 或 STRING8。 
  
多值属性包含一个或多个其类型的值。 与 OLE variant 数组不同, 多值属性中的每个值都具有相同的类型。 用于表示多值属性的常量是通过将 MV_FLAG 标志与对应的单个 value 常量 (表示基类型) 相结合来创建的。 有三个部分: 前缀 PT_ 后跟 MV_, 后跟描述类型的字符串。 例如, 包含多个整数的属性的类型为 PT_MV_LONG, 多字符字符串的类型为 PT_MV_STRING8。
  
下图显示了[SPropValue](spropvalue.md)结构的结构, 用于描述多值整数, 即 PT_MV_LONG 类型的属性。 **值**成员将展开, 以包含属性中的整数值数和指向这些值的数组的指针的计数。 
  
**多值属性**
  
![多值属性](media/amapi_12.gif "多值属性")
  
虽然对多值属性的支持是可选的, 但 MAPI 建议客户端和服务提供程序支持这两种属性类型, 因为这样做可以在符合 MAPI 的组件之间进行更大的交互。
  
下图列出了所有不同的属性类型常量, 显示它们在**SPropValue**结构中的存储位置。 **值**成员的大小取决于特定的类型。 请注意, 并非所有单值类型都有多值等效项。 
  
**属性类型常量**
  
![属性类型常量](media/amapi_11.gif "属性类型常量")
  
使用属性的客户端和服务提供商需要执行以下两个步骤:
  
1. 确定属性可用或不可用。
    
2. 如果可用, 请检索属性的值。
    
有时, 客户端或服务提供商只需检查是否存在属性;其他时候, 需要检查特定值。 例如, 传输提供程序具有三个用于处理**\_PR SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) 属性的不同操作课程, 一个布尔值, 指示是否应使用发送邮件格式化文本。 如果**PR\_SEND_RICH_INFO**设置为 TRUE, 则传输提供程序将传输格式化的文本。 如果设置为 FALSE, 则在传输前放弃格式化的文本。 如果**PR_SEND_RICH_INFO**不可用, 则传输提供程序将遵循其默认的操作过程, 即针对特定提供程序的任何内容。 
  
MAPI 定义了一个特殊的属性类型 PT_UNSPECIFIED, 客户端或服务提供程序可以使用该属性类型在属性类型未知时检索属性。若要检索属性而不事先了解其类型, 客户端或服务提供程序将调用对象的[IMAPIProp:: GetProps](imapiprop-getprops.md)方法, 并传递一个由属性的标识符和 PT_UNSPECIFIED 属性类型组成的属性标记。 **GetProps**返回属性的[SPropValue](spropvalue.md)结构, 并将 PT_UNSPECIFIED 替换为适当的类型。 实现**GetProps**的服务提供程序需要支持 PT_UNSPECIFIED。 
  
某些 MAPI 对象支持本身就是对象的属性。 对象属性的类型为 PT_OBJECT。 除了使用**IMAPIProp:: GetProps**访问这些属性, 客户端和服务提供商通常用户是[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法, 为 access 指定适当的界面, 或者对象的方法支持属性。 
  
由于访问 object 属性的值涉及使用对象的接口之一, 因此**GetProps**不适当。 通过**GetProps**, 调用方通过**SPropValue**结构访问属性的值。 通过**IMAPIProp:: OpenProperty**, 调用方将检索指向可访问该对象的接口的指针。 **OpenProperty**可始终用于检索对象属性。 在对象上调用方法的另一个选项对每个对象属性不可用。 
  
例如, 每个文件夹支持两个表, 即层次结构表和内容表。 这些表是文件夹的属性;其属性标记为**PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) 和**PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md))。 表是需要**IMAPITable**接口进行访问的对象。 客户端可以调用文件夹的[IMAPIContainer:: GetHierarchyTable](imapicontainer-gethierarchytable.md)方法以访问层次结构表、文件夹的[IMAPIContainer:: GetContentsTable](imapicontainer-getcontentstable.md)方法以访问内容表, 或者文件夹的[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)用于访问任意一个表的方法。 若要调用**OpenProperty**, 客户端会将属性的属性标记作为第一个参数传递, 并将用于 access 的接口标识符作为第二个参数进行传递。 这些参数将为**PR_CONTAINER_HIERARCHY**或**PR_CONTAINER_CONTENTS**和**IID_IMAPITable**。
  
有关单值和多值属性类型的完整列表, 请参阅[属性类型](property-types.md)。 
  
## <a name="see-also"></a>另请参阅

- [MAPI 属性概述](mapi-property-overview.md)

