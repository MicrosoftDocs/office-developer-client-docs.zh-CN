---
title: 传输提供程序的类型
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 772ecab1-7e91-415b-bae8-af8ffb7b7ed9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ca224658552af105d95794b4dd01d2ac76fe084f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315377"
---
# <a name="types-of-transport-providers"></a><span data-ttu-id="d37b2-103">传输提供程序的类型</span><span class="sxs-lookup"><span data-stu-id="d37b2-103">Types of Transport Providers</span></span>

  
  
<span data-ttu-id="d37b2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d37b2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d37b2-105">所有传输提供程序都支持一系列标准功能, 如:</span><span class="sxs-lookup"><span data-stu-id="d37b2-105">All transport providers support a range of standard features, such as:</span></span>
  
- <span data-ttu-id="d37b2-106">为基础邮件系统提供正确的安全性。</span><span class="sxs-lookup"><span data-stu-id="d37b2-106">Providing proper security for the underlying messaging system.</span></span>
    
- <span data-ttu-id="d37b2-107">从基础邮件系统发送和接收邮件。</span><span class="sxs-lookup"><span data-stu-id="d37b2-107">Sending and receiving messages from the underlying messaging system.</span></span>
    
- <span data-ttu-id="d37b2-108">公开传输提供程序支持的地址类型, 以便 MAPI 后台处理程序和客户端应用程序可以适当地使用它们。</span><span class="sxs-lookup"><span data-stu-id="d37b2-108">Exposing the address types the transport providers support so the MAPI spooler and client applications can use them appropriately.</span></span>
    
- <span data-ttu-id="d37b2-109">接受特定收件人的传递。</span><span class="sxs-lookup"><span data-stu-id="d37b2-109">Accepting delivery for specific recipients.</span></span>
    
<span data-ttu-id="d37b2-110">此外, MAPI 还支持针对特定邮件系统的两种专用类型的提供程序。</span><span class="sxs-lookup"><span data-stu-id="d37b2-110">In addition, MAPI supports two specialized types of providers for specific messaging systems.</span></span>
  
|<span data-ttu-id="d37b2-111">**传输类型**</span><span class="sxs-lookup"><span data-stu-id="d37b2-111">**Transport type**</span></span>|<span data-ttu-id="d37b2-112">**新增功能**</span><span class="sxs-lookup"><span data-stu-id="d37b2-112">**Added functionality**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d37b2-113">远程传输</span><span class="sxs-lookup"><span data-stu-id="d37b2-113">Remote Transport</span></span>  <br/> |<span data-ttu-id="d37b2-114">启用与远程连接的客户端的互操作性。</span><span class="sxs-lookup"><span data-stu-id="d37b2-114">Enables interoperability with clients connected remotely.</span></span>  <br/> |
|<span data-ttu-id="d37b2-115">TNEF 传输</span><span class="sxs-lookup"><span data-stu-id="d37b2-115">TNEF Transport</span></span>  <br/> |<span data-ttu-id="d37b2-116">允许将 MAPI 属性保留在不支持它们的邮件系统上。</span><span class="sxs-lookup"><span data-stu-id="d37b2-116">Allows MAPI properties to be preserved on messaging systems that do not support them.</span></span>  <br/> |
   
<span data-ttu-id="d37b2-117">TNEF 传输用于在支持不同的 MAPI 属性集的邮件系统之间转换邮件。</span><span class="sxs-lookup"><span data-stu-id="d37b2-117">TNEF transports are used for translating messages between messaging systems that support different sets of MAPI properties.</span></span> <span data-ttu-id="d37b2-118">TNEF 传输使用 MAPI [ITnef: IUnknown](itnefiunknown.md)接口将目标系统不能直接代表的任何属性转换为可以附加到邮件的二进制数据流。</span><span class="sxs-lookup"><span data-stu-id="d37b2-118">TNEF transports use the MAPI [ITnef : IUnknown](itnefiunknown.md) interface to convert any properties that the destination system cannot represent directly into a binary data stream that can be attached to the message.</span></span> <span data-ttu-id="d37b2-119">稍后, 另一个 TNEF 传输可以使用**ITnef**对数据流进行解码, 并使原始 MAPI 属性对客户端应用程序可用。</span><span class="sxs-lookup"><span data-stu-id="d37b2-119">Later, another TNEF transport can use **ITnef** to decode the data stream and make the original MAPI properties available to client applications.</span></span> <span data-ttu-id="d37b2-120">此外, 如果传输需要支持自定义邮件类别, 则需要 TNEF 支持。</span><span class="sxs-lookup"><span data-stu-id="d37b2-120">Additionally, TNEF support is required if your transport needs to support custom message classes.</span></span> <span data-ttu-id="d37b2-121">有关实现 tnef 传输的信息, 请参阅[开发启用 tnef 的传输提供程序](developing-a-tnef-enabled-transport-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="d37b2-121">For information about implementing TNEF transports, see [Developing a TNEF-Enabled Transport Provider](developing-a-tnef-enabled-transport-provider.md).</span></span>
  
<span data-ttu-id="d37b2-122">如果你的传输提供程序不是这些类型之一, 则必须使用目标平台上可用的基本 MAPI 函数和网络功能来实现它。</span><span class="sxs-lookup"><span data-stu-id="d37b2-122">If your transport provider is not one of these types, you will have to implement it with the basic MAPI functions and networking functions available on your target platform.</span></span>
  

