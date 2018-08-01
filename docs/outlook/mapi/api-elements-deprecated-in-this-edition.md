---
title: 在此版本中弃用的 API 元素
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d0a6d182-961c-4496-a3bd-f643612527a5
description: 上次修改时间： 2012 年 6 月 25 日
ms.openlocfilehash: c70e89efba585183d2019bbda49102ecd14b9e20
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774545"
---
# <a name="api-elements-deprecated-in-this-edition"></a>在此版本中弃用的 API 元素

  
  
**适用于**： Outlook 
  
Microsoft Outlook 2013 中弃用以下 API 元素。 不再受支持和不应新项目中使用它们。
  
## <a name="deprecation-of-message-and-recipient-options"></a>Deprecation 邮件和收件人选项

以下 API 元素已弃用此版本中，因为已过时邮件和收件人的选项：
  
- **IXPLogon::RegisterOptions**— MAPI 子系统不能再调用此方法来建立传输提供程序的邮件和收件人选项的任何默认值。
    
- **OPTIONDATA**— 此支持邮件和收件人选项属性的数据结构已过时。 MAPI 子系统不能再调用**IXPLogon::RegisterOptions**获取的任何消息或传输提供程序支持的特定地址类型的收件人选项。 
    
- **OPTIONCALLBACK**-此函数原型，其传输提供程序用于反过来，声明的回调函数和，用于解析提供程序的属性的 MAPI 子系统已过时。 MAPI 子系统不能再调用**IXPLogon::RegisterOptions**或使用由传输提供程序返回任何回调函数。 
    
- **IMAPISession::MessageOptions**— MAPI 客户端与服务提供程序应不再调用此方法来显示属性，或允许用户设置控制特定的邮件和地址类型的属性。 该方法将始终返回 MAPI_E_NOT_FOUND，这表明没有为特定邮件的邮件选项。
    
- **IMAPISession::QueryDefaultMessageOpt**— MAPI 客户端与服务提供程序应不再调用此方法来检索控制消息选项的特定地址类型的属性。 方法无法再到任何属性值的数组返回一个指针。
    
- **IAddrBook::RecipOptions**— MAPI 客户端与服务提供程序应不再调用此方法来显示属性，或允许用户设置该控件处理的特定地址类型的收件人的属性。 该方法将始终返回 MAPI_W_ERRORS_RETURNED，这表明没有特定收件人的收件人的选项。
    
- **IAddrBook::QueryDefaultRecipOpt**— MAPI 客户端与服务提供程序应不再调用此方法来检索控制收件人选项的特定地址类型的属性。 方法无法再到任何属性值的数组返回一个指针。
    
## <a name="see-also"></a>另请参阅



[Outlook MAPI 引用入门](getting-started-with-the-outlook-mapi-reference.md)

