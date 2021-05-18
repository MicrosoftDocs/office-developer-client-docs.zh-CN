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
# <a name="loading-message-store-providers"></a><span data-ttu-id="b4856-103">加载邮件存储提供程序</span><span class="sxs-lookup"><span data-stu-id="b4856-103">Loading Message Store Providers</span></span>

  
  
<span data-ttu-id="b4856-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b4856-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b4856-105">当客户端应用程序打开邮件存储时，MAPI 将邮件存储提供程序的 DLL 加载到内存中。</span><span class="sxs-lookup"><span data-stu-id="b4856-105">When a client application opens a message store, MAPI loads the message store provider's DLL into memory.</span></span> <span data-ttu-id="b4856-106">在 MAPI 加载 DLL 后，在消息存储提供程序和 MAPI 之间发生一系列非常具体的方法调用。</span><span class="sxs-lookup"><span data-stu-id="b4856-106">After MAPI loads the DLL, a very specific sequence of method calls occurs between the message store provider and MAPI.</span></span> <span data-ttu-id="b4856-107">此方法调用序列使 MAPI 可以获取顶级 [IMSProvider ： IUnknown](imsprovideriunknown.md)、 [IMSLogon ： IUnknown](imslogoniunknown.md)和 [IMsgStore ： IMAPIProp](imsgstoreimapiprop.md) 接口，并允许消息存储提供程序获取 MAPI 支持对象。</span><span class="sxs-lookup"><span data-stu-id="b4856-107">This method call sequence enables MAPI to get top-level [IMSProvider : IUnknown](imsprovideriunknown.md), [IMSLogon : IUnknown](imslogoniunknown.md), and [IMsgStore : IMAPIProp](imsgstoreimapiprop.md) interfaces, and allows the message store provider to get a MAPI support object.</span></span> <span data-ttu-id="b4856-108">在调用序列之后，邮件存储提供程序应已准备好接受来自客户端的登台。</span><span class="sxs-lookup"><span data-stu-id="b4856-108">After the call sequence, the message store provider should be ready to accept logons from clients.</span></span> 
  
<span data-ttu-id="b4856-109">加载消息提供程序 DLL 时调用顺序如下所示：</span><span class="sxs-lookup"><span data-stu-id="b4856-109">The call sequence when a message provider DLL is loaded is as follows:</span></span>
  
1. <span data-ttu-id="b4856-110">客户端调用 [IMAPISession：：OpenMsgStore](imapisession-openmsgstore.md)。</span><span class="sxs-lookup"><span data-stu-id="b4856-110">The client calls [IMAPISession::OpenMsgStore](imapisession-openmsgstore.md).</span></span>
    
2. <span data-ttu-id="b4856-111">如果消息存储尚未打开，MAPI 将加载存储提供程序的 DLL 并调用 DLL 的 [MSProviderInit](msproviderinit.md) 入口点。</span><span class="sxs-lookup"><span data-stu-id="b4856-111">If the message store is not already open, MAPI loads the store provider's DLL and calls the DLL's [MSProviderInit](msproviderinit.md) entry point.</span></span> <span data-ttu-id="b4856-112">如果消息存储已打开，MAPI 将跳过步骤 2 和 3，然后使用现有的 [IMSProvider ： IUnknown](imsprovideriunknown.md) 接口完成步骤 4。</span><span class="sxs-lookup"><span data-stu-id="b4856-112">If the message store is already open, MAPI skips steps 2 and 3, and then uses the existing [IMSProvider : IUnknown](imsprovideriunknown.md) interface to complete step 4.</span></span> 
    
3. <span data-ttu-id="b4856-113">**MSProviderInit** 创建并返回 **IMSProvider** 对象。</span><span class="sxs-lookup"><span data-stu-id="b4856-113">**MSProviderInit** creates and returns an **IMSProvider** object.</span></span> 
    
4. <span data-ttu-id="b4856-114">MAPI 调用 [IMSProvider：：Logon，](imsprovider-logon.md)传递客户端应用程序的邮件存储条目标识符。</span><span class="sxs-lookup"><span data-stu-id="b4856-114">MAPI calls [IMSProvider::Logon](imsprovider-logon.md), passing the client application's message store entry identifier.</span></span>
    
