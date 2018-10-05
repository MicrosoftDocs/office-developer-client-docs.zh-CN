---
title: 加载邮件存储区提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 632d3ef9-43c5-429a-84d7-2dce543d49fb
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: fe3a76fa246cba9447db2f99562670973af183ab
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25398393"
---
# <a name="loading-message-store-providers"></a>加载邮件存储区提供程序

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
当客户端应用程序打开的消息存储时，MAPI 将消息存储提供程序的 DLL 加载到内存中。 MAPI 加载 DLL 之后，非常特定的方法调用序列消息存储提供程序和 MAPI 之间。 此方法的调用序列启用 MAPI 获取顶级[IMSProvider: IUnknown](imsprovideriunknown.md)， [IMSLogon: IUnknown](imslogoniunknown.md)，和[IMsgStore: IMAPIProp](imsgstoreimapiprop.md)接口，并允许消息存储提供程序获取 MAPI 支持对象。 后的呼叫顺序的消息存储提供程序应该就可以接受来自客户端登录。 
  
加载 DLL 消息提供程序时的呼叫顺序如下所示：
  
1. 客户端调用[IMAPISession::OpenMsgStore](imapisession-openmsgstore.md)。
    
2. 如果消息存储尚未打开，MAPI 加载的存储提供程序 DLL，并调用 DLL 的[MSProviderInit](msproviderinit.md)入口点。 如果消息存储已经打开，MAPI 跳过步骤 2 和 3，，，然后使用现有[IMSProvider: IUnknown](imsprovideriunknown.md)界面来完成步骤 4。 
    
3. **MSProviderInit**创建并返回一个**IMSProvider**对象。 
    
4. MAPI 调用[IMSProvider::Logon](imsprovider-logon.md)，传递客户端应用程序的消息存储项标识符。
    
5. **IMSProvider::Logon**创建并返回[IMSLogon: IUnknown](imslogoniunknown.md)接口和[IMsgStore: IMAPIProp](imsgstoreimapiprop.md)接口，然后调用上的[IUnknown::AddRef](https://msdn.microsoft.com/library/b4316efd-73d4-4995-b898-8025a316ba63%28Office.15%29.aspx)方法及其[IMAPISupport: IUnknown](imapisupportiunknown.md)接口。 如果客户端的消息存储条目标识符指的是已打开的消息存储，可以返回现有**IMSLogon**和**IMsgStore**接口的消息存储提供程序，并且不需要对其支持的对象调用**AddRef** 。 
    
6. 如果客户端没有设置 MAPI_NO_MAIL 标志时其登录和它未在步骤 1，MAPI 中设置 MDB_NO_MAIL，消息存储的项标识符 MAPI 后台处理程序这样 MAPI 后台处理程序可以登录到的消息存储。
    
7. MAPI 返回到客户端**IMsgStore**接口。 
    
8. MAPI 后台处理程序调用[IMSProvider::SpoolerLogon](imsprovider-spoolerlogon.md)。
    
9. 从步骤 5 中**IMSProvider::SpoolerLogon**返回相同的**IMSLogon**和**IMsgStore**接口。 
    
> [!NOTE]
> 如果邮件登录调用存储提供程序失败，因为提供密码不正确，消息存储提供程序无法显示接口寻求正确的密码，则应返回**IMSProvider::Logon MAPI_E_FAILONEPROVIDER**方法。 这将允许客户端可以提示用户输入密码以尝试登录到而导致 MAPI 整个会话失败提供程序不是再次的消息存储提供程序。 
  
## <a name="see-also"></a>另请参阅



[开发 MAPI 邮件存储区提供程序](developing-a-mapi-message-store-provider.md)

