---
title: 此版本中弃用 API 元素
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d0a6d182-961c-4496-a3bd-f643612527a5
description: 上次修改时间：2012 年 6 月 25 日
ms.openlocfilehash: abfe734ad8af436f52fc0308d0cd236078bb47df
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436886"
---
# <a name="api-elements-deprecated-in-this-edition"></a>此版本中弃用 API 元素

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
以下 API 元素在 Microsoft Outlook 2013 中已弃Microsoft Outlook 2013。 它们不再受支持，不应在新项目中使用它们。
  
## <a name="deprecation-of-message-and-recipient-options"></a>弃用邮件和收件人选项

由于邮件和收件人选项过时，此版本中弃用以下 API 元素：
  
- **IXPLogon：：RegisterOptions**- MAPI 子系统不再调用此方法来为传输提供程序的邮件和收件人选项建立任何默认值。
    
- **OPTIONDATA** 支持邮件和收件人选项属性的此数据结构已过时。 MAPI 子系统不再调用 **IXPLogon：：RegisterOptions** 来获取传输提供程序支持的特定地址类型的任何邮件或收件人选项。 
    
- **OPTIONCALLBACK** 此函数原型（传输提供程序用于声明回调函数，而用于解析提供程序属性的 MAPI 子系统）已过时。 MAPI 子系统不再调用 **IXPLogon：：RegisterOptions** 或使用传输提供程序返回的任何回调函数。 
    
- **IMAPISession：：MessageOptions** MAPI 客户端和服务提供商不应再调用此方法来显示属性或允许用户设置控制特定邮件和地址类型的属性。 方法始终返回 MAPI_E_NOT_FOUND，这表示没有特定邮件的邮件选项。
    
- **IMAPISession：：QueryDefaultMessageOpt**- MAPI 客户端和服务提供商不应再调用此方法来检索控制特定地址类型的邮件选项的属性。 方法不再返回指向任何属性值数组的指针。
    
- **IAddrBook：：RecipOptions** MAPI 客户端和服务提供商不应再调用此方法来显示属性或允许用户设置用于控制特定地址类型收件人处理的属性。 方法始终返回MAPI_W_ERRORS_RETURNED，这表示没有特定收件人的收件人选项。
    
- **IAddrBook：：QueryDefaultRecipOpt** MAPI 客户端和服务提供商不应再调用此方法来检索控制特定地址类型的收件人选项的属性。 方法不再返回指向任何属性值数组的指针。
    
## <a name="see-also"></a>另请参阅



[Outlook MAPI 引用入门](getting-started-with-the-outlook-mapi-reference.md)

