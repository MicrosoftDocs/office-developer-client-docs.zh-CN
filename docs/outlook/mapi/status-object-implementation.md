---
title: 状态对象实现
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 48fd3e28-c2d2-474d-9487-5e2f08ca7319
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: e019ad8d0063514cd41017b459cc701c45c22a2e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569594"
---
# <a name="status-object-implementation"></a>状态对象实现

**适用于**： Outlook 2013 |Outlook 2016 
  
所有服务提供程序必须实现状态对象，并提供了该属性设置为会话状态表。 在状态表中，具体取决于您控制的资源数可以包括一个或多个行。 传输提供程序，例如，应创建行状态表中管理每个消息队列。 更改时，必须更新相应的状态表格行。 状态对象被实现提供访问状态表中包含的信息，不包含表中的其他信息。
  
### <a name="to-implement-a-status-object"></a>若要实现状态对象

1. 实现登录对象的**OpenStatusEntry**方法。 当客户端想要打开状态对象时，它们会调用[IMAPISession::OpenEntry](imapisession-openentry.md)。 MAPI 履行打开请求通过调用您的提供商**OpenStatusEntry**方法，导致您的提供商，以打开其状态对象并返回到客户端指向其**IMAPIStatus**实现的指针。 在**OpenStatusEntry**实现中，完成以下步骤： 
    
   1. 如果您的登录对象尚未创建状态对象，请执行以下任务：
    
      1. 调用支持对象的[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)方法，以访问提供程序的配置文件一节。 
          
      2. 创建新的状态对象。
          
      3. 存储提供程序的状态对象中的配置文件部分的引用，并调用配置文件部分的[IUnknown::AddRef](http://msdn.microsoft.com/library/b4316efd-73d4-4995-b898-8025a316ba63%28Office.15%29.aspx)方法，以增加引用计数。 
          
      4. 存储提供程序的状态对象中的登录对象的引用，并调用登录对象的**IUnknown::AddRef**方法，以增加引用计数。 
          
      5. 存储提供程序的登录对象中的状态对象的引用。
    
   2. 调用状态对象的**IUnknown::AddRef**方法，以增加引用计数登录对象中。 
    
   3. 将状态对象的**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md)) 属性设置为 MAPI_STATUS。
    
   4. 设置以指向状态的对象，并返回_lppMAPIStatus_输出参数。 
    
   5. 检查_ulFlags_输入的参数。 如果您的提供商支持对其状态对象的读/写访问其设置为 MAPI_MODIFY，返回一个可写对象。 但是，如果您的提供程序不支持对其状态对象的读/写访问，不会失败。 返回一个状态对象，是只读的。 希望接收读/写状态对象的客户端应验证尝试进行任何更改之前已被授予了读/写权限。 
    
2. 设置所需的状态的所有对象和状态表属性。 您在您的状态表格行中包含的属性应为可通过状态对象，通过 MAPI 计算属性除外。 必需的属性，如下所示：
    
   - **PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))
    
   - **PR_PROVIDER_DLL_NAME**([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md))
    
   - **PR_PROVIDER_DISPLAY**([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md))
    
   - **PR_RESOURCE_TYPE**([PidTagResourceType](pidtagresourcetype-canonical-property.md))
    
   - **PR_RESOURCE_METHODS**([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md))
    
   - **PR_RESOURCE_FLAGS**([PidTagResourceFlags](pidtagresourceflags-canonical-property.md))
    
   - **PR_STATUS_CODE**([PidTagStatusCode](pidtagstatuscode-canonical-property.md))
    
3. 实现[IMAPIStatus: IMAPIProp](imapistatusimapiprop.md)适合您的提供商的方法。 根据您的提供商，不需要在**IMAPIStatus**中实现的所有四个方法。 每个提供程序应实现的方法的只读版本[IMAPIProp: IUnknown](imapipropiunknown.md)接口和[IMAPIStatus::ValidateState](imapistatus-validatestate.md)方法。 

   传输提供程序还应实现[IMAPIStatus::FlushQueues](imapistatus-flushqueues.md)，和所有提供程序应支持[IMAPIStatus::SettingsDialog](imapistatus-settingsdialog.md)。 但是，支持[IMAPIStatus::ChangePassword](imapistatus-changepassword.md)是可选的。 仅服务提供程序要求密码，并且想要允许用户以编程方式更改它们需要实现此方法。 对于每个支持的方法， **PR_RESOURCE_METHODS**属性中设置相应的位。 例如，如果仅支持**ValidateState**和**留待**，设置为**PR_RESOURCE_METHODS** : 
    
   `STATUS_VALIDATE_STATE | STATUS_SETTINGS_DIALOG`
    
   客户端应尝试呼叫您状态的对象之前检查**PR_RESOURCE_METHODS**的值。 返回 MAPI_E_NO_SUPPORT 通过以下方式处理对任何您不受支持的方法调用。 
    
4. 若要将您一行或多行添加到状态表的登录过程中调用[IMAPISupport::ModifyStatusRow](imapisupport-modifystatusrow.md) 。 传递包含行的列信息和 0 _ulFlags_参数的属性值数组。 如果会话更高版本中的某个时刻提供商的状态更改和其变得更新列信息所需的**ModifyStatusRow**再次调用设置了 STATUSROW_UPDATE 标志。 
    
有关状态的对象的详细信息，请参阅[MAPI 状态对象](mapi-status-objects.md)。
  
## <a name="see-also"></a>另请参阅

- [MAPI 服务提供商](mapi-service-providers.md)

