---
title: 邮件存储提供程序的结构
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 064b2fc1-e690-43e6-95d3-a61438115de5
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: eda62a4cd31e0de695d52391a6717e7a0f5ea581
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426420"
---
# <a name="structure-of-message-store-providers"></a><span data-ttu-id="ff4bd-103">邮件存储提供程序的结构</span><span class="sxs-lookup"><span data-stu-id="ff4bd-103">Structure of message store providers</span></span>
  
<span data-ttu-id="ff4bd-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ff4bd-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ff4bd-105">消息存储提供程序在内存中运行时，是 [IMSProvider ： IUnknown](imsprovideriunknown.md) 接口。</span><span class="sxs-lookup"><span data-stu-id="ff4bd-105">A message store provider, when it is running in memory, is an [IMSProvider : IUnknown](imsprovideriunknown.md) interface.</span></span> <span data-ttu-id="ff4bd-106">**IMSProvider** 接口允许客户端应用程序和 MAPI 后台处理程序登录到和注销消息存储。</span><span class="sxs-lookup"><span data-stu-id="ff4bd-106">The **IMSProvider** interface allows client applications and the MAPI spooler to log on to and off of the message store.</span></span> <span data-ttu-id="ff4bd-107">客户端应用程序和 MAPI 后台处理程序用于访问邮件存储中的文件夹和消息的接口是 [IMSLogon](imslogoniunknown.md) 和 [IMsgStore](imsgstoreimapiprop.md) 接口。</span><span class="sxs-lookup"><span data-stu-id="ff4bd-107">The interfaces that client applications and the MAPI spooler use to access folders and messages in the message store are [IMSLogon](imslogoniunknown.md) and [IMsgStore](imsgstoreimapiprop.md) interfaces.</span></span> <span data-ttu-id="ff4bd-108">虽然邮件存储 DLL 的 [MSProviderInit](msproviderinit.md) 入口点也可以创建它们，但是这些接口通常是在邮件存储首次登录时创建的。</span><span class="sxs-lookup"><span data-stu-id="ff4bd-108">These interfaces are typically created when the message store is first logged on to, although the [MSProviderInit](msproviderinit.md) entry point of the message store DLL could also create them.</span></span> 
  
<span data-ttu-id="ff4bd-109">由于 **IMSLogon** 和 **IMsgStore** 接口共享一些方法，因此创建一个继承自这两个接口的类对象可能会更容易。</span><span class="sxs-lookup"><span data-stu-id="ff4bd-109">Because the **IMSLogon** and **IMsgStore** interfaces share some methods, it may be easier to create one class object that inherits from both of these interfaces.</span></span> <span data-ttu-id="ff4bd-110">您还可以在单独的对象中实现这些接口，在 DLL 内部编写帮助程序函数，这些函数实现共享方法，然后可以从 **IMSLogon** 和 **IMsgStore** 接口中的方法调用这些方法。</span><span class="sxs-lookup"><span data-stu-id="ff4bd-110">You can also implement these interfaces in separate objects, and write helper functions internal to your DLL that implement the shared methods that can then be called from the methods in the **IMSLogon** and **IMsgStore** interfaces.</span></span> 
  
<span data-ttu-id="ff4bd-111">下图显示了正在运行的邮件存储中对象层次结构的简要概述。</span><span class="sxs-lookup"><span data-stu-id="ff4bd-111">The following illustration shows a high-level outline of the object hierarchy within a running message store.</span></span>
  
<span data-ttu-id="ff4bd-112">**消息存储对象层次结构**</span><span class="sxs-lookup"><span data-stu-id="ff4bd-112">**Message store object hierarchy**</span></span>
  
<span data-ttu-id="ff4bd-113">![邮件存储对象层次结构](media/storeobj.gif "邮件存储对象层次结构")</span><span class="sxs-lookup"><span data-stu-id="ff4bd-113">![Message store object hierarchy](media/storeobj.gif "Message store object hierarchy")</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ff4bd-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ff4bd-114">See also</span></span>

- [<span data-ttu-id="ff4bd-115">开发 MAPI 邮件存储提供程序</span><span class="sxs-lookup"><span data-stu-id="ff4bd-115">Developing a MAPI Message Store Provider</span></span>](developing-a-mapi-message-store-provider.md)

