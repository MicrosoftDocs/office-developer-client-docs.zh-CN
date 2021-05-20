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
  
通讯簿提供程序通过实现 [IABProvider ： IUnknown](iabprovideriunknown.md) 接口的方法支持会话登录和注销。 ** IABProvider ** 接口直接继承自 **IUnknown** 并仅添加其他两种方法：**登录和****关机**。 
  
## <a name="logoff"></a>注销

MAPI 将在每个会话的开头以及将提供程序添加到当前配置文件且客户端支持动态重新配置时调用提供程序的 [IABProvider：：Logon](iabprovider-logon.md) 方法。 当 MAPI 调用 **IABProvider：：Logon** 方法时，通讯簿提供程序将开始其登录过程。 
  
**实现 IABProvider：：Log**
  
1. 初始化 MAPI 传入的所有输出参数指针。 
    
2. 调用支持对象的 **IUnknown：：AddRef** 方法来增加其引用计数。 
    
3. 调用支持对象的 [IMAPISupport：：OpenProfileSection](imapisupport-openprofilesection.md) 方法以打开包含有关提供程序的配置信息的配置文件部分。 如果打算进行更改，请为  _lpUID_ 参数和 MAPI_MODIFY 标志传递 NULL。 
    
4. 调用配置文件节的 [IMAPIProp：：GetProps](imapiprop-getprops.md) 方法来检索提供程序登录所需的属性，例如数据文件或数据库表的名称。 
    
5. 检查属性是否全部可用且有效。 如有必要且允许，显示一个对话框，提示用户对无效或缺失的信息进行更正或添加，并调用配置文件节的 [IMAPIProp：：SetProps](imapiprop-setprops.md) 方法来保存任何更改。 一些应该可用的常见属性包括： 
    
   **PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 
    
   **PR_ENTRYID (** [PidTagEntryId](pidtagentryid-canonical-property.md)) 
    
   **PR_PROVIDER_DISPLAY (** [PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md)) 
    
   **PR_RECORD_KEY (** [PidTagRecordKey)](pidtagrecordkey-canonical-property.md)
    
   > [!NOTE]
   > 不要将 **PR_RESOURCE_FLAGS (** [PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 或 **PR_PROVIDER_DLL_NAME** ([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md)) 。 登录时，这些属性是只读的。 
  
6. 如果一个或多个配置属性不可用，则失败并返回值 MAPI_E_UNCONFIGURED。
    
7. 调用 [IMAPISupport：：SetProviderUID](imapisupport-setprovideruid.md) 注册 [MAPIUID](mapiuid.md)。 你的提供程序可以通过：创建 **MAPIUID：** 
    
   - 调用 [IMAPISupport：：NewUID](imapisupport-newuid.md) 方法。 
    
   - 调用 UUIDGEN.EXE 工具定义提供程序用于包括在其头文件之一中的 GUID。
    
8. 如果需要，通过调用配置文件节的 ** IMAPIProp：：SetProps ** 方法，将新创建的 **MAPIUID** 保存到当前配置文件中。 
    
9. 通过调用其 **IUnknown：：Release 方法释放配置文件** 部分。 
    
10. 实例化新的登录对象，将  _lppABLogon_ 参数的内容设置为此新对象的地址。 
    
由于 MAPI 可以在会话期间多次调用 ** Logon ** 方法，因此，通过能够创建多个登录对象并跟踪创建的每个对象，在实现中支持这种可能性是明智的。 例如，支持 **多个** 登录调用使客户端应用程序的用户可以登录到具有不同标识的会话或使用不同的传递目标。 
  
**会话** 结束时将调用关闭。 MAPI 调用 [IABProvider：：Shutdown](iabprovider-shutdown.md) 方法作为关闭会话所涉及的最后一项任务之一。 MAPI 已释放提供程序的所有登录对象，当提供程序收到此调用时，它可以假定这是它将接收的最后一个调用。 在 **IABProvider：：Shutdown** 的实现中，执行你认为必要的任何最终清理。 例如，如果提供程序调用 **MAPIInitIdle** 以在会话期间使用空闲引擎或尚未释放的任何对象的 **IUnknown：：Release** 方法，则提供程序可能会调用 **MAPIDeinitIdle。** 
  
如果提供程序没有最终清理，其实现可以由一行代码决定： 
  
```cpp
return S_OK;

```


