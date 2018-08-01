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
ms.openlocfilehash: 4a0ab660b8df2fb32f21f9bc93932a9187c37b7b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779013"
---
# <a name="types-of-transport-providers"></a><span data-ttu-id="702ea-103">传输提供程序的类型</span><span class="sxs-lookup"><span data-stu-id="702ea-103">Types of Transport Providers</span></span>

  
  
<span data-ttu-id="702ea-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="702ea-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="702ea-105">所有传输提供程序都支持各种标准版功能，如：</span><span class="sxs-lookup"><span data-stu-id="702ea-105">All transport providers support a range of standard features, such as:</span></span>
  
- <span data-ttu-id="702ea-106">为基础的消息系统提供适当的安全。</span><span class="sxs-lookup"><span data-stu-id="702ea-106">Providing proper security for the underlying messaging system.</span></span>
    
- <span data-ttu-id="702ea-107">发送和接收来自基础消息系统消息。</span><span class="sxs-lookup"><span data-stu-id="702ea-107">Sending and receiving messages from the underlying messaging system.</span></span>
    
- <span data-ttu-id="702ea-108">公开地址类型，以便的 MAPI 后台处理程序和客户端应用程序可以相应地使用它们支持传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="702ea-108">Exposing the address types the transport providers support so the MAPI spooler and client applications can use them appropriately.</span></span>
    
- <span data-ttu-id="702ea-109">对特定收件人的接受传递。</span><span class="sxs-lookup"><span data-stu-id="702ea-109">Accepting delivery for specific recipients.</span></span>
    
<span data-ttu-id="702ea-110">此外，MAPI 支持提供程序的两个专用的的类型的特定邮件系统。</span><span class="sxs-lookup"><span data-stu-id="702ea-110">In addition, MAPI supports two specialized types of providers for specific messaging systems.</span></span>
  
|<span data-ttu-id="702ea-111">**传输类型**</span><span class="sxs-lookup"><span data-stu-id="702ea-111">**Transport type**</span></span>|<span data-ttu-id="702ea-112">**新增的功能**</span><span class="sxs-lookup"><span data-stu-id="702ea-112">**Added functionality**</span></span>|
|:-----|:-----|
|<span data-ttu-id="702ea-113">远程传输</span><span class="sxs-lookup"><span data-stu-id="702ea-113">Remote Transport</span></span>  <br/> |<span data-ttu-id="702ea-114">与远程连接的客户端实现互操作性。</span><span class="sxs-lookup"><span data-stu-id="702ea-114">Enables interoperability with clients connected remotely.</span></span>  <br/> |
|<span data-ttu-id="702ea-115">TNEF 传输</span><span class="sxs-lookup"><span data-stu-id="702ea-115">TNEF Transport</span></span>  <br/> |<span data-ttu-id="702ea-116">允许消息不支持它们的系统上保留的 MAPI 属性。</span><span class="sxs-lookup"><span data-stu-id="702ea-116">Allows MAPI properties to be preserved on messaging systems that do not support them.</span></span>  <br/> |
   
<span data-ttu-id="702ea-117">TNEF 传输用于翻译支持不同的 MAPI 属性集的邮件系统之间的邮件。</span><span class="sxs-lookup"><span data-stu-id="702ea-117">TNEF transports are used for translating messages between messaging systems that support different sets of MAPI properties.</span></span> <span data-ttu-id="702ea-118">TNEF 传输使用 MAPI [ITnef: IUnknown](itnefiunknown.md)接口将直接转换可以附加到邮件二进制数据流的目标系统不能代表其任何属性。</span><span class="sxs-lookup"><span data-stu-id="702ea-118">TNEF transports use the MAPI [ITnef : IUnknown](itnefiunknown.md) interface to convert any properties that the destination system cannot represent directly into a binary data stream that can be attached to the message.</span></span> <span data-ttu-id="702ea-119">更高版本，另一个 TNEF 传输可以使用**ITnef**解码数据流并使其原始的 MAPI 属性供客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="702ea-119">Later, another TNEF transport can use **ITnef** to decode the data stream and make the original MAPI properties available to client applications.</span></span> <span data-ttu-id="702ea-120">此外，TNEF 支持时需要您传输需要支持自定义邮件类别。</span><span class="sxs-lookup"><span data-stu-id="702ea-120">Additionally, TNEF support is required if your transport needs to support custom message classes.</span></span> <span data-ttu-id="702ea-121">有关实现 TNEF 传输的信息，请参阅[开发 TNEF-Enabled 传输提供程序](developing-a-tnef-enabled-transport-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="702ea-121">For information about implementing TNEF transports, see [Developing a TNEF-Enabled Transport Provider](developing-a-tnef-enabled-transport-provider.md).</span></span>
  
<span data-ttu-id="702ea-122">如果您传输提供程序不是其中一种类型，必须将实现它的基本 MAPI 函数和网络功能在您的目标平台上可用。</span><span class="sxs-lookup"><span data-stu-id="702ea-122">If your transport provider is not one of these types, you will have to implement it with the basic MAPI functions and networking functions available on your target platform.</span></span>
  

