---
title: 实现通讯簿提供程序登录和注销
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c4a1fb5d-ae23-445b-a6f0-ef430b03fc9a
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 8d33bccdd01075d692e5a887082ba51ee23bb083
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438734"
---
# <a name="implementing-address-book-provider-logon-and-logoff"></a>实现通讯簿提供程序登录和注销

**适用于**：Outlook 2013 | Outlook 2016 
  
通讯簿提供程序通过实现[IABProvider: IUnknown](iabprovideriunknown.md)接口的方法来支持会话登录和注销。 * * IABProvider * * 接口直接继承自**IUnknown** , 并只添加两个其他方法: **Logon** and **Shutdown**。 
  
## <a name="logoff"></a>注销

MAPI 将在每个会话开始时调用提供程序的[IABProvider:: Logon](iabprovider-logon.md)方法, 只要向当前配置文件添加提供程序, 并且客户端支持动态重新配置。 当 MAPI 调用**IABProvider:: Logon**方法时, 您的通讯簿提供程序将启动其登录过程。 
  
**实现 IABProvider:: Log**
  
1. 初始化 MAPI 中传递的所有输出参数指针。 
    
2. 调用支持对象的**IUnknown:: AddRef**方法以增加其引用计数。 
    
3. 调用支持对象的[IMAPISupport:: OpenProfileSection](imapisupport-openprofilesection.md)方法, 打开包含有关提供程序的配置信息的配置文件部分。 如果要进行更改, 请为_lpUID_参数和 MAPI_MODIFY 标志传递 NULL。 
    
4. 调用 profile 节的[IMAPIProp:: GetProps](imapiprop-getprops.md)方法以检索提供程序登录所需的属性, 例如数据文件或数据库表的名称。 
    
5. 检查属性是否全部可用和有效。 如果需要并允许, 显示一个对话框, 提示用户对无效或丢失的信息进行更正或添加, 并调用 profile 节的[IMAPIProp:: SetProps](imapiprop-setprops.md)方法以保存所有更改。 应使用的一些常见属性包括: 
    
   **PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))
    
   **PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))
    
   **PR_PROVIDER_DISPLAY**([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md))
    
   **PR_RECORD_KEY**([PidTagRecordKey](pidtagrecordkey-canonical-property.md))
    
   > [!NOTE]
   > 请勿设置**PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 或**PR_PROVIDER_DLL_NAME** ([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md))。 在登录时, 这些属性是只读的。 
  
6. 如果一个或多个配置属性不可用, 将失败并返回值 MAPI_E_UNCONFIGURED。
    
7. 调用[IMAPISupport:: SetProviderUID](imapisupport-setprovideruid.md)以注册[MAPIUID](mapiuid.md)。 提供程序可以通过以下方式创建**MAPIUID** : 
    
   - 调用[IMAPISupport:: NewUID](imapisupport-newuid.md)方法。 
    
   - 调用 UUIDGEN。EXE 工具来定义您的提供程序用来包含在其中一个头文件中的 GUID。
    
8. 如果需要, 通过调用配置文件节的 * * IMAPIProp:: SetProps * * 方法, 在当前配置文件中保存新创建的**MAPIUID** 。 
    
9. 通过调用其**IUnknown:: Release**方法来释放配置文件部分。 
    
10. 实例化新的登录对象, 并将_lppABLogon_参数的内容设置为此新对象的地址。 
    
由于 MAPI 可以在会话期间多次调用您的 * * 登录 * * 方法, 因此最好在实现过程中支持这种可能性, 这是为了能够创建多个登录对象并跟踪所创建的每个对象。 如果支持多个**登录**调用, 则客户端应用程序的用户可以使用不同的标识登录会话或使用不同的传递目标。 
  
会话结束时调用**Shutdown** 。 MAPI 将您的[IABProvider:: Shutdown](iabprovider-shutdown.md)方法作为上次关闭会话所涉及的最后一项任务调用。 MAPI 已释放了您的所有提供程序的登录对象, 当提供程序收到此呼叫时, 它可以假定这是最后一次将接收的呼叫。 在 IABProvider 的实现 **:: Shutdown**中, 执行您认为必要的任何最终清理。 例如, 如果您的提供程序调用**MAPIInitIdle**在尚未发布的任何对象的会话期间或**IUnknown:: Release**方法中使用空闲引擎, 则您的提供程序可能会调用**MAPIDeinitIdle** 。 
  
如果提供程序没有最终清除, 则其实现可以由单行代码组成: 
  
```cpp
return S_OK;

```


