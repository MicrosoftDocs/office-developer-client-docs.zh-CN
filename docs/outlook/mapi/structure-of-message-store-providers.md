---
title: 消息存储提供程序的结构
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 064b2fc1-e690-43e6-95d3-a61438115de5
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 2f78428b8067b7937e9bd2ee36934cc29a16bfb7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778916"
---
# <a name="structure-of-message-store-providers"></a><span data-ttu-id="40139-103">消息存储提供程序的结构</span><span class="sxs-lookup"><span data-stu-id="40139-103">Structure of message store providers</span></span>
  
<span data-ttu-id="40139-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="40139-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="40139-105">消息存储提供程序，在内存中，运行时是[IMSProvider: IUnknown](imsprovideriunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="40139-105">A message store provider, when it is running in memory, is an [IMSProvider : IUnknown](imsprovideriunknown.md) interface.</span></span> <span data-ttu-id="40139-106">**IMSProvider**界面允许客户端应用程序和 MAPI 后台处理程序登录到和移开的邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="40139-106">The **IMSProvider** interface allows client applications and the MAPI spooler to log on to and off of the message store.</span></span> <span data-ttu-id="40139-107">客户端应用程序和 MAPI 后台处理程序用来访问文件夹和邮件存储区中的邮件的接口是[IMSLogon](imslogoniunknown.md)和[IMsgStore](imsgstoreimapiprop.md)接口。</span><span class="sxs-lookup"><span data-stu-id="40139-107">The interfaces that client applications and the MAPI spooler use to access folders and messages in the message store are [IMSLogon](imslogoniunknown.md) and [IMsgStore](imsgstoreimapiprop.md) interfaces.</span></span> <span data-ttu-id="40139-108">消息存储首次登录到时，通常创建这些接口，尽管[MSProviderInit](msproviderinit.md)入口点的邮件存储 DLL 无法创建它们。</span><span class="sxs-lookup"><span data-stu-id="40139-108">These interfaces are typically created when the message store is first logged on to, although the [MSProviderInit](msproviderinit.md) entry point of the message store DLL could also create them.</span></span> 
  
<span data-ttu-id="40139-109">因为**IMSLogon**和**IMsgStore**接口共享一些方法，所以可能更轻松地创建继承自这两种接口的一个类对象。</span><span class="sxs-lookup"><span data-stu-id="40139-109">Because the **IMSLogon** and **IMsgStore** interfaces share some methods, it may be easier to create one class object that inherits from both of these interfaces.</span></span> <span data-ttu-id="40139-110">此外可以在独立的对象，实现这些接口和写入 helper 函数内部为您的 DLL 的实现共享然后可从**IMSLogon**和**IMsgStore**接口中的方法调用的方法。</span><span class="sxs-lookup"><span data-stu-id="40139-110">You can also implement these interfaces in separate objects, and write helper functions internal to your DLL that implement the shared methods that can then be called from the methods in the **IMSLogon** and **IMsgStore** interfaces.</span></span> 
  
<span data-ttu-id="40139-111">下图显示内运行的消息存储对象层次结构的高级大纲。</span><span class="sxs-lookup"><span data-stu-id="40139-111">The following illustration shows a high-level outline of the object hierarchy within a running message store.</span></span>
  
<span data-ttu-id="40139-112">**消息存储对象层次结构**</span><span class="sxs-lookup"><span data-stu-id="40139-112">**Message store object hierarchy**</span></span>
  
<span data-ttu-id="40139-113">![消息存储对象层次结构](media/storeobj.gif "消息存储对象层次结构")</span><span class="sxs-lookup"><span data-stu-id="40139-113">![Message store object hierarchy](media/storeobj.gif "Message store object hierarchy")</span></span>
  
## <a name="see-also"></a><span data-ttu-id="40139-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="40139-114">See also</span></span>

- [<span data-ttu-id="40139-115">开发 MAPI 邮件存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="40139-115">Developing a MAPI Message Store Provider</span></span>](developing-a-mapi-message-store-provider.md)

