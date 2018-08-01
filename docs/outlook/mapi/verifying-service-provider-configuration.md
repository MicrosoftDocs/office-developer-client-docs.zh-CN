---
title: 验证服务提供程序配置
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: dc23dc61-7b51-43ab-a184-ce0bdac91d03
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 047a3b99b2d615984252071a1264521a4b2240f8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779084"
---
# <a name="verifying-service-provider-configuration"></a>验证服务提供程序配置
  
**适用于**： Outlook 
  
您的登录方法 （[IABProvider::Logon](iabprovider-logon.md)、 [IMSProvider::Logon](imsprovider-logon.md)或[IXPProvider::TransportLogon](ixpprovider-transportlogon.md)） 必须验证提供程序的配置。 此步骤需要检查正确设置的所有属性所需的完整的操作。 每个提供程序需要大量不同的属性。配置取决于您的提供商和允许的用户交互程度。 某些服务提供程序将保留所有必要的属性配置文件中。 

其他服务提供程序配置文件中保留一组部分属性，并提示用户输入缺少的值。 仍其他提供程序不存储属性配置文件中，所有依赖于用户提供所有所需的配置信息。
  
### <a name="to-retrieve-properties-stored-in-the-profile"></a>若要检索存储在配置文件属性
  
1. 调用[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)，将您的提供商[MAPIUID](mapiuid.md)作为输入参数传递。 
    
2. 调用配置文件部分的[IMAPIProp::GetProps](imapiprop-getprops.md)或[IMAPIProp::GetPropList](imapiprop-getproplist.md)方法来检索单个属性或属性列表。 
    
### <a name="to-set-properties-from-user-information"></a>若要从用户信息设置属性
  
如果 MAPI 还没有设置禁止显示一个标志，显示属性表、。 以下标志指示无法看到一个用户界面。
  
|**Flag**|**服务提供商**|
|:-----|:-----|
|AB_NO_DIALOG  <br/> |通讯簿提供程序  <br/> |
|LOGON_NO_DIALOG  <br/> |传输提供程序  <br/> |
|MDB_NO_DIALOG  <br/> |消息存储提供程序  <br/> |
   
如果您的提供商不会存储其配置属性的所有配置文件中, 需要用户交互，并 MAPI 将将其中一个对话框中禁止显示标志传递给 logon 方法，则返回 MAPI_E_UNCONFIGURED。 未设置对话框禁止显示标志，但用户不会提供所有所需的信息时，还返回此错误。
  
服务提供商失败时其登录方法与 MAPI_E_UNCONFIGURED，MAPI 再次调用您入口点函数。 如果信息不能位于与第二个呼叫，可能终止会话，具体取决于是如何重要服务提供商。 
  
下图显示了您的服务提供登录方法中的配置所需的逻辑。 
  
**配置验证流程图**
  
![配置验证流程图](media/amapi_62.gif "配置验证流程图")
  
## <a name="see-also"></a>另请参阅

- [实现服务提供程序登录](implementing-service-provider-logon.md)

