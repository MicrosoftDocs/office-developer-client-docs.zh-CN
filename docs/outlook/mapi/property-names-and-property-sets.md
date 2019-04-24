---
title: 属性名称和属性集
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: cb216f5c-c965-4372-a15b-82090a410266
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: fa9d6afcaf1b360f37e8c8873c9d1a823fcd4888
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328544"
---
# <a name="property-names-and-property-sets"></a>属性名称和属性集

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
每个命名属性的名称包含两个部分:
  
- 指定属性集的全局唯一标识符 (即 GUID)。
    
- 一个 Unicode 字符字符串或32位数字值。 
    
命名属性的名称使用[MAPINAMEID](mapinameid.md)结构进行描述。 此结构包含一个属性集成员、用于指定数字或字符串格式的名称的成员, 以及用于标识所使用的格式的成员。 由于属性集是属性名称的一部分, 因此它不是可选的。 MAPI 定义了多个用于客户端和服务提供程序的属性集, 但如果现有属性集不合适, 则可以定义新的属性集。 客户端和服务提供程序可以通过调用[CoCreateGUID](https://msdn.microsoft.com/library/ms688568.aspx)函数来定义其自己的属性集。 通常, 这些属性集是为自定义客户端应用程序创建的。 
  
MAPI 的属性集由下列常量表示:
  
PS_MAPI
  
PS_PUBLIC_STRINGS
  
PS_ROUTING_EMAIL_ADDRESSES
  
PS_ROUTING_ADDRTYPE
  
PS_ROUTING_SEARCH_KEY
  
PS_ROUTING_DISPLAY_NAME
  
PS_ROUTING_ENTRYID
  
PS_MAPI 属性集是保留的;服务提供程序使用它为具有命名属性范围下的标识符的属性生成名称。 PS_PUBLIC_STRINGS 属性集由客户端用于 IPM 邮件的命名属性。 由于 PS_PUBLIC_STRINGS 属性集中的命名属性将出现在客户端的用户界面中, 因此 nonvisible 邮件 (如属于 IPC 邮件类的邮件) 应避免使用此属性集创建命名属性。 相反, 它们应在特定于邮件类别的范围 (0x6800 到 0x7FFF) 中创建属性。
  
其他属性集保留了描述通常是路由列表成员的收件人的命名属性。 包含与收件人列表属性相关联的属性的相同类型的信息, 网关将理解这些属性集中的属性, 以要求对目标邮件系统进行映射。 由于有五种类型的信息可用于描述属性, 因此 MAPI 定义了五个不同的属性集。 发送邮件时, 如果客户端发送的邮件必须包含其路由列表成员的地址和地址类型, 则为 PS_ROUTING_EMAIL_ADDRESSES 和 PS_ROUTING_ADDRTYPE 属性集中的每个成员分配一个命名属性。 这样可确保地址和地址类型在发送到外部邮件系统时仍然可用。
  
## <a name="see-also"></a>另请参阅



[MAPI 命名属性](mapi-named-properties.md)

