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
  
所有服务提供程序都必须实现 status 对象并将其提供给会话状态表中的属性。 可以在状态表中包含一个或多个行, 具体取决于所控制的资源数量。 例如, 传输提供程序应在状态表中为其管理的每个邮件队列创建一行。 发生更改时, 必须更新相应的状态表行。 通过实现 status 对象, 可提供对状态表中包含的信息的访问权限以及表中未包含的其他信息。
  
### <a name="to-implement-a-status-object"></a>实现 status 对象

1. 实现您的登录对象的**OpenStatusEntry**方法。 当客户端想要打开状态对象时, 他们会调用[IMAPISession:: OpenEntry](imapisession-openentry.md)。 MAPI 通过调用提供程序的**OpenStatusEntry**方法来实现打开请求, 从而使提供程序打开其状态对象并返回到客户端的**IMAPIStatus**实现的指针。 在您的**OpenStatusEntry**实现中, 请完成以下步骤: 
    
   1. 如果您的登录对象尚未创建 status 对象, 请执行以下任务:
    
      1. 调用支持对象的[IMAPISupport:: OpenProfileSection](imapisupport-openprofilesection.md)方法以访问提供程序的配置文件部分。 
          
      2. 创建新的 status 对象。
          
      3. 在提供程序的 status 对象中存储对 profile 节的引用, 并调用配置文件节的[IUnknown:: AddRef](https://msdn.microsoft.com/library/b4316efd-73d4-4995-b898-8025a316ba63%28Office.15%29.aspx)方法以增加其引用计数。 
          
      4. 在提供程序的 status 对象中存储对 logon 对象的引用, 并调用登录对象的**IUnknown:: AddRef**方法以增加其引用计数。 
          
      5. 在提供程序的登录对象中存储对 status 对象的引用。
    
   2. 调用 status 对象的**IUnknown:: AddRef**方法以在 logon 对象中增加其引用计数。 
    
   3. 将 status 对象的**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md)) 属性设置为 MAPI_STATUS。
    
   4. 将_lppMAPIStatus_输出参数设置为指向 status 对象, 并返回。 
    
   5. 检查_ulFlags_输入参数。 如果将其设置为 MAPI_MODIFY, 并且您的提供程序支持对其状态对象的读/写访问权限, 则返回可写对象。 但是, 如果提供程序不支持对其状态对象进行读/写访问, 则不要失败。 返回只读的状态对象。 预期接收读/写状态对象的客户端应先验证是否已授予读/写权限, 然后再尝试进行任何更改。 
    
2. 设置所有必需的状态对象和状态表属性。 您的状态表行中包含的属性应通过 status 对象可用, 但 MAPI 计算的属性除外。 必需属性如下所示:
    
   - **PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))
    
   - **PR_PROVIDER_DLL_NAME**([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md))
    
   - **PR_PROVIDER_DISPLAY**([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md))
    
   - **PR_RESOURCE_TYPE**([PidTagResourceType](pidtagresourcetype-canonical-property.md))
    
   - **PR_RESOURCE_METHODS**([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md))
    
   - **PR_RESOURCE_FLAGS**([PidTagResourceFlags](pidtagresourceflags-canonical-property.md))
    
   - **PR_STATUS_CODE**([PidTagStatusCode](pidtagstatuscode-canonical-property.md))
    
3. 实现适用于您的提供程序的[IMAPIStatus: IMAPIProp](imapistatusimapiprop.md)方法。 根据提供程序的不同, 您无需实现**IMAPIStatus**中的所有四种方法。 每个提供程序都应实现只读版本的[IMAPIProp: IUnknown](imapipropiunknown.md)接口和[IMAPIStatus:: ValidateState](imapistatus-validatestate.md)方法的方法。 

   传输提供程序还应实现[IMAPIStatus:: FlushQueues](imapistatus-flushqueues.md), 并且所有提供程序都应支持[IMAPIStatus:: SettingsDialog](imapistatus-settingsdialog.md)。 但是, 对[IMAPIStatus:: ChangePassword](imapistatus-changepassword.md)的支持是可选的。 只有需要密码的服务提供程序, 并希望允许用户以编程方式更改它们时, 才需要实现此方法。 对于您支持的每个方法, 在**PR_RESOURCE_METHODS**属性中设置相应的位。 例如, 如果仅支持**ValidateState**和**SettingsDialog** , 请将**PR_RESOURCE_METHODS**设置为以下内容: 
    
   `STATUS_VALIDATE_STATE | STATUS_SETTINGS_DIALOG`
    
   客户端应该先检查**PR_RESOURCE_METHODS**的值, 然后再尝试调用 status 对象。 通过返回 MAPI_E_NO_SUPPORT 处理对任何不受支持的方法的调用。 
    
4. 在登录过程中调用[IMAPISupport:: ModifyStatusRow](imapisupport-modifystatusrow.md)以将您的行或行添加到状态表中。 传递包含行的列信息的属性值数组和_ulFlags_参数的值为0。 如果在会话后面的某一点, 提供程序的状态发生更改, 并且需要更新列信息, 请在设置 STATUSROW_UPDATE 标志后再次调用**ModifyStatusRow** 。 
    
有关 status 对象的详细信息, 请参阅[MAPI 状态对象](mapi-status-objects.md)。
  
## <a name="see-also"></a>另请参阅

- [MAPI 服务提供程序](mapi-service-providers.md)

