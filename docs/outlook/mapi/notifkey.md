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
ms.openlocfilehash: ab1586696a4b72aa9e88545c2069c3f8b5d22d72
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32280045"
---
# <a name="notifkey"></a><span data-ttu-id="ebd00-103">NOTIFKEY</span><span class="sxs-lookup"><span data-stu-id="ebd00-103">NOTIFKEY</span></span>

  
  
<span data-ttu-id="ebd00-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ebd00-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ebd00-105">唯一标识通知接收器、通知源和 MAPI 之间的连接。</span><span class="sxs-lookup"><span data-stu-id="ebd00-105">Uniquely identifies a connection between an advise sink, an advise source, and MAPI.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ebd00-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="ebd00-106">Header file:</span></span>  <br/> |<span data-ttu-id="ebd00-107">Mapispi</span><span class="sxs-lookup"><span data-stu-id="ebd00-107">Mapispi.h</span></span>  <br/> |
   
```cpp
typedef struct
{
  ULONG cb;
  BYTE ab[MAPI_DIM];
} NOTIFKEY, FAR *LPNOTIFKEY;

```

## <a name="members"></a><span data-ttu-id="ebd00-108">Members</span><span class="sxs-lookup"><span data-stu-id="ebd00-108">Members</span></span>

 <span data-ttu-id="ebd00-109">**cb**</span><span class="sxs-lookup"><span data-stu-id="ebd00-109">**cb**</span></span>
  
> <span data-ttu-id="ebd00-110">**ab**成员中的字节数。</span><span class="sxs-lookup"><span data-stu-id="ebd00-110">Count of bytes in the **ab** member.</span></span> 
    
 <span data-ttu-id="ebd00-111">**ab**</span><span class="sxs-lookup"><span data-stu-id="ebd00-111">**ab**</span></span>
  
> <span data-ttu-id="ebd00-112">描述通知密钥的字节数组。</span><span class="sxs-lookup"><span data-stu-id="ebd00-112">Array of bytes describing the notification key.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="ebd00-113">注解</span><span class="sxs-lookup"><span data-stu-id="ebd00-113">Remarks</span></span>

<span data-ttu-id="ebd00-114">[IMAPISupport](imapisupportiunknown.md)的[订阅](imapisupport-subscribe.md)和[通知](imapisupport-notify.md)方法使用**NOTIFKEY**结构向相应的建议接收器生成有关相应的建议源的通知。</span><span class="sxs-lookup"><span data-stu-id="ebd00-114">The [Subscribe](imapisupport-subscribe.md) and [Notify](imapisupport-notify.md) methods of [IMAPISupport](imapisupportiunknown.md) use the **NOTIFKEY** structure to generate notifications to the appropriate advise sink about the appropriate advise source.</span></span> 
  
<span data-ttu-id="ebd00-115">服务提供程序在调用其**Advise**方法时生成通知密钥, 他们希望呼叫**订阅**以处理通知注册和后续发送通知。</span><span class="sxs-lookup"><span data-stu-id="ebd00-115">Service providers generate notification keys when their **Advise** method is called and they want to call **Subscribe** to handle the notification registration and the subsequent sending of notifications.</span></span> <span data-ttu-id="ebd00-116">通知密钥可以是建议源的条目标识符, 也可以是任何其他标识项 (如常量)。</span><span class="sxs-lookup"><span data-stu-id="ebd00-116">A notification key can be the entry identifier of the advise source or it can be any other identifying item such as a constant.</span></span> <span data-ttu-id="ebd00-117">例如, 邮件存储提供程序可能会将文件夹的路径用作其通知密钥。</span><span class="sxs-lookup"><span data-stu-id="ebd00-117">For example, a message store provider might use the path of a folder as its notification key.</span></span> 
  
<span data-ttu-id="ebd00-118">通知密钥应跨多个进程运行。</span><span class="sxs-lookup"><span data-stu-id="ebd00-118">The notification key should work across multiple processes.</span></span> 
  
<span data-ttu-id="ebd00-119">通知密钥的范围要求与长期条目标识符的范围要求类似。</span><span class="sxs-lookup"><span data-stu-id="ebd00-119">The scope requirements for a notification key resemble those for a long-term entry identifier.</span></span> <span data-ttu-id="ebd00-120">但是, 与条目标识符不同的是, 通知密钥必须可比二进制比较。</span><span class="sxs-lookup"><span data-stu-id="ebd00-120">However, unlike an entry identifier, a notification key must be binary-comparable.</span></span> <span data-ttu-id="ebd00-121">通常情况下, 通知密钥包括服务提供程序定义的**GUID**值, 后跟该对象特有的特定于提供程序的特定信息。</span><span class="sxs-lookup"><span data-stu-id="ebd00-121">Typically, a notification key includes a **GUID** value defined by the service provider followed by other provider-specific information unique to the object.</span></span> 
  
<span data-ttu-id="ebd00-122">有关使用**NOTIFKEY**结构来管理通知接收器与生成通知的对象之间的连接的讨论, 请参阅[支持事件通知](supporting-event-notification.md)。</span><span class="sxs-lookup"><span data-stu-id="ebd00-122">For a discussion of the use of the **NOTIFKEY** structure to manage the connections between the advise sinks and the objects that generate the notifications, see [Supporting Event Notification](supporting-event-notification.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ebd00-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ebd00-123">See also</span></span>



[<span data-ttu-id="ebd00-124">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="ebd00-124">MAPI Structures</span></span>](mapi-structures.md)

