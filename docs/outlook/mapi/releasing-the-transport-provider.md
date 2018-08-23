---
title: 释放传输提供程序
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e0f37485-55c9-40f0-bc8c-48f7297f9f50
description: 上次修改时间： 2015年12月7日
ms.openlocfilehash: ea9656f9571777478d3db9a2613fbff5ddef0ee6
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592288"
---
# <a name="releasing-the-transport-provider"></a><span data-ttu-id="a2bfd-103">释放传输提供程序</span><span class="sxs-lookup"><span data-stu-id="a2bfd-103">Releasing the Transport Provider</span></span>

 
  
<span data-ttu-id="a2bfd-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a2bfd-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a2bfd-105">当 MAPI 或 MAPI 后台处理程序完成使用传输登录对象：</span><span class="sxs-lookup"><span data-stu-id="a2bfd-105">When MAPI or the MAPI spooler finishes using a transport logon object:</span></span>
  
1. <span data-ttu-id="a2bfd-106">MAPI 或 MAPI 后台处理程序调用传输提供程序的[IXPLogon::TransportLogoff](ixplogon-transportlogoff.md)方法。</span><span class="sxs-lookup"><span data-stu-id="a2bfd-106">MAPI or the MAPI spooler calls the transport provider's [IXPLogon::TransportLogoff](ixplogon-transportlogoff.md) method.</span></span> 
    
2. <span data-ttu-id="a2bfd-107">传输提供程序使状态对象无效通过调用[IMAPISupport::MakeInvalid](imapisupport-makeinvalid.md)方法。</span><span class="sxs-lookup"><span data-stu-id="a2bfd-107">The transport provider invalidates the status object by calling the [IMAPISupport::MakeInvalid](imapisupport-makeinvalid.md) method.</span></span> <span data-ttu-id="a2bfd-108">传输提供程序使失效的消息对象是否正在发送或接收在**TransportLogoff**呼叫的时间取决于已传递给**TransportLogoff**的标志。</span><span class="sxs-lookup"><span data-stu-id="a2bfd-108">Whether the transport provider invalidates message objects that are being sent or received at the time of the **TransportLogoff** call depends on the flags that were passed to **TransportLogoff**.</span></span>
    
3. <span data-ttu-id="a2bfd-109">传输提供程序调用支持对象的[IUnknown::Release](http://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx)方法来从状态表中删除传输提供程序的行，从内部表中删除已设置[IMAPISupport 与任何唯一标识符 (Uid)::SetProviderUID](imapisupport-setprovideruid.md)方法。</span><span class="sxs-lookup"><span data-stu-id="a2bfd-109">The transport provider calls the support object's [IUnknown::Release](http://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx) method to remove the transport provider's row from the status table and remove from internal tables any unique identifiers (UIDs) that were set with the [IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md) method.</span></span> <span data-ttu-id="a2bfd-110">它递减已知的登录对象上此提供商对象的计数。</span><span class="sxs-lookup"><span data-stu-id="a2bfd-110">It decrements the count of known logon objects active on this provider object.</span></span> <span data-ttu-id="a2bfd-111">如果计数为零时，MAPI 提供程序对象上调用[IXPProvider::Shutdown](ixpprovider-shutdown.md)方法和**版本**。</span><span class="sxs-lookup"><span data-stu-id="a2bfd-111">If the count reaches zero, MAPI calls the [IXPProvider::Shutdown](ixpprovider-shutdown.md) method and **Release** on the provider object.</span></span> <span data-ttu-id="a2bfd-112">如果这是在此过程中使用此 DLL 的最后一个已知的提供程序对象，MAPI 会在以后对 DLL 调用**句**函数。</span><span class="sxs-lookup"><span data-stu-id="a2bfd-112">If this was the last known provider object using this DLL on this process, MAPI calls the **FreeLibrary** function on the DLL at a later time.</span></span> <span data-ttu-id="a2bfd-113">释放内存的 MAPI 支持对象，并支持对象**释放**方法返回。</span><span class="sxs-lookup"><span data-stu-id="a2bfd-113">Memory for the MAPI support object is freed and the support object **Release** method returns.</span></span> 
    
4. <span data-ttu-id="a2bfd-114">**TransportLogoff**方法，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="a2bfd-114">The **TransportLogoff** method returns S_OK.</span></span> 
    
5. <span data-ttu-id="a2bfd-115">MAPI 或 MAPI 后台处理程序传输提供程序的登录对象上调用**版本**。</span><span class="sxs-lookup"><span data-stu-id="a2bfd-115">MAPI or the MAPI spooler calls **Release** on the transport provider's logon object.</span></span> <span data-ttu-id="a2bfd-116">释放对象的内存。</span><span class="sxs-lookup"><span data-stu-id="a2bfd-116">The memory for the object is released.</span></span> 
    
6. <span data-ttu-id="a2bfd-117">MAPI 或 MAPI 后台处理程序提供程序 DLL 调用**句**。</span><span class="sxs-lookup"><span data-stu-id="a2bfd-117">MAPI or the MAPI spooler calls **FreeLibrary** on the provider DLL.</span></span> 
    
<span data-ttu-id="a2bfd-118">考虑到可靠性，应能够处理自身而无需事先其**TransportLogoff**或**关闭**方法调用的最终**发行**呼叫的登录和提供程序的对象。</span><span class="sxs-lookup"><span data-stu-id="a2bfd-118">For robustness, the logon and provider objects should be able to handle final **Release** calls on themselves without first having their **TransportLogoff** or **Shutdown** methods called.</span></span> <span data-ttu-id="a2bfd-119">如果在这种情况下调用**发行版**，则传输提供程序应将呼叫，视为**TransportLogoff**或**关闭**已被调用**发行**后跟零个参数。</span><span class="sxs-lookup"><span data-stu-id="a2bfd-119">If **Release** is called in such cases, transport providers should treat the calls as if **TransportLogoff** or **Shutdown** had been called with a zero argument followed by **Release**.</span></span>
  

