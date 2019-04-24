---
title: 此版本中弃用的 API 元素
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d0a6d182-961c-4496-a3bd-f643612527a5
description: 上次修改时间：2012 年 6 月 25 日
ms.openlocfilehash: abfe734ad8af436f52fc0308d0cd236078bb47df
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32318204"
---
# <a name="api-elements-deprecated-in-this-edition"></a>此版本中弃用的 API 元素

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
以下 API 元素在 Microsoft Outlook 2013 中已弃用。 它们不再受支持, 不应在新项目中使用它们。
  
## <a name="deprecation-of-message-and-recipient-options"></a>邮件和收件人选项的弃用

由于过时的邮件和收件人选项, 此版本中弃用了以下 API 元素:
  
- **IXPLogon:: RegisterOptions**— MAPI 子系统不再会调用此方法来为传输提供程序建立邮件和收件人选项的任何默认值。
    
- **OPTIONDATA**—支持邮件和收件人选项的属性的此数据结构已过时。 MAPI 子系统不再调用**IXPLogon:: RegisterOptions**以获取传输提供程序为特定地址类型支持的任何邮件或收件人选项。 
    
- **OPTIONCALLBACK**—此函数原型, 它是一个用于声明回调函数的传输提供程序, 后者又是用于解析提供程序属性的 MAPI 子系统已过时。 MAPI 子系统不再调用**IXPLogon:: RegisterOptions**或使用传输提供程序返回的任何回调函数。 
    
- **IMAPISession:: MessageOptions**-MAPI 客户端和服务提供程序不应再调用此方法来显示属性, 或允许用户设置控制特定邮件和地址类型的属性。 该方法始终返回 MAPI_E_NOT_FOUND, 指示没有适用于特定邮件的任何邮件选项。
    
- **IMAPISession:: QueryDefaultMessageOpt**-MAPI 客户端和服务提供程序不应再调用此方法来检索控制特定地址类型的邮件选项的属性。 方法不再返回指向任何属性值数组的指针。
    
- **IAddrBook:: RecipOptions**-MAPI 客户端和服务提供程序不应再调用此方法来显示属性, 或允许用户设置控制特定地址类型的收件人处理的属性。 该方法始终返回 MAPI_W_ERRORS_RETURNED, 表示特定收件人没有收件人选项。
    
- **IAddrBook:: QueryDefaultRecipOpt**-MAPI 客户端和服务提供程序不应再调用此方法来检索控制特定地址类型的收件人选项的属性。 方法不再返回指向任何属性值数组的指针。
    
## <a name="see-also"></a>另请参阅



[Outlook MAPI 引用入门](getting-started-with-the-outlook-mapi-reference.md)

