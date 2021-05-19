---
title: 映射和映射签名
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 773f6671-cc21-4d1f-a11d-308bc71c852d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: cd26ce4bc2da3da639b4a611fc9a69f39b13e5f3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410012"
---
# <a name="mappings-and-mapping-signatures"></a>映射和映射签名

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
当服务提供商支持命名属性时，每组标识符和名称对都称为映射。 服务提供商可以支持一个或多个映射。 也就是说，例如，一个邮件存储提供程序可以针对其所有邮件、文件夹和邮件存储对象实现 **GetIDsFromNames** 和 **GetNamesFromIDs** 方法，以使用单个名称列表及其对应的标识符。 另一个邮件存储提供程序可能针对每个文件夹及其中包含的邮件具有一个列表，或者针对每封邮件和每个文件夹实现一个唯一列表。 对每封邮件使用唯一映射的邮件存储提供程序不得允许命名属性显示在其文件夹内容表中，因为对于给定的属性名称，属性标识符将因邮件不同而不同。 MAPI 建议提供程序保持简单，并针对其所有对象（包括表）使用单个列表。 
  
对于每个映射，服务提供商必须提供映射签名。 映射签名是一个二进制值，通常为 GUID，用于唯一标识一组属性标识符及其相应的名称。 映射签名存储在对象的 PR_MAPPING_SIGNATURE ([PidTagMappingSignature](pidtagmappingsignature-canonical-property.md)) 属性中。  只要对它表示的映射进行了PR_MAPPING_SIGNATURE，服务提供商就必须更改其 PR_MAPPING_SIGNATURE 属性的值。  例如 **，PR_MAPPING_SIGNATURE** 新标识符或添加了新名称和标识符对，则必须更新该标识符。 
  
使用对象的命名属性的客户端在比较 **和复制操作PR_MAPPING_SIGNATURE** 对象的属性。 为了比较属于两个对象的命名属性标识符，没有使用映射签名的客户端必须调用这两个对象上的 [IMAPIProp：：GetNamesFromIDs](imapiprop-getnamesfromids.md) 以检索每个标识符的名称。 使用对象的映射签名会使此调用成为不必要的。 当两个对象的两个属性 **PR_MAPPING_SIGNATURE相同时** ，它们使用相同的映射。 可以直接比较使用相同映射的标识符。 实现 [IMAPIProp：：CopyTo](imapiprop-copyto.md) 和 [IMAPIProp：：CopyProps](imapiprop-copyprops.md) 的服务提供商还可以利用对象的映射签名。 在对象之间复制命名属性时，当源对象和目标对象具有相同的映射签名时，服务提供商可以避免转换步骤。 
  
## <a name="see-also"></a>另请参阅



[IMAPIProp : IUnknown](imapipropiunknown.md)


[MAPI 命名属性](mapi-named-properties.md)

