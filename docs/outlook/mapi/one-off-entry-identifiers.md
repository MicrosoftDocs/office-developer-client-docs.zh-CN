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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411041"
---
# <a name="one-off-entry-identifiers"></a>一次性条目标识符
  
**适用于**：Outlook 2013 | Outlook 2016 
  
一次输入标识符由 MAPI 在 **IAddrBook：：CreateOneOff** 方法中创建，由无法访问 MAPI 子系统的组件（如网关组件）创建。 有关详细信息，请参阅 [IAddrBook：：CreateOneOff](iaddrbook-createoneoff.md)。 下图显示了一次输入标识符的格式。
  
**一次性条目标识符格式**
  
![一次使用条目标识符格式](media/amapi_69.gif "一次使用条目标识符格式")
  
第一个字段是一个特殊的 [MAPIUID](mapiuid.md) 结构，用于将条目标识符标识为表示自定义收件人。 此 **MAPIUID** 结构必须设置为常量 MAPI_ONE_OFF_UID。 MAPI_ONE_OFF_UID在头文件 MAPIDEFS.H 中定义。 
  
版本和标志字段是按 Intel 字节顺序表示的 16 位单词。 版本字段必须设置为零。 可以将 flags 字段设置为以下值：
  
MAPI_ONE_OFF_NO_RICH_INFO
  
MAPI_ONE_OFF_UNICODE
  
如果MAPI_ONE_OFF_NO_RICH_INFO TNEF 策略中不应接收传输中性封装格式的邮件内容， (设置) 。 此标志在将 MAPI_SEND_NO_RICH_INFO [IAddrBook：：CreateOneOff](iaddrbook-createoneoff.md) 方法时设置。 
  
如果MAPI_ONE_OFF_UNICODE和电子邮件地址是 Unicode 字符串显示名称，则设置此参数标记。 此标志在将MAPI_UNICODE **IAddrBook：：CreateOneOff** 时设置。 当 MAPI_UNICODE 标志未传递到 **CreateOneOff** 时，MAPI 假定 显示名称 和电子邮件地址字符串位于工作站的当前 ANSI 字符集。 ANSI 字符串通常对使用不同字符集的平台之间发送的消息不起作用，因为代码页未在条目标识符中编码。 若要防止这种潜在的不兼容，许多地址类型仅限于在多个字符集之间通用的那些字符。 但是，为了确保字符集和平台兼容性，客户端应针对消息中的字符串使用 Unicode。
  
the 显示名称 is a null-terminated string that corresponds to the recipient's **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property and to the  _lpszName_ parameter passed to **IAddrBook：：CreateOneOff**. 如果设置了字符集标志，则字符集MAPI_ONE_OFF_UNICODE Unicode;如果字符集是清除标记，则字符集为 ANSI。 
  
地址类型是一个以 null 结尾的字符串，对应于收件人的 **PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) 属性和传递到 **IAddrBook：：CreateOneOff** 的 _lpszAdrType_ 参数。 
  
电子邮件地址是一个以 null 结尾的字符串，对应于收件人的 **PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) 属性和传递到 **IAddrBook：：CreateOneOff**_的 lpszAddress_ 参数。 
  
> [!NOTE]
> 一次项标识符结构中没有填充;字节的打包方式与上述完全相同，条目标识符长度不应包含电子邮件地址的终止 null 字符之外的任何字节。 
  
手动构造一次条目标识符的客户端和通讯簿提供程序可能还需要为 **PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 和 **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 属性生成值。 记录键与条目标识符相同。 搜索键应按以下顺序连接以下字段来形成：
  
1. 转换为大写字符的地址类型。
    
2. 冒号 (：) 。
    
3. 转换为大写字符的电子邮件地址。
    
4. 终止 null 字符。
    
生成搜索键时，无需执行字符集转换。
  