5. <span data-ttu-id="b4856-115">**IMSProvider：：Logon** 创建并返回 [IMSLogon ： IUnknown](imslogoniunknown.md)接口和 [IMsgStore ： IMAPIProp](imsgstoreimapiprop.md)接口，然后在其 [IMAPISupport ： IUnknown](imapisupportiunknown.md)接口上调用 [IUnknown：：AddRef](https://msdn.microsoft.com/library/b4316efd-73d4-4995-b898-8025a316ba63%28Office.15%29.aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="b4856-115">**IMSProvider::Logon** creates and returns an [IMSLogon : IUnknown](imslogoniunknown.md) interface and an [IMsgStore : IMAPIProp](imsgstoreimapiprop.md) interface, and then calls the [IUnknown::AddRef](https://msdn.microsoft.com/library/b4316efd-73d4-4995-b898-8025a316ba63%28Office.15%29.aspx) method on its [IMAPISupport : IUnknown](imapisupportiunknown.md) interface.</span></span> <span data-ttu-id="b4856-116">如果客户端的邮件存储条目标识符引用已打开的消息存储，则消息存储提供程序可以返回现有的 **IMSLogon** 和 **IMsgStore** 接口，并且不需要在其支持对象上调用 **AddRef。**</span><span class="sxs-lookup"><span data-stu-id="b4856-116">If the client's message store entry identifier refers to a message store that is already open, the message store provider can return existing **IMSLogon** and **IMsgStore** interfaces and does not need to call **AddRef** on its support object.</span></span> 
    
6. <span data-ttu-id="b4856-117">如果客户端在登录时未设置 MAPI_NO_MAIL 标志，并且未在步骤 1 中设置 MDB_NO_MAIL，MAPI 会向 MAPI 后台处理程序提供邮件存储的条目标识符，以便 MAPI 后台处理程序可以登录到邮件存储。</span><span class="sxs-lookup"><span data-stu-id="b4856-117">If the client did not set the MAPI_NO_MAIL flag when it logged on and it did not set the MDB_NO_MAIL in step 1, MAPI gives the message store's entry identifier to the MAPI spooler so the MAPI spooler can log on to the message store.</span></span>
    
7. <span data-ttu-id="b4856-118">MAPI 将 **IMsgStore** 接口返回到客户端。</span><span class="sxs-lookup"><span data-stu-id="b4856-118">MAPI returns the **IMsgStore** interface to the client.</span></span> 
    
8. <span data-ttu-id="b4856-119">MAPI 后台处理程序调用 [IMSProvider：：SpoolerLogon](imsprovider-spoolerlogon.md)。</span><span class="sxs-lookup"><span data-stu-id="b4856-119">The MAPI spooler calls [IMSProvider::SpoolerLogon](imsprovider-spoolerlogon.md).</span></span>
    
9. <span data-ttu-id="b4856-120">**IMSProvider：：SpoolerLogon** 返回步骤 5 中的相同 **IMSLogon** 和 **IMsgStore** 接口。</span><span class="sxs-lookup"><span data-stu-id="b4856-120">**IMSProvider::SpoolerLogon** returns the same **IMSLogon** and **IMsgStore** interfaces from step 5.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="b4856-121">如果由于提供的密码不正确而对消息存储提供程序的登录调用失败，并且邮件存储提供程序无法显示询问正确密码的接口，则应该从 **IMSProvider：：Logon** 方法返回 MAPI_E_FAILONEPROVIDER。</span><span class="sxs-lookup"><span data-stu-id="b4856-121">If the logon call to the message store provider fails because an incorrect password was supplied and the message store provider cannot display an interface to ask for the correct password, it should return MAPI_E_FAILONEPROVIDER from the **IMSProvider::Logon** method.</span></span> <span data-ttu-id="b4856-122">这将允许客户端提示用户输入密码，尝试再次登录邮件存储提供程序，而不是使 MAPI 在整个会话期间使提供程序失败。</span><span class="sxs-lookup"><span data-stu-id="b4856-122">This will allow clients to prompt the user for a password to try logging on to the message store provider again instead of causing MAPI to fail the provider for the entire session.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="b4856-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b4856-123">See also</span></span>



[<span data-ttu-id="b4856-124">开发 MAPI 邮件存储提供程序</span><span class="sxs-lookup"><span data-stu-id="b4856-124">Developing a MAPI Message Store Provider</span></span>](developing-a-mapi-message-store-provider.md)

