---
title: 关于注册新域以进行自动配置
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: a7ab8a50-dd30-4ba5-b6d8-e6d1f482e6f1
description: Outlook为自动配置指定新邮件服务域并允许邮件服务提供商配置帐户的方法。
ms.openlocfilehash: bf06ff8d145ed6173e3545f784f8b5b7b5f433be
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316966"
---
# <a name="about-registering-a-new-domain-for-automatic-configuration"></a>关于注册新域以进行自动配置

Outlook为自动配置指定新邮件服务域并允许邮件服务提供商配置帐户的方法。
  
在设计邮件服务提供商时，可以使用 Windows 注册表中的以下注册表项指定由相应的邮件服务提供商自动配置的新域： 
  
`HKLM\Software\Microsoft\Office\Outlook\AutoConfigDomains\<domain name>\`
  
在 键中 `<domain name>` ， 是自动配置的域。 此域名仅在开始时 \* 支持通配符。 下表显示了此键支持的值。 
  
| 值 | 类型 | 说明 |
|:-----|:-----|:-----|
|友好名称  <br/> |REG_SZ  <br/> |在自动配置过程中向用户显示的域名。  <br/> |
|服务名称  <br/> |REG_SZ  <br/> |在支持此域的 mapisvc.inf 中注册的邮件服务。  <br/> |
|安装位置  <br/> |REG_SZ  <br/> |要安装邮件服务提供商的位置的 URL（如果尚未安装）。  <br/> |
|最低版本  <br/> |REG_DWORD  <br/> |邮件服务提供商.dll的最低版本。 该值是可选的。  <br/> |
   
当Outlook自动配置电子邮件帐户时，它会检查Windows注册表中是否注册电子邮件地址指定的域。 如果已在注册表中指定域Windows，Outlook检查邮件服务是否已在 Mapisvc.inf 中注册。 Outlook域的自动配置，除非已在注册表中指定Windows配置。
  
如果指定的邮件服务当前未在 Mapisvc.inf 中注册，或者安装了邮件服务提供商，但 .dll 的版本早于指定的最小值，Outlook 将使用指定的友好名称并提示用户安装提供程序。 如果用户接受，Outlook将用户重定向到指定的安装位置，以便用户可以安装提供程序。 安装提供程序会注册 Mapisvc.inf 中的邮件服务。
  
如果邮件服务当前在 Mapisvc.inf 中注册，并且服务提供商 .dll 是一个合适的版本，Outlook 会使用[IMsgServiceAdmin：：CreateMsgService](https://msdn.microsoft.com/library/0135f049-0311-45e5-9685-78597d599a4e%28Office.15%29.aspx)创建邮件服务，然后使用[IMsgServiceAdmin：：ConfigureMsgService](https://msdn.microsoft.com/library/a08f5905-2585-49ca-abb7-a77f2736f604%28Office.15%29.aspx)对其进行配置。 Outlook自动配置使用下列三个属性允许提供程序设置帐户[：PidTagAutoConfigurationUserName、PidTagAutoConfigurationUserEmail](https://msdn.microsoft.com/library/05dfa0e2-4ab1-4f57-9009-6a815aca87bd%28Office.15%29.aspx)和[PidTagAutoConfigurationUserPassword](https://msdn.microsoft.com/library/d33e7c45-55d8-4dc1-ade9-605542d87e61%28Office.15%29.aspx)。 [](https://msdn.microsoft.com/library/845140c8-5454-4b47-acec-ab5aff00b768%28Office.15%29.aspx)
  
## <a name="see-also"></a>另请参阅

- [MapiSvc.inf 的文件格式](https://msdn.microsoft.com/library/b48eda17-83a8-4dc4-85c8-4ca827d13d25%28Office.15%29.aspx)

