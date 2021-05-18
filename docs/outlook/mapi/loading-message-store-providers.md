---
title: 加载邮件存储提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 632d3ef9-43c5-429a-84d7-2dce543d49fb
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: fe3a76fa246cba9447db2f99562670973af183ab
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32307803"
---
# <a name="loading-message-store-providers"></a>加载邮件存储提供程序

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
当客户端应用程序打开邮件存储时，MAPI 将邮件存储提供程序的 DLL 加载到内存中。 在 MAPI 加载 DLL 后，在消息存储提供程序和 MAPI 之间发生一系列非常具体的方法调用。 此方法调用序列使 MAPI 可以获取顶级 [IMSProvider ： IUnknown](imsprovideriunknown.md)、 [IMSLogon ： IUnknown](imslogoniunknown.md)和 [IMsgStore ： IMAPIProp](imsgstoreimapiprop.md) 接口，并允许消息存储提供程序获取 MAPI 支持对象。 在调用序列之后，邮件存储提供程序应已准备好接受来自客户端的登台。 
  
加载消息提供程序 DLL 时调用顺序如下所示：
  
1. 客户端调用 [IMAPISession：：OpenMsgStore](imapisession-openmsgstore.md)。
    
2. 如果消息存储尚未打开，MAPI 将加载存储提供程序的 DLL 并调用 DLL 的 [MSProviderInit](msproviderinit.md) 入口点。 如果消息存储已打开，MAPI 将跳过步骤 2 和 3，然后使用现有的 [IMSProvider ： IUnknown](imsprovideriunknown.md) 接口完成步骤 4。 
    
3. **MSProviderInit** 创建并返回 **IMSProvider** 对象。 
    
4. MAPI 调用 [IMSProvider：：Logon，](imsprovider-logon.md)传递客户端应用程序的邮件存储条目标识符。
    
5. **IMSProvider：：Logon** 创建并返回 [IMSLogon ： IUnknown](imslogoniunknown.md)接口和 [IMsgStore ： IMAPIProp](imsgstoreimapiprop.md)接口，然后在其 [IMAPISupport ： IUnknown](imapisupportiunknown.md)接口上调用 [IUnknown：：AddRef](https://msdn.microsoft.com/library/b4316efd-73d4-4995-b898-8025a316ba63%28Office.15%29.aspx)方法。 如果客户端的邮件存储条目标识符引用已打开的消息存储，则消息存储提供程序可以返回现有的 **IMSLogon** 和 **IMsgStore** 接口，并且不需要在其支持对象上调用 **AddRef。** 
    
6. 如果客户端在登录时未设置 MAPI_NO_MAIL 标志，并且未在步骤 1 中设置 MDB_NO_MAIL，MAPI 会向 MAPI 后台处理程序提供邮件存储的条目标识符，以便 MAPI 后台处理程序可以登录到邮件存储。
    
7. MAPI 将 **IMsgStore** 接口返回到客户端。 
    
8. MAPI 后台处理程序调用 [IMSProvider：：SpoolerLogon](imsprovider-spoolerlogon.md)。
    
9. **IMSProvider：：SpoolerLogon** 返回步骤 5 中的相同 **IMSLogon** 和 **IMsgStore** 接口。 
    
> [!NOTE]
> 如果由于提供的密码不正确而对消息存储提供程序的登录调用失败，并且邮件存储提供程序无法显示询问正确密码的接口，则应该从 **IMSProvider：：Logon** 方法返回 MAPI_E_FAILONEPROVIDER。 这将允许客户端提示用户输入密码，尝试再次登录邮件存储提供程序，而不是使 MAPI 在整个会话期间使提供程序失败。 
  
## <a name="see-also"></a>另请参阅



[开发 MAPI 邮件存储提供程序](developing-a-mapi-message-store-provider.md)

