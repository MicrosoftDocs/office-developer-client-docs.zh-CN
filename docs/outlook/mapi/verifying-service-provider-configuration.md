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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329603"
---
# <a name="verifying-service-provider-configuration"></a>验证服务提供程序配置
  
**适用于**：Outlook 2013 | Outlook 2016 
  
您的登录方法 ([IABProvider:: logon](iabprovider-logon.md)、 [IMSProvider:: logon](imsprovider-logon.md)或[IXPProvider:: TransportLogon](ixpprovider-transportlogon.md)) 必须验证提供程序的配置。 这包括检查完整操作所需的全部属性是否已正确设置。 每个提供程序都需要不同数量的属性;配置取决于提供商以及允许的用户交互程度。 某些服务提供程序在配置文件中保留了所有必需的属性。 

其他服务提供程序在配置文件中保留部分属性集, 并提示用户缺少值。 此外, 其他提供程序根本不会在配置文件中存储属性, 依赖用户提供配置所需的所有信息。
  
### <a name="to-retrieve-properties-stored-in-the-profile"></a>检索存储在配置文件中的属性
  
1. 调用[IMAPISupport:: OpenProfileSection](imapisupport-openprofilesection.md), 并将您的提供程序的[MAPIUID](mapiuid.md)作为输入参数进行传递。 
    
2. 调用配置文件节的[IMAPIProp:: GetProps](imapiprop-getprops.md)或[IMAPIProp:: GetPropList](imapiprop-getproplist.md)方法以检索各个属性或属性列表。 
    
### <a name="to-set-properties-from-user-information"></a>设置用户信息的属性
  
如果 MAPI 未设置阻止显示的标志, 则显示属性表。 以下标志表明无法显示用户界面。
  
|**Flag**|**服务提供程序**|
|:-----|:-----|
|AB_NO_DIALOG  <br/> |通讯簿提供程序  <br/> |
|LOGON_NO_DIALOG  <br/> |传输提供程序  <br/> |
|MDB_NO_DIALOG  <br/> |邮件存储区提供程序  <br/> |
   
如果提供程序未将其所有配置属性存储在配置文件中, 需要用户交互, 并且 MAPI 会将某个对话框禁止显示标记传递给您的登录方法, 则返回 MAPI_E_UNCONFIGURED。 如果未设置对话框隐藏标志, 但用户不提供所有必需的信息, 也会返回此错误。
  
当您的服务提供商将其登录方法与 MAPI_E_UNCONFIGURED 一起失败时, MAPI 会再次调用您的入口点函数。 如果无法通过第二次调用找到信息, 则会话可能会终止, 具体取决于服务提供商的重要性。 
  
下图显示了在服务提供程序登录方法中配置所需的逻辑。 
  
**配置验证流程图**
  
![配置验证流程图](media/amapi_62.gif "配置验证流程图")
  
## <a name="see-also"></a>另请参阅

- [实现服务提供程序登录](implementing-service-provider-logon.md)

