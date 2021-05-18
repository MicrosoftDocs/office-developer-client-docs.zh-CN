---
title: 释放传输提供程序
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e0f37485-55c9-40f0-bc8c-48f7297f9f50
description: 上次修改时间：2015 年 12 月 7 日
ms.openlocfilehash: 41d953db8e00ff52cd09a27e2f7550f9f1879321
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328383"
---
# <a name="releasing-the-transport-provider"></a><span data-ttu-id="2d78d-103">释放传输提供程序</span><span class="sxs-lookup"><span data-stu-id="2d78d-103">Releasing the Transport Provider</span></span>

 
  
<span data-ttu-id="2d78d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2d78d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2d78d-105">当 MAPI 或 MAPI 后台处理程序使用传输登录对象完成时：</span><span class="sxs-lookup"><span data-stu-id="2d78d-105">When MAPI or the MAPI spooler finishes using a transport logon object:</span></span>
  
1. <span data-ttu-id="2d78d-106">MAPI 或 MAPI 后台处理程序调用传输提供程序的 [IXPLogon：：TransportLogoff](ixplogon-transportlogoff.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="2d78d-106">MAPI or the MAPI spooler calls the transport provider's [IXPLogon::TransportLogoff](ixplogon-transportlogoff.md) method.</span></span> 
    
2. <span data-ttu-id="2d78d-107">传输提供程序通过调用 [IMAPISupport：：MakeInvalid](imapisupport-makeinvalid.md) 方法使状态对象失效。</span><span class="sxs-lookup"><span data-stu-id="2d78d-107">The transport provider invalidates the status object by calling the [IMAPISupport::MakeInvalid](imapisupport-makeinvalid.md) method.</span></span> <span data-ttu-id="2d78d-108">传输提供程序是否使 **在 TransportLogoff** 调用时发送或接收的邮件对象失效取决于传递给 **TransportLogoff 的标志**。</span><span class="sxs-lookup"><span data-stu-id="2d78d-108">Whether the transport provider invalidates message objects that are being sent or received at the time of the **TransportLogoff** call depends on the flags that were passed to **TransportLogoff**.</span></span>
    
3. <span data-ttu-id="2d78d-109">传输提供程序调用支持对象的 [IUnknown：：Release](https://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx) 方法，以从状态表中删除传输提供程序的行，并从内部表中删除使用 [IMAPISupport：：SetProviderUID](imapisupport-setprovideruid.md) 方法设置的任何唯一标识符 (UID) 。</span><span class="sxs-lookup"><span data-stu-id="2d78d-109">The transport provider calls the support object's [IUnknown::Release](https://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx) method to remove the transport provider's row from the status table and remove from internal tables any unique identifiers (UIDs) that were set with the [IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md) method.</span></span> <span data-ttu-id="2d78d-110">它可缩小此提供程序对象上活动的已知登录对象数。</span><span class="sxs-lookup"><span data-stu-id="2d78d-110">It decrements the count of known logon objects active on this provider object.</span></span> <span data-ttu-id="2d78d-111">如果计数达到零，MAPI 将调用提供程序对象的 [IXPProvider：：Shutdown](ixpprovider-shutdown.md)方法和 **Release。**</span><span class="sxs-lookup"><span data-stu-id="2d78d-111">If the count reaches zero, MAPI calls the [IXPProvider::Shutdown](ixpprovider-shutdown.md) method and **Release** on the provider object.</span></span> <span data-ttu-id="2d78d-112">如果这是最后一个在此进程中使用此 DLL 的已知提供程序对象，MAPI 稍后将调用 DLL 上的 **FreeLibrary** 函数。</span><span class="sxs-lookup"><span data-stu-id="2d78d-112">If this was the last known provider object using this DLL on this process, MAPI calls the **FreeLibrary** function on the DLL at a later time.</span></span> <span data-ttu-id="2d78d-113">释放 MAPI 支持对象的内存，并且支持对象的 **Release** 方法返回。</span><span class="sxs-lookup"><span data-stu-id="2d78d-113">Memory for the MAPI support object is freed and the support object **Release** method returns.</span></span> 
    
4. <span data-ttu-id="2d78d-114">**TransportLogoff** 方法返回S_OK。</span><span class="sxs-lookup"><span data-stu-id="2d78d-114">The **TransportLogoff** method returns S_OK.</span></span> 
    
5. <span data-ttu-id="2d78d-115">MAPI 或 MAPI 后台处理程序对传输提供程序的登录对象调用 **Release。**</span><span class="sxs-lookup"><span data-stu-id="2d78d-115">MAPI or the MAPI spooler calls **Release** on the transport provider's logon object.</span></span> <span data-ttu-id="2d78d-116">释放对象的内存。</span><span class="sxs-lookup"><span data-stu-id="2d78d-116">The memory for the object is released.</span></span> 
    
6. <span data-ttu-id="2d78d-117">MAPI 或 MAPI 后台处理程序在提供程序 DLL 上调用 **FreeLibrary。**</span><span class="sxs-lookup"><span data-stu-id="2d78d-117">MAPI or the MAPI spooler calls **FreeLibrary** on the provider DLL.</span></span> 
    
<span data-ttu-id="2d78d-118">为了可靠，登录和提供程序对象应能够自行处理最终 **的 Release** 调用，而无需首先调用 **其 TransportLogoff** 或 **Shutdown** 方法。</span><span class="sxs-lookup"><span data-stu-id="2d78d-118">For robustness, the logon and provider objects should be able to handle final **Release** calls on themselves without first having their **TransportLogoff** or **Shutdown** methods called.</span></span> <span data-ttu-id="2d78d-119">如果 **在这种情况下调用 Release，** 则传输提供程序应该将调用视为使用零参数调用 **TransportLogoff** 或 **Shutdown** 后跟 **Release**。</span><span class="sxs-lookup"><span data-stu-id="2d78d-119">If **Release** is called in such cases, transport providers should treat the calls as if **TransportLogoff** or **Shutdown** had been called with a zero argument followed by **Release**.</span></span>
  

