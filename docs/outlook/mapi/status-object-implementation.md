---
title: 状态对象实现
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 48fd3e28-c2d2-474d-9487-5e2f08ca7319
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: e97efb70716ffbd7fa98f980ce8520cfcb988532
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32336335"
---
# <a name="status-object-implementation"></a>状态对象实现

**适用于**：Outlook 2013 | Outlook 2016 
  
所有服务提供程序都必须实现状态对象，并且将该对象中的属性提供至会话状态表。 您可以在状态表中包括一行或多行，具体取决于您控制的资源数。 例如，传输提供程序应在状态表中为它管理的每个邮件队列创建一行。 发生更改时，必须更新相应的状态表行。 实现 Status 对象可提供对状态表中包含的信息和表中未包含的其他信息的访问。
  
### <a name="to-implement-a-status-object"></a>实现状态对象

1. 实现登录对象的 **OpenStatusEntry** 方法。 当客户端想要打开状态对象时，它们调用 [IMAPISession：：OpenEntry](imapisession-openentry.md)。 MAPI 通过调用提供程序的 **OpenStatusEntry** 方法实现打开的请求，从而导致提供程序打开其状态对象，并返回到客户端一个指向 **其 IMAPIStatus** 实现的指针。 在 **OpenStatusEntry** 实现中，完成以下步骤： 
    
   1. 如果登录对象尚未创建状态对象，请执行以下任务：
    
      1. 调用支持对象的 [IMAPISupport：：OpenProfileSection](imapisupport-openprofilesection.md) 方法以访问提供程序的配置文件部分。 
          
      2. 创建新的状态对象。
          
      3. 在提供程序的状态对象中存储对配置文件节的引用，并调用配置文件节的 [IUnknown：：AddRef](https://msdn.microsoft.com/library/b4316efd-73d4-4995-b898-8025a316ba63%28Office.15%29.aspx) 方法来增加其引用计数。 
          
      4. 在提供程序的状态对象中存储对登录对象的引用，并调用登录对象的 **IUnknown：：AddRef** 方法来增加其引用计数。 
          
      5. 在提供程序的登录对象中存储对 status 对象的引用。
    
   2. 调用 status 对象的 **IUnknown：：AddRef** 方法，以在登录对象中增加其引用计数。 
    
   3. 将 status 对象的PR_OBJECT_TYPE ([PidTagObjectType](pidtagobjecttype-canonical-property.md)) 设置为 MAPI_STATUS。
    
   4. 将  _lppMAPIStatus_ 输出参数设置为指向 status 对象并返回。 
    
   5. 检查  _ulFlags_ 输入参数。 如果设置为"MAPI_MODIFY提供程序支持对状态对象的读/写访问，则返回一个可写对象。 但是，如果您的提供程序不支持对 status 对象的读/写访问，请不要失败。 返回一个只读状态对象。 预期接收读/写状态对象的客户端应在尝试进行更改之前验证已授予读/写权限。 
    
2. 设置所有必需的状态对象和状态表属性。 状态表行中包括的属性应该可以通过状态对象使用，MAPI 计算的属性除外。 所需属性如下所示：
    
   - **PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 
    
   - **PR_PROVIDER_DLL_NAME (** [PidTagProviderDllName](pidtagproviderdllname-canonical-property.md)) 
    
   - **PR_PROVIDER_DISPLAY (** [PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md)) 
    
   - **PR_RESOURCE_TYPE (** [PidTagResourceType](pidtagresourcetype-canonical-property.md)) 
    
   - **PR_RESOURCE_METHODS (** [PidTagResourceMethods)](pidtagresourcemethods-canonical-property.md)
    
   - **PR_RESOURCE_FLAGS (** [PidTagResourceFlags)](pidtagresourceflags-canonical-property.md)
    
   - **PR_STATUS_CODE (** [PidTagStatusCode](pidtagstatuscode-canonical-property.md)) 
    
3. 实现适用于你的提供程序的 [IMAPIStatus ： IMAPIProp](imapistatusimapiprop.md) 方法。 根据你的提供程序，你无需在 **IMAPIStatus** 中实现所有四种方法。 每个提供程序都应实现 [IMAPIProp ： IUnknown](imapipropiunknown.md) 接口和 [IMAPIStatus：：ValidateState](imapistatus-validatestate.md) 方法方法的只读版本。 

   传输提供程序还应实现 [IMAPIStatus：：FlushQueues](imapistatus-flushqueues.md)，并且所有提供程序都应支持 [IMAPIStatus：：SettingsDialog](imapistatus-settingsdialog.md)。 但是，对 [IMAPIStatus：：ChangePassword](imapistatus-changepassword.md) 的支持是可选的。 只有需要密码并且希望允许用户以编程方式更改密码的服务提供商才需要实现此方法。 对于您支持的每种方法，在 PR_RESOURCE_METHODS 属性 **中** 设置相应的位。 例如，如果仅支持 **ValidateState** 和 **SettingsDialog，PR_RESOURCE_METHODS****设置为：** 
    
   `STATUS_VALIDATE_STATE | STATUS_SETTINGS_DIALOG`
    
   客户端应先检查PR_RESOURCE_METHODS，然后再尝试调用状态对象。 通过返回任何不受支持的方法来处理MAPI_E_NO_SUPPORT。 
    
4. 在 [登录期间调用 IMAPISupport：：ModifyStatusRow](imapisupport-modifystatusrow.md) 以将一行或多行添加到状态表中。 传递一个属性值数组，其中包含行的列信息  _，ulFlags_ 参数的列信息为 0。 如果稍后在会话中提供程序的状态发生更改，并且有必要更新列信息，请再次调用 **ModifyStatusRow，** 并设置 STATUSROW_UPDATE标记。 
    
有关状态对象的信息，请参阅 [MAPI Status Objects](mapi-status-objects.md)。
  
## <a name="see-also"></a>另请参阅

- [MAPI 服务提供程序](mapi-service-providers.md)

