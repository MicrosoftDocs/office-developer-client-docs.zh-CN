---
title: MAPI 地址类型
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: eee97982-29be-4dcf-ae11-8a38f0080ea7
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b0ff4ecff7a6e834f1e017adc11244657896db03
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405434"
---
# <a name="mapi-address-types"></a>MAPI 地址类型

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
每个邮件用户都与一个地址类型相关联，该地址类型是描述存储在 **PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) 属性中的用户地址格式的字符串。 地址类型映射到地址格式。 也就是说，通过查看收件人的地址类型，客户端应用程序可以确定如何设置适合收件人的地址的格式。 
  
例如，  `SMTP` 地址类型指定标准 Internet 地址： 
  
 `username@companyname.com.`
  
地址 `EX` 类型指定一个Exchange Server地址。 
  
所有通讯簿条目都必须具有有效的地址类型。 客户端要求其用户在创建通讯簿提供程序不支持的自定义收件人类型时指定地址类型。 对于它们支持的条目，通讯簿提供程序需要提供有效的地址类型。 
  
MAPI 仅定义一个地址类型：MAPIPDL，它代表个人通讯组列表。
  
为了获取会话中所有传输提供程序支持的地址类型列表，客户端应用程序调用 **IMAPISession：：EnumAdrTypes** 方法。 有关详细信息，请参阅 [IMAPISession：：EnumAdrTypes](imapisession-enumadrtypes.md)。
  

