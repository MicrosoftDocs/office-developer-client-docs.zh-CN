---
title: MAPI 地址类型
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: eee97982-29be-4dcf-ae11-8a38f0080ea7
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 20eb429b2574f67e8b28ae96eeb96f42840123d0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776181"
---
# <a name="mapi-address-types"></a>MAPI 地址类型

  
  
**适用于**： Outlook 
  
消息的每个用户相关联的地址类型，描述**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) 属性中存储的用户的地址的格式的字符串。 地址类型映射到地址格式。 即通过查看收件人的地址类型，客户端应用程序可以确定如何设置适用于收件人的地址的格式。 
  
例如，`SMTP`地址类型指定的标准 Internet 地址： 
  
 `username@companyname.com.`
  
和，`EX`地址类型指定的 Exchange Server 地址。 
  
所有通讯簿条目必须都具有有效的地址类型。 客户端要求其用户创建的自定义不支持通过通讯簿提供程序的收件人类型时指定的地址类型。 它们支持的条目，通讯簿提供程序所需提供有效的地址类型。 
  
MAPI 定义只有一个地址类型： MAPIPDL，代表个人通讯组列表。
  
若要获取会话中支持的所有传输提供程序的地址类型的列表，客户端应用程序，请调用**IMAPISession::EnumAdrTypes**方法。 有关详细信息，请参阅[IMAPISession::EnumAdrTypes](imapisession-enumadrtypes.md)。
  

