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
  
当客户端应用程序打开邮件存储区时, MAPI 会将邮件存储提供程序的 DLL 加载到内存中。 MAPI 加载 DLL 后, 在邮件存储提供程序和 MAPI 之间发生的方法调用的具体顺序。 此方法调用序列使 MAPI 能够获取顶级[IMSProvider: iunknown](imsprovideriunknown.md)、 [IMSLogon: iunknown](imslogoniunknown.md)和[IMsgStore: IMAPIProp](imsgstoreimapiprop.md)接口, 并允许邮件存储提供程序获取 MAPI 支持对象。 在呼叫序列之后, 邮件存储提供程序应准备好接受来自客户端的登录。 
  
当加载邮件提供程序 DLL 时, 调用顺序如下所示:
  
1. 客户端调用[IMAPISession:: OpenMsgStore](imapisession-openmsgstore.md)。
    
2. 如果邮件存储尚未打开, MAPI 将加载存储提供程序的 DLL, 并调用该 dll 的[MSProviderInit](msproviderinit.md)入口点。 如果邮件存储已打开, MAPI 将跳过步骤2和步骤 3, 然后使用现有的[IMSProvider: IUnknown](imsprovideriunknown.md)接口完成步骤4。 
    
3. **MSProviderInit**创建并返回一个**IMSProvider**对象。 
    
4. MAPI 调用[IMSProvider:: Logon](imsprovider-logon.md), 传递客户端应用程序的邮件存储项标识符。
    
5. **IMSProvider:: Logon**创建并返回[IMSLogon: iunknown](imslogoniunknown.md)接口和[IMsgStore: IMAPIProp](imsgstoreimapiprop.md)接口, 然后在其[AddRef: IUnknown](imapisupportiunknown.md)接口上调用[iunknown:: IMAPISupport](https://msdn.microsoft.com/library/b4316efd-73d4-4995-b898-8025a316ba63%28Office.15%29.aspx)方法。 如果客户端的邮件存储项标识符引用已打开的邮件存储区, 则邮件存储提供程序可以返回现有的**IMSLogon**和**IMsgStore**接口, 而无需对其支持对象调用**AddRef** 。 
    
6. 如果客户端在登录时未设置 MAPI_NO_MAIL 标志, 并且未在第1步中设置 MDB_NO_MAIL, mapi 将向 mapi 后台处理程序提供邮件存储的条目标识符, 以便 mapi 后台处理程序可以登录到邮件存储库。
    
7. MAPI 将**IMsgStore**接口返回给客户端。 
    
8. MAPI 后台处理程序调用[IMSProvider:: SpoolerLogon](imsprovider-spoolerlogon.md)。
    
9. **IMSProvider:: SpoolerLogon**返回步骤5中的相同**IMSLogon**和**IMsgStore**接口。 
    
> [!NOTE]
> 如果由于提供了错误密码而导致对邮件存储提供程序的登录调用失败, 且邮件存储区提供程序无法显示用于请求正确密码的接口, 则应返回**IMSProvider:: logon 中的 MAPI_E_FAILONEPROVIDER**方法。 这将允许客户端提示用户输入密码以再次尝试登录到邮件存储区提供程序, 而不是导致 MAPI 使整个会话的提供程序失败。 
  
## <a name="see-also"></a>另请参阅



[开发 MAPI 邮件存储提供程序](developing-a-mapi-message-store-provider.md)

