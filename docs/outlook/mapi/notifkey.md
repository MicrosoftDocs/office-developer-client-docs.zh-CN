---
title: NOTIFKEY
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.NOTIFKEY
api_type:
- COM
ms.assetid: 031b7e18-59b2-445c-a747-348fda92f458
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 36b8381e2bf98f5ddcb88a54b56f2b5c91b3b668
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22572597"
---
# <a name="notifkey"></a><span data-ttu-id="362b4-103">NOTIFKEY</span><span class="sxs-lookup"><span data-stu-id="362b4-103">NOTIFKEY</span></span>

  
  
<span data-ttu-id="362b4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="362b4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="362b4-105">唯一标识通知接收器、 advise 源和 MAPI 之间的连接。</span><span class="sxs-lookup"><span data-stu-id="362b4-105">Uniquely identifies a connection between an advise sink, an advise source, and MAPI.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="362b4-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="362b4-106">Header file:</span></span>  <br/> |<span data-ttu-id="362b4-107">Mapispi.h</span><span class="sxs-lookup"><span data-stu-id="362b4-107">Mapispi.h</span></span>  <br/> |
   
```cpp
typedef struct
{
  ULONG cb;
  BYTE ab[MAPI_DIM];
} NOTIFKEY, FAR *LPNOTIFKEY;

```

## <a name="members"></a><span data-ttu-id="362b4-108">Members</span><span class="sxs-lookup"><span data-stu-id="362b4-108">Members</span></span>

 <span data-ttu-id="362b4-109">**cb**</span><span class="sxs-lookup"><span data-stu-id="362b4-109">**cb**</span></span>
  
> <span data-ttu-id="362b4-110">**Ab**成员中的字节数。</span><span class="sxs-lookup"><span data-stu-id="362b4-110">Count of bytes in the **ab** member.</span></span> 
    
 <span data-ttu-id="362b4-111">**ab**</span><span class="sxs-lookup"><span data-stu-id="362b4-111">**ab**</span></span>
  
> <span data-ttu-id="362b4-112">描述通知密钥的字节数组。</span><span class="sxs-lookup"><span data-stu-id="362b4-112">Array of bytes describing the notification key.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="362b4-113">注解</span><span class="sxs-lookup"><span data-stu-id="362b4-113">Remarks</span></span>

<span data-ttu-id="362b4-114">[IMAPISupport](imapisupportiunknown.md)的[Subscribe](imapisupport-subscribe.md)和[Notify](imapisupport-notify.md)方法使用**NOTIFKEY**结构生成适当的通知接收器有关适合 advise 源通知。</span><span class="sxs-lookup"><span data-stu-id="362b4-114">The [Subscribe](imapisupport-subscribe.md) and [Notify](imapisupport-notify.md) methods of [IMAPISupport](imapisupportiunknown.md) use the **NOTIFKEY** structure to generate notifications to the appropriate advise sink about the appropriate advise source.</span></span> 
  
<span data-ttu-id="362b4-115">服务提供商生成通知密钥时调用其**Advise**方法，他们希望将呼叫**Subscribe**来处理通知注册和后续发送的通知。</span><span class="sxs-lookup"><span data-stu-id="362b4-115">Service providers generate notification keys when their **Advise** method is called and they want to call **Subscribe** to handle the notification registration and the subsequent sending of notifications.</span></span> <span data-ttu-id="362b4-116">通知键可 advise 源的项标识符，也可以是任何其他标识的项目，如常量。</span><span class="sxs-lookup"><span data-stu-id="362b4-116">A notification key can be the entry identifier of the advise source or it can be any other identifying item such as a constant.</span></span> <span data-ttu-id="362b4-117">例如，消息存储提供程序可能使用的文件夹的路径作为通知键。</span><span class="sxs-lookup"><span data-stu-id="362b4-117">For example, a message store provider might use the path of a folder as its notification key.</span></span> 
  
<span data-ttu-id="362b4-118">跨多个进程情况下，通知键应起作用。</span><span class="sxs-lookup"><span data-stu-id="362b4-118">The notification key should work across multiple processes.</span></span> 
  
<span data-ttu-id="362b4-119">通知密钥的作用域要求类似于那些长期的项标识符。</span><span class="sxs-lookup"><span data-stu-id="362b4-119">The scope requirements for a notification key resemble those for a long-term entry identifier.</span></span> <span data-ttu-id="362b4-120">但是，与条目标识符，不同通知密钥必须二进制比较。</span><span class="sxs-lookup"><span data-stu-id="362b4-120">However, unlike an entry identifier, a notification key must be binary-comparable.</span></span> <span data-ttu-id="362b4-121">通常情况下，通知键包括由到对象后跟唯一其他特定于提供程序的信息的服务提供程序定义的**GUID**值。</span><span class="sxs-lookup"><span data-stu-id="362b4-121">Typically, a notification key includes a **GUID** value defined by the service provider followed by other provider-specific information unique to the object.</span></span> 
  
<span data-ttu-id="362b4-122">有关**NOTIFKEY**结构管理使用的讨论 advise 接收器生成通知的对象之间的连接，请参阅[支持事件通知](supporting-event-notification.md)。</span><span class="sxs-lookup"><span data-stu-id="362b4-122">For a discussion of the use of the **NOTIFKEY** structure to manage the connections between the advise sinks and the objects that generate the notifications, see [Supporting Event Notification](supporting-event-notification.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="362b4-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="362b4-123">See also</span></span>



[<span data-ttu-id="362b4-124">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="362b4-124">MAPI Structures</span></span>](mapi-structures.md)

