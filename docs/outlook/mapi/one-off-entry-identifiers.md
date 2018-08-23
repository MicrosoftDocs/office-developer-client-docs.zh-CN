---
title: 一次性条目标识符
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 741d21ae-f14a-4b7f-80aa-91d0f0ff3f34
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 3a086d1b9bcc1eae620b2f0a5ce96a545ce68342
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22585533"
---
# <a name="one-off-entry-identifiers"></a>一次性条目标识符
  
**适用于**： Outlook 2013 |Outlook 2016 
  
一次性条目标识符创建**IAddrBook::CreateOneOff**方法中的 MAPI 和不具有访问 MAPI 子系统，如网关组件的组件。 有关详细信息，请参阅[IAddrBook::CreateOneOff](iaddrbook-createoneoff.md)。 下图显示了一次性条目标识符格式。
  
**一次性条目标识符格式**
  
![一次性条目标识符格式](media/amapi_69.gif "一次性条目标识符格式")
  
第一个域是标识为表示自定义的收件人的项标识符的特殊[MAPIUID](mapiuid.md)结构。 此**MAPIUID**结构必须设置为常量 MAPI_ONE_OFF_UID。 MAPI_ONE_OFF_UID MAPIDEFS 的头文件中定义。H。 
  
版本和标志字段是 16 位 Intel 字节顺序中的单词。 版本字段必须设置为零。 标志字段可以设置为下列值：
  
MAPI_ONE_OFF_NO_RICH_INFO
  
MAPI_ONE_OFF_UNICODE
  
如果收件人不应接收消息内容传输中性封装格式 (TNEF) 中，设置了 MAPI_ONE_OFF_NO_RICH_INFO 标志。 时 MAPI_SEND_NO_RICH_INFO 传递给[IAddrBook::CreateOneOff](iaddrbook-createoneoff.md)方法设置此标志。 
  
Unicode 字符串的显示名称和电子邮件地址时设置 MAPI_ONE_OFF_UNICODE 标志。 当 MAPI_UNICODE 传递给**IAddrBook::CreateOneOff**设置此标志。 当 MAPI_UNICODE 标志不传递给**CreateOneOff**时，MAPI 假定的显示名称和电子邮件地址字符串在工作站的当前的 ANSI 字符集。 ANSI 字符串通常不非常适用于使用不同的字符集，因为的项标识符未编码的代码页的平台之间发送的邮件。 若要防止此潜在不兼容性，多个地址类型，仅限于仅共有跨多个字符集这些字符。 但是，若要确保字符设置和平台兼容性，客户端应该使用 Unicode 字符串在其邮件中。
  
显示名称为 null 结尾的收件人的**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性以及与_lpszName_参数传递给**IAddrBook::CreateOneOff**相对应的字符串。 字符集时 MAPI_ONE_OFF_UNICODE 标志是设置和 ANSI 清除时，将 Unicode。 
  
地址类型是收件人的**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) 属性以及与传递给**IAddrBook::CreateOneOff** _lpszAdrType_参数相对应以 null 结尾的字符串。 
  
该电子邮件地址是收件人的**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) 属性以及与传递给**IAddrBook::CreateOneOff** _lpszAddress_参数相对应以 null 结尾的字符串。 
  
> [!NOTE]
> 一次性条目标识符结构; 中没有空白字节被完全如上所示打包和项标识符长度不应包含任何字节超出的电子邮件地址的终止 null 字符。 
  
客户端和手动构建一次性条目标识符的通讯簿提供程序可能还需要生成**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 和**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 属性的值。 记录关键是相同的项标识符。 应通过将按以下顺序的以下字段形成搜索关键字：
  
1. 地址类型，转换为大写字符。
    
2. 冒号 （:）。
    
3. 电子邮件地址，转换为大写字符。
    
4. 终止空字符。
    
生成搜索关键字时，必须不完成任何字符集转换。
  

