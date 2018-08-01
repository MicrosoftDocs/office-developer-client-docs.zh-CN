---
title: 映射和映射签名
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 773f6671-cc21-4d1f-a11d-308bc71c852d
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 16f192ae816aba2dd0e34a42fba211c3ef70ba47
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776411"
---
# <a name="mappings-and-mapping-signatures"></a>映射和映射签名

  
  
**适用于**： Outlook 
  
如果服务提供商支持命名的属性，每组标识符和名称对称为映射。 一个映射或几个可支持服务提供商。 是，一个消息存储提供程序，例如，可以实现其消息、 文件夹和消息存储对象，以使用单个列表的名称和其相应的标识符的所有**GetIDsFromNames**和**GetNamesFromIDs**方法。 其他消息存储提供程序可能对每个文件夹和邮件，其中包含一个列表或实现的每条消息和每个文件夹的唯一列表。 消息存储提供程序的唯一映射用于每个邮件必须不允许其文件夹内容表中显示，因为属性标识符将给定的属性名称，不同消息消息的命名的属性。 MAPI 建议提供程序使简单，并包括表其对象的所有单个列表执行操作。 
  
对于每个映射，服务提供商必须提供映射签名。 映射签名是二进制值，通常标识的 GUID，唯一一组属性标识符和其相应的名称。 映射签名存储在对象的**PR_MAPPING_SIGNATURE** ([PidTagMappingSignature](pidtagmappingsignature-canonical-property.md)) 属性。 对它所表示的映射进行更改时，服务提供商必须更改其**PR_MAPPING_SIGNATURE**属性的值。 例如，如果新标识符分配给的名称或新名称和标识符对添加，则必须更新**PR_MAPPING_SIGNATURE** 。 
  
客户端使用的对象的命名属性在比较和复制操作中使用的对象的**PR_MAPPING_SIGNATURE**属性。 要比较名为属性属于两个对象的标识符，不使用映射签名的客户端必须调用[IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md)上两个对象来检索每个标识符的名称。 使用的对象的映射签名会导致此呼叫不必要。 当两个对象及其**PR_MAPPING_SIGNATURE**属性的值相同时，他们使用相同的映射。 使用相同的映射的标识符可以直接进行比较。 服务提供商实现[IMAPIProp::CopyTo](imapiprop-copyto.md)和[IMAPIProp::CopyProps](imapiprop-copyprops.md)还可以利用对象的映射签名。 复制命名对象之间的属性，当服务提供商可以避免转换步骤时的源和目标对象具有相同的映射签名。 
  
## <a name="see-also"></a>另请参阅



[IMAPIProp : IUnknown](imapipropiunknown.md)


[MAPI 命名属性](mapi-named-properties.md)

