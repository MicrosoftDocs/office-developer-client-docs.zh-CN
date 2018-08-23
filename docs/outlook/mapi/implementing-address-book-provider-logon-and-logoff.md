---
title: 实现通讯簿提供程序登录和注销
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c4a1fb5d-ae23-445b-a6f0-ef430b03fc9a
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: f26e7b7ec607c9714012870d5367a0e775c62f34
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22572100"
---
# <a name="implementing-address-book-provider-logon-and-logoff"></a>实现通讯簿提供程序登录和注销

**适用于**： Outlook 2013 |Outlook 2016 
  
通讯簿提供程序实现的方法通过支持会话登录和注销[IABProvider: IUnknown](iabprovideriunknown.md)接口。 * * IABProvider * * 界面直接从**IUnknown**继承并添加其他只有两个方法：**登录**和**关机**。 
  
## <a name="logoff"></a>注销

MAPI 将调用您的提供商[IABProvider::Logon](iabprovider-logon.md)方法的开头的每个会话，只要您提供程序添加到当前配置文件和客户端支持动态重新配置。 MAPI 调用**IABProvider::Logon**方法时，通讯簿提供程序开始其登录过程。 
  
**若要实现 IABProvider::Log**
  
1. 初始化所有通过 MAPI 传入的输出参数指针。 
    
2. 调用支持对象的**IUnknown::AddRef**方法，以增加引用计数。 
    
3. 调用支持对象的[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)方法以打开配置文件包含有关您的提供商的配置信息部分。 如果想要进行更改，请传递 NULL _lpUID_参数和 MAPI_MODIFY 标志。 
    
4. 调用配置文件部分的[IMAPIProp::GetProps](imapiprop-getprops.md)方法来检索提供程序所需要的登录名，例如数据文件或数据库表的名称的属性。 
    
5. 检查属性所有可用且有效。 如果需要，并且允许，显示一个对话框，提示用户对无效或丢失信息进行更正或添加并调用配置文件部分的[IMAPIProp::SetProps](imapiprop-setprops.md)方法保存任何更改。 一些应该可用的通用属性包括： 
    
   **PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))
    
   **PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))
    
   **PR_PROVIDER_DISPLAY**([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md))
    
   **PR_RECORD_KEY**([PidTagRecordKey](pidtagrecordkey-canonical-property.md))
    
   > [!NOTE]
   > 未设置**PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 或**PR_PROVIDER_DLL_NAME** ([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md))。 在登录时，这些属性是只读的。 
  
6. 如果一个或多个配置属性不可用，失败并返回 MAPI_E_UNCONFIGURED 的值。
    
7. 调用[IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md)注册[MAPIUID](mapiuid.md)。 您的提供商可以创建由**MAPIUID** : 
    
   - 调用[IMAPISupport::NewUID](imapisupport-newuid.md)方法。 
    
   - 调用 UUIDGEN。EXE 工具定义您的提供商使用其标头文件中包含的 GUID。
    
8. 如果需要，保存新创建的**MAPIUID**当前配置文件中通过调用配置文件部分的 * * IMAPIProp::SetProps * * 方法。 
    
9. 通过调用其**IUnknown::Release**方法发布配置文件一节。 
    
10. 实例化一个新的登录对象并将_lppABLogon_参数的内容设置为此新对象的地址。 
    
因为它是可能的 MAPI 调用您 * * 登录 * * 在会话期间几次方法，则最好通过能够创建多个登录对象并跟踪创建每个对象在实现中支持这种可能性。 支持多个**登录**呼叫允许用户客户端应用程序，例如，登录到不同的身份或使用不同的传送目标的会话。 
  
**关闭**时结束会话调用。 MAPI 调用的最后一个任务之一[IABProvider::Shutdown](iabprovider-shutdown.md)方法关闭会话所涉及。 MAPI 已发布的所有提供商的登录对象和，当您的提供商收到此呼叫时，它可以假设这是它将接收的最后一个呼叫。 **IABProvider::Shutdown**的实现中, 执行任何必要的最终清理。 例如，您的提供商可能会调用**MAPIDeinitIdle** ，如果它具有调用**MAPIInitIdle**会话或任何对象，具有尚未必须释放的**IUnknown::Release**方法期间使用的空闲引擎。 
  
如果您的提供不商任何最终清理，其实现的一行代码表进行： 
  
```cpp
return S_OK;

```


