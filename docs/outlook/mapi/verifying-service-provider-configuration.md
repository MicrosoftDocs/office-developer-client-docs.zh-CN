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
ms.openlocfilehash: 381e2c9ec84811b69d666017a568e7b9cca21755
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418846"
---
# <a name="verifying-service-provider-configuration"></a>验证服务提供程序配置
  
**适用于**：Outlook 2013 | Outlook 2016 
  
您的登录 ([IABProvider：：Logon、IMSProvider：：Logon](iabprovider-logon.md)或[IXPProvider：：TransportLogon](ixpprovider-transportlogon.md)) 必须验证提供程序的配置。 [](imsprovider-logon.md) 这包括检查完整操作所需的所有属性是否设置正确。 每个提供程序都需要不同数量的属性;配置取决于你的提供程序以及你允许的用户交互程度。 某些服务提供商在配置文件中保留所有必需的属性。 

其他服务提供商在配置文件中保留部分属性集，并提示用户输入缺失值。 此外，其他提供程序完全不会在配置文件中存储属性，而依赖用户提供配置所需的全部信息。
  
### <a name="to-retrieve-properties-stored-in-the-profile"></a>检索配置文件中存储的属性
  
1. 调用 [IMAPISupport：：OpenProfileSection](imapisupport-openprofilesection.md)，将提供程序的 [MAPIUID](mapiuid.md) 作为输入参数传递。 
    
2. 调用配置文件节的 [IMAPIProp：：GetProps](imapiprop-getprops.md) 或 [IMAPIProp：：GetPropList](imapiprop-getproplist.md) 方法来检索单个属性或属性列表。 
    
### <a name="to-set-properties-from-user-information"></a>从用户信息设置属性
  
显示属性表，如果 MAPI 尚未设置禁止显示的标志。 以下标志指示无法显示用户界面。
  
|**Flag**|**服务提供程序**|
|:-----|:-----|
|AB_NO_DIALOG  <br/> |通讯簿提供程序  <br/> |
|LOGON_NO_DIALOG  <br/> |传输提供程序  <br/> |
|MDB_NO_DIALOG  <br/> |邮件存储提供程序  <br/> |
   
如果你的提供程序未在配置文件中存储其所有配置属性，因此需要用户交互，并且 MAPI 将其中一个对话框抑制标志传递给你的登录方法，则返回MAPI_E_UNCONFIGURED。 此外，在未设置对话框抑制标志，但用户未提供所有所需信息时，也返回此错误。
  
当服务提供程序在其登录方法失败时MAPI_E_UNCONFIGURED MAPI 将再次调用入口点函数。 如果无法通过第二次调用找到该信息，则会话可能会终止，具体取决于您的服务提供商非常重要。 
  
下图显示了在服务提供程序登录方法中配置所需的逻辑。 
  
**配置验证流程图**
  
![配置验证流程图](media/amapi_62.gif "配置验证流程图")
  
## <a name="see-also"></a>另请参阅

- [实现服务提供程序登录](implementing-service-provider-logon.md)

