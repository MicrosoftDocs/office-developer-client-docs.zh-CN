---
title: 关于注册新域以进行自动配置
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: a7ab8a50-dd30-4ba5-b6d8-e6d1f482e6f1
description: Outlook 提供了一种方法，以指定自动配置的新消息服务域和允许消息服务提供商配置帐户。
ms.openlocfilehash: bf06ff8d145ed6173e3545f784f8b5b7b5f433be
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25388600"
---
# <a name="about-registering-a-new-domain-for-automatic-configuration"></a>关于注册新域以进行自动配置

Outlook 提供了一种方法，以指定自动配置的新消息服务域和允许消息服务提供商配置帐户。
  
在设计时消息服务提供程序，您可以使用在 Windows 注册表中以下项指定新域进行自动配置相应的消息服务提供商： 
  
`HKLM\Software\Microsoft\Office\Outlook\AutoConfigDomains\<domain name>\`
  
在项中，`<domain name>`是自动配置的域。 此域名支持通配符\*开头仅。 下表显示了此项支持的值。 
  
| 值 | 类型 | 说明 |
|:-----|:-----|:-----|
|友好名称  <br/> |REG_SZ  <br/> |向用户显示自动配置过程中的域名。  <br/> |
|服务名称  <br/> |REG_SZ  <br/> |邮件服务中支持此域的 mapisvc.inf 注册。  <br/> |
|安装位置  <br/> |REG_SZ  <br/> |安装邮件服务提供商，如果未安装位置的 URL。  <br/> |
|最低版本  <br/> |REG_DWORD  <br/> |.Dll 消息服务提供程序所需的最低版本。 此值是可选的。  <br/> |
   
Outlook 开始时自动配置的电子邮件帐户，它会检查 Windows 注册表中以便按电子邮件地址指定的域的注册。 如果已在 Windows 注册表中指定的域，则 Outlook 将检查是否在 Mapisvc.inf 注册邮件服务。 除非在 Windows 注册表中已指定，outlook 就无法继续使用自动配置的域。
  
如果未指定的邮件服务当前在 Mapisvc.inf 中, 注册或消息服务提供商已安装但.dll 具有版本早于指定的最小，Outlook 使用指定的友好名称，并提示用户安装提供程序。 如果用户接受，Outlook 将用户重定向到指定的安装位置，以便用户可以安装提供程序。 安装提供程序中 Mapisvc.inf 注册邮件服务。
  
如果在 Mapisvc.inf 当前注册的邮件服务、 服务提供程序.dll 是相应版本，Outlook 使用[IMsgServiceAdmin::CreateMsgService](https://msdn.microsoft.com/library/0135f049-0311-45e5-9685-78597d599a4e%28Office.15%29.aspx)，创建邮件服务，然后将其配置使用[IMsgServiceAdmin::ConfigureMsgService](https://msdn.microsoft.com/library/a08f5905-2585-49ca-abb7-a77f2736f604%28Office.15%29.aspx)。 Outlook 自动配置使用以下三个属性来允许要设置帐户的提供程序： [PidTagAutoConfigurationUserName](https://msdn.microsoft.com/library/05dfa0e2-4ab1-4f57-9009-6a815aca87bd%28Office.15%29.aspx)、 [PidTagAutoConfigurationUserEmail](https://msdn.microsoft.com/library/845140c8-5454-4b47-acec-ab5aff00b768%28Office.15%29.aspx)和[PidTagAutoConfigurationUserPassword](https://msdn.microsoft.com/library/d33e7c45-55d8-4dc1-ade9-605542d87e61%28Office.15%29.aspx).
  
## <a name="see-also"></a>另请参阅

- [MapiSvc.inf 的文件格式](https://msdn.microsoft.com/library/b48eda17-83a8-4dc4-85c8-4ca827d13d25%28Office.15%29.aspx)

