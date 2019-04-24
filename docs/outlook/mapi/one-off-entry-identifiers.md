---
title: 一次性条目标识符
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 741d21ae-f14a-4b7f-80aa-91d0f0ff3f34
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: abe52cb45e13e6713d28fffe379e245e2483bffa
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32279688"
---
# <a name="one-off-entry-identifiers"></a>一次性条目标识符
  
**适用于**：Outlook 2013 | Outlook 2016 
  
一次性条目标识符由 MAPI 在**IAddrBook:: CreateOneOff**方法和不具有 MAPI 子系统访问权限的组件 (如网关组件) 中创建。 有关详细信息, 请参阅[IAddrBook:: CreateOneOff](iaddrbook-createoneoff.md)。 下图显示一次性条目标识符的格式。
  
**一次性条目标识符格式**
  
![一次性条目标识符格式](media/amapi_69.gif "一次性条目标识符格式")
  
第一个字段是一个特殊的[MAPIUID](mapiuid.md)结构, 用于标识代表自定义收件人的条目标识符。 必须将此**MAPIUID**结构设置为常量 MAPI_ONE_OFF_UID。 MAPI_ONE_OFF_UID 是在头文件 mapidefs.h 中定义的。水平. 
  
"版本" 和 "标志" 字段是采用英特尔字节顺序的16位单词。 "版本" 字段必须设置为零。 可以将 "flags" 字段设置为以下值:
  
MAPI_ONE_OFF_NO_RICH_INFO
  
MAPI_ONE_OFF_UNICODE
  
如果收件人不应接收传输中性封装格式 (TNEF) 中的邮件内容, 则设置 MAPI_ONE_OFF_NO_RICH_INFO 标志。 将 MAPI_SEND_NO_RICH_INFO 传递给[IAddrBook:: CreateOneOff](iaddrbook-createoneoff.md)方法时, 将设置此标志。 
  
如果显示名称和电子邮件地址为 UNICODE 字符串, 则设置 MAPI_ONE_OFF_UNICODE 标志。 将 MAPI_UNICODE 传递给**IAddrBook:: CreateOneOff**时, 将设置此标志。 当 MAPI_UNICODE 标志未传递给**CreateOneOff**时, MAPI 将假定显示名称和电子邮件地址字符串位于工作站的当前 ANSI 字符集中。 在使用不同字符集的平台之间发送的邮件中, ANSI 字符串通常不会很好地工作, 因为代码页未在条目标识符中编码。 为了防止这种潜在的兼容性, 许多地址类型仅限于在多个字符集中通用的那些字符。 但是, 为了确保字符集和平台兼容性, 客户端应使用 Unicode 对其邮件中的字符字符串进行设置。
  
显示名称是一个以 null 结尾的字符串, 对应于收件人的**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性和传递给**IAddrBook:: CreateOneOff**的_lpszName_参数。 如果设置了 MAPI_ONE_OFF_UNICODE 标志, 则字符集为 Unicode; 如果清除, 则设置为 ANSI。 
  
地址类型是以 null 结尾的字符串, 对应于收件人的**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) 属性和传递给**IAddrBook:: CreateOneOff**的_lpszAdrType_参数。 
  
电子邮件地址是一个以 null 结尾的字符串, 对应于收件人的**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) 属性和传递给**IAddrBook:: CreateOneOff**的_lpszAddress_参数。 
  
> [!NOTE]
> 一次性条目标识符结构中没有填充;按上述方式压缩字节, 并且条目标识符长度不应包含超出电子邮件地址的终止 null 字符的任何字节。 
  
手动构造一次性条目标识符的客户端和通讯簿提供程序可能还需要生成**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 和**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 属性的值。 记录键与条目标识符相同。 应按以下顺序将以下字段串联, 以形成搜索关键字:
  
1. 地址类型, 转换为大写字符。
    
2. 冒号 (:)。
    
3. 电子邮件地址, 转换为大写字符。
    
4. 一个终止的 null 字符。
    
生成搜索关键字时, 不应进行字符集转换。
  

