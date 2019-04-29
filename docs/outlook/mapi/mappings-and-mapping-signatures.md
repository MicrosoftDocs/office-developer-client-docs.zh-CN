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
  
当服务提供程序支持命名属性时, 每组标识符和名称对称为一个映射。 服务提供程序可以支持一个或多个映射。 也就是说, 一个邮件存储提供程序可以实现其所有邮件、文件夹和邮件存储对象的**GetIDsFromNames**和**GetNamesFromIDs**方法, 使其与单个名称列表及其对应的标识符一起使用。 另一个邮件存储提供程序可能有一个列表, 其中包含每个文件夹和其中包含的邮件, 或者为每个邮件和每个文件夹实现一个唯一的列表。 对每个邮件使用唯一映射的邮件存储提供程序必须不允许命名属性出现在其文件夹内容表中, 因为对于给定的属性名称, 属性标识符将因邮件而异。 MAPI 建议提供程序将其简化, 并对其所有对象 (包括表) 的单个列表运行。 
  
对于每个映射, 服务提供程序都必须提供映射签名。 映射签名是一个二进制值, 通常是一个 GUID, 它唯一标识一组属性标识符及其对应的名称。 映射签名存储在对象的**PR_MAPPING_SIGNATURE** ([PidTagMappingSignature](pidtagmappingsignature-canonical-property.md)) 属性中。 每当对它所表示的映射进行更改时, 服务提供程序必须更改其**PR_MAPPING_SIGNATURE**属性的值。 例如, 如果向某个名称分配了新的标识符, 或者添加了新的名称和标识符对, 则必须更新**PR_MAPPING_SIGNATURE** 。 
  
使用对象的命名属性的客户端在比较和复制操作中使用对象的**PR_MAPPING_SIGNATURE**属性。 若要比较属于两个对象的命名属性标识符, 不使用映射签名的客户端必须在两个对象上调用[IMAPIProp:: GetNamesFromIDs](imapiprop-getnamesfromids.md)以检索每个标识符的名称。 使用对象的映射签名可不必要地呈现此呼叫。 当两个对象的**PR_MAPPING_SIGNATURE**属性具有相同的值时, 它们将使用相同的映射。 可以直接对使用相同映射的标识符进行比较。 实现[IMAPIProp:: CopyTo](imapiprop-copyto.md)和[IMAPIProp:: CopyProps](imapiprop-copyprops.md)的服务提供程序还可以利用对象的映射签名。 当复制对象之间的命名属性时, 当源和目标对象具有相同的映射签名时, 服务提供程序可以避免转换步骤。 
  
## <a name="see-also"></a>另请参阅



[IMAPIProp : IUnknown](imapipropiunknown.md)


[MAPI 命名属性](mapi-named-properties.md)

