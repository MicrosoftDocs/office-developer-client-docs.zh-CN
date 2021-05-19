---
title: 设置传输顺序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4a140ec3-9520-4119-a975-0fb6c1049967
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: efa2d6ab9edbd50634093b5185ef9036689f1379
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433596"
---
# <a name="setting-transport-order"></a>设置传输顺序

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 后台处理程序根据传输提供程序声明可以处理的地址类型和标识符分配传出邮件的责任。 当 MAPI 在登录后直接调用 [其 IXPLogon：：AddressTypes](ixplogon-addresstypes.md)方法时，传输提供程序将发布受支持的地址类型和标识符的列表（存储在 **MAPIUID** 结构中）。 收件人的地址类型存储在其[PidTagAddressType PR_ADDRTYPE (PidTagAddressType](pidtagaddresstype-canonical-property.md)) 属性中。 
  
注册地址类型向 MAPI 指示传输提供程序可以发送给其 PR_ADDRTYPE **属性设置为** 注册地址类型的收件人。 同样，注册 **MAPIUID** 指示传输提供程序可以传递至使用注册 **的 MAPIUID** 的条目标识符表示的收件人。
  
大多数传输提供程序注册一个或多个地址类型;很少通过 **MAPIUID 注册**。 与通讯簿提供程序紧密结合并了解其条目标识符格式的传输提供程序可以通过 **MAPIUID** 注册以处理邮件，从而提高性能。 这些紧密耦合的传输提供程序可以从条目标识符中提取收件人的电子邮件地址和其他必要信息，而无需使用 **IMAPISupport：：OpenEntry** 调用打开它。 
  
MAPI 维护传输提供程序的顺序，当多个传输提供程序已注册同一地址类型或 **MAPIUID 时，** 可以通过调用 [IMsgServiceAdmin：：MsgServiceTransportOrder](imsgserviceadmin-msgservicetransportorder.md)并传递由 _lpUIDList_ 参数指向的所有活动传输提供程序的 **MAPIUID** 的有序列表来替代此顺序： 
  
若要检索一个活动传输提供程序可以处理的所有地址类型的列表，请调用 [IMAPISession：：EnumAdrTypes](imapisession-enumadrtypes.md)。 **EnumAdrTypes** 返回一个字符串数组，该数组描述当前会话中处于活动状态的传输提供程序支持的地址类型。 
  

