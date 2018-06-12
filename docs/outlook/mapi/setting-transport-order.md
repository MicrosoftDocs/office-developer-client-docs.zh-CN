---
title: 设置传输顺序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4a140ec3-9520-4119-a975-0fb6c1049967
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 71d7ebf2bc8c7bbf3b5ee6ce60959fdeee79abe3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778764"
---
# <a name="setting-transport-order"></a>设置传输顺序

  
  
**适用于**： Outlook 
  
MAPI 后台处理程序分配的基于地址类型和传输提供程序声明它们可以处理的标识符的传出邮件的责任。 传输提供程序发布支持的地址类型和标识符的列表，存储在**MAPIUID**结构 — 当 MAPI 调用其[IXPLogon::AddressTypes](ixplogon-addresstypes.md)方法，直接登录后。 收件人的地址类型存储在其**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) 属性。
  
为地址类型注册指示 MAPI 到传输提供程序可以传递给收件人其**PR_ADDRTYPE**属性设置为已注册的地址类型。 同样，为**MAPIUID**注册指示的传输提供程序可以传递给由与注册**MAPIUID**的项标识符的收件人。
  
大多数传输提供程序注册一个或多个地址类型;注册由**MAPIUID**少。 传输提供程序与通讯簿提供程序紧密耦合并了解其条目标识符格式可以注册来处理由**MAPIUID**，从而提高性能的消息。 这些紧密耦合的传输提供程序可以收件人的电子邮件地址和其他必要信息从提取的条目标识符而无需打开使用**IMAPISupport::OpenEntry**呼叫。 
  
MAPI 维护多个传输提供程序具有相同的地址类型或**MAPIUID**注册时使用的传输提供程序的顺序。 通过调用[IMsgServiceAdmin::MsgServiceTransportOrder](imsgserviceadmin-msgservicetransportorder.md) ，可以覆盖此顺序和_lpUIDList_参数传递**MAPIUID**s 所有主动传输提供程序的一个已排序的列表指向。: 
  
若要检索所有地址类型可以处理由一个活动传输提供程序的列表，请调用[IMAPISession::EnumAdrTypes](imapisession-enumadrtypes.md)。 **EnumAdrTypes**返回描述当前会话中处于活动状态的传输提供程序支持的地址类型的字符串数组。 
  

