---
title: IXPLogonAddressTypes
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IXPLogon.AddressTypes
api_type:
- COM
ms.assetid: 5add1f2b-d9e6-4d78-8739-c3848f6e32a3
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ca68c604152a7a28fb6a5357aa9c012ec7466b5a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435374"
---
# <a name="ixplogonaddresstypes"></a><span data-ttu-id="5ba43-103">IXPLogon::AddressTypes</span><span class="sxs-lookup"><span data-stu-id="5ba43-103">IXPLogon::AddressTypes</span></span>

  
  
<span data-ttu-id="5ba43-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5ba43-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5ba43-105">返回传输提供程序处理的收件人类型。</span><span class="sxs-lookup"><span data-stu-id="5ba43-105">Returns the types of recipients that the transport provider handles.</span></span>
  
```cpp
HRESULT AddressTypes(
  ULONG FAR * lpulFlags,
  ULONG FAR * lpcAdrType,
  LPSTR FAR * FAR * lpppszAdrTypeArray,
  ULONG FAR * lpcMAPIUID,
  LPUID FAR * FAR * lpppUIDArray
);
```

## <a name="parameters"></a><span data-ttu-id="5ba43-106">参数</span><span class="sxs-lookup"><span data-stu-id="5ba43-106">Parameters</span></span>

 <span data-ttu-id="5ba43-107">_lpulFlags_</span><span class="sxs-lookup"><span data-stu-id="5ba43-107">_lpulFlags_</span></span>
  
> <span data-ttu-id="5ba43-108">[out]控制返回的字符串类型的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="5ba43-108">[out] A bitmask of flags that controls the type of strings returned.</span></span> <span data-ttu-id="5ba43-109">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="5ba43-109">The following flag can be set:</span></span>
    
<span data-ttu-id="5ba43-110">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="5ba43-110">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="5ba43-111">返回的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="5ba43-111">The returned strings are in Unicode format.</span></span> <span data-ttu-id="5ba43-112">如果未MAPI_UNICODE，则字符串采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="5ba43-112">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="5ba43-113">_lpcAdrType_</span><span class="sxs-lookup"><span data-stu-id="5ba43-113">_lpcAdrType_</span></span>
  
> <span data-ttu-id="5ba43-114">[out]指向  _lpppszAdrTypeArray_ 参数指向的数组中的条目计数的指针。</span><span class="sxs-lookup"><span data-stu-id="5ba43-114">[out] A pointer to the count of entries in the array pointed to by the  _lpppszAdrTypeArray_ parameter.</span></span> 
    
 <span data-ttu-id="5ba43-115">_lpppszAdrTypeArray_</span><span class="sxs-lookup"><span data-stu-id="5ba43-115">_lpppszAdrTypeArray_</span></span>
  
> <span data-ttu-id="5ba43-116">[out]指向指向标识收件人类型的字符串数组的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="5ba43-116">[out] A pointer to a pointer to an array of strings that identify recipient types.</span></span>
    
 <span data-ttu-id="5ba43-117">_lpcMAPIUID_</span><span class="sxs-lookup"><span data-stu-id="5ba43-117">_lpcMAPIUID_</span></span>
  
> <span data-ttu-id="5ba43-118">[out]指向  _lpppUIDArray_ 参数指向的数组中的条目计数的指针。</span><span class="sxs-lookup"><span data-stu-id="5ba43-118">[out] A pointer to the count of entries in the array pointed to by the  _lpppUIDArray_ parameter.</span></span> 
    
 <span data-ttu-id="5ba43-119">_lpppUIDArray_</span><span class="sxs-lookup"><span data-stu-id="5ba43-119">_lpppUIDArray_</span></span>
  
> <span data-ttu-id="5ba43-120">[out]指向指向指向标识收件人类型的 [MAPIUID](mapiuid.md) 结构的指针数组的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="5ba43-120">[out] A pointer to a pointer to an array of pointers to [MAPIUID](mapiuid.md) structures that identify recipient types.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="5ba43-121">返回值</span><span class="sxs-lookup"><span data-stu-id="5ba43-121">Return value</span></span>

<span data-ttu-id="5ba43-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="5ba43-122">S_OK</span></span> 
  
> <span data-ttu-id="5ba43-123">传输提供程序已成功指示它可以处理的收件人类型。</span><span class="sxs-lookup"><span data-stu-id="5ba43-123">The transport provider successfully indicated the types of recipients that it can handle.</span></span>
    
## <a name="notes-to-implementers"></a><span data-ttu-id="5ba43-124">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="5ba43-124">Notes to implementers</span></span>

<span data-ttu-id="5ba43-125">MAPI 后台处理程序在传输提供程序从对 [IXPProvider：：TransportLogon](ixpprovider-transportlogon.md)方法的调用返回后立即调用 **IXPLogon：：AddressTypes** 方法，以便传输提供程序可以指示它处理的收件人类型。</span><span class="sxs-lookup"><span data-stu-id="5ba43-125">The MAPI spooler calls the **IXPLogon::AddressTypes** method immediately after a transport provider returns from a call to the [IXPProvider::TransportLogon](ixpprovider-transportlogon.md) method so the transport provider can indicate what types of recipients it handles.</span></span> <span data-ttu-id="5ba43-126">为表明这一点，传输提供程序应在  _lpppszAdrTypeArray_ 参数中传递回指向指向字符串的指针数组的指针，或传递回  _lpppUIDArray_ 参数指向 **指向 MAPIUID** 结构的指针数组的指针，或传递这两个参数中的值。</span><span class="sxs-lookup"><span data-stu-id="5ba43-126">To indicate this, the transport provider should pass back in the  _lpppszAdrTypeArray_ parameter a pointer to an array of pointers to strings, or pass back in the  _lpppUIDArray_ parameter a pointer to an array of pointers to **MAPIUID** structures, or pass values in both parameters.</span></span> 
  
<span data-ttu-id="5ba43-127">这两个数组用于不同的标识过程。</span><span class="sxs-lookup"><span data-stu-id="5ba43-127">These two arrays are used for different identification processes.</span></span> <span data-ttu-id="5ba43-128">MAPI 和 MAPI 后台处理程序使用 _lpppUIDArray_ 数组中的 [MAPIUID](mapiuid.md)结构标识由传输提供程序或传输提供程序连接到的邮件系统直接处理的收件人条目标识符。</span><span class="sxs-lookup"><span data-stu-id="5ba43-128">MAPI and the MAPI spooler use the [MAPIUID](mapiuid.md) structures in the  _lpppUIDArray_ array to identify those recipient entry identifiers that are directly handled by the transport provider or by the messaging system to which the transport provider connects.</span></span> <span data-ttu-id="5ba43-129">MAPI 和 MAPI 后台处理程序都不通过使用这些 **MAPIUID** 结构中包含的条目标识符来扩展地址;这些结构仅用于收件人类型标识。</span><span class="sxs-lookup"><span data-stu-id="5ba43-129">Neither MAPI nor the MAPI spooler expands addresses by using entry identifiers contained in any of these **MAPIUID** structures; these structures are used only for recipient type identification.</span></span> 
  
<span data-ttu-id="5ba43-130">MAPI 后台处理程序在决定哪个传输提供程序应处理出站邮件的哪些收件人时，将使用  _lpppszAdrTypeArray_ 参数中的每个字符串进行比较测试。</span><span class="sxs-lookup"><span data-stu-id="5ba43-130">The MAPI spooler uses each of the strings in the  _lpppszAdrTypeArray_ parameter for a comparison test when it decides which transport provider should handle which recipients for an outbound message.</span></span> <span data-ttu-id="5ba43-131">如果邮件收件人的 **PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) 属性与标识传输提供程序提供的邮件地址类型之一的字符串完全匹配，则提供程序可以将邮件传递至该收件人。</span><span class="sxs-lookup"><span data-stu-id="5ba43-131">If a message recipient's **PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) property exactly matches a string that identifies one of the messaging address types that the transport provider supplies, the provider can deliver the message to that recipient.</span></span>
  
<span data-ttu-id="5ba43-132">如果多个传输提供程序可以处理同一类型的收件人，MAPI 将基于客户端应用程序的配置文件中指示的传输优先级顺序选择传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="5ba43-132">If multiple transport providers can handle the same type of recipient, MAPI selects a transport provider based on the transport priority order indicated in the client application's profile.</span></span> <span data-ttu-id="5ba43-133">为了确定要使用哪个传输提供程序，MAPI 后台处理程序按优先级顺序扫描所有提供程序指定的 **MAPIUID** 结构，然后按优先级顺序扫描所有提供程序指定的地址类型值。</span><span class="sxs-lookup"><span data-stu-id="5ba43-133">To determine which transport provider to use, the MAPI spooler scans all provider-specified **MAPIUID** structures in priority order, and then all provider-specified address type values in priority order.</span></span> <span data-ttu-id="5ba43-134">此扫描中与特定收件人匹配的第一个传输提供程序将第一次获得处理此收件人的机会。</span><span class="sxs-lookup"><span data-stu-id="5ba43-134">The first transport provider to match a particular recipient in this scan gets the first opportunity to handle this recipient.</span></span> <span data-ttu-id="5ba43-135">如果该提供程序不处理收件人，MAPI 后台处理程序将继续扫描以查找任何尚未处理的收件人的传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="5ba43-135">If that provider does not handle the recipient, the MAPI spooler continues the scan to find a transport provider for any recipient not yet handled.</span></span> <span data-ttu-id="5ba43-136">扫描将继续，直到未找到任何进一步匹配项，此时会为未处理的任何收件人生成未送达报告。</span><span class="sxs-lookup"><span data-stu-id="5ba43-136">The scan continues until no further matches are found, at which point a nondelivery report is generated for any recipient that was not handled.</span></span> 
  
<span data-ttu-id="5ba43-137">如果提供程序始终支持一组特定的收件人类型，则传输提供程序传递的地址类型和 **MAPIUID** 数组可以是静态的。</span><span class="sxs-lookup"><span data-stu-id="5ba43-137">If the provider always supports a particular set of recipient types, the address type and **MAPIUID** arrays that the transport provider passed can be static.</span></span> <span data-ttu-id="5ba43-138">如果传输提供程序动态构造这些数组，它可以使用之前在调用 **TransportLogon** 时传递的支持对象来分配内存，尽管这不是必需的。</span><span class="sxs-lookup"><span data-stu-id="5ba43-138">If the transport provider dynamically constructs these arrays, it can allocate memory by using the support object that was previously passed in the call to **TransportLogon**, although this is not necessary.</span></span>
  
<span data-ttu-id="5ba43-139">用于地址类型和 **MAPIUID** 数组的内存应保持分配状态，直到最终调用 [IXPLogon：：TransportLogoff](ixplogon-transportlogoff.md) 方法，传输提供程序在必要时可以释放内存。</span><span class="sxs-lookup"><span data-stu-id="5ba43-139">The memory used for the address type and **MAPIUID** arrays should remain allocated until the final call to the [IXPLogon::TransportLogoff](ixplogon-transportlogoff.md) method, at which time the transport provider can free the memory, if necessary.</span></span> <span data-ttu-id="5ba43-140">传输提供程序在从 **TransportLogoff** 调用返回后不应更改这些数组的内容。</span><span class="sxs-lookup"><span data-stu-id="5ba43-140">The transport provider should not alter the contents of these arrays after it returns from the **TransportLogoff** call.</span></span> 
  
<span data-ttu-id="5ba43-141">可以处理任何类型的收件人的传输提供程序可以在  _lpppszAdrTypeArray_ 参数中返回 NULL。</span><span class="sxs-lookup"><span data-stu-id="5ba43-141">A transport provider that can handle any type of recipient can return NULL in the  _lpppszAdrTypeArray_ parameter.</span></span> <span data-ttu-id="5ba43-142">基于 LAN 的邮件系统的传输提供程序，使用中央服务器将传出邮件发送到各种外消息系统通常可以这样做。</span><span class="sxs-lookup"><span data-stu-id="5ba43-142">Transport providers for LAN-based messaging systems that use a central server to deliver outgoing messages to various foreign message systems commonly do this.</span></span> <span data-ttu-id="5ba43-143">这种类型的传输提供程序应在配置文件中传输提供程序的 MAPI 和 MAPI 后台处理程序优先级顺序中最后安装。</span><span class="sxs-lookup"><span data-stu-id="5ba43-143">This type of transport provider should be installed last in the MAPI and MAPI spooler priority order of transport providers in the profile.</span></span> 
  
<span data-ttu-id="5ba43-144">不支持根据地址类型调度到它的出站邮件的传输提供程序应在  _lpppszAdrTypeArray_ 中返回单个零长度字符串。</span><span class="sxs-lookup"><span data-stu-id="5ba43-144">A transport provider that does not support outbound messages that are dispatched to it based on address type should return a single zero-length string in  _lpppszAdrTypeArray_.</span></span> <span data-ttu-id="5ba43-145">如果传输提供程序不支持收件人类型，则应该为 **MAPIUID** 结构传递 NULL，为地址类型传递空字符串。</span><span class="sxs-lookup"><span data-stu-id="5ba43-145">If a transport provider supports no recipient types, it should pass NULL for the **MAPIUID** structure and an empty string for the address type.</span></span> <span data-ttu-id="5ba43-146">此类型的传输提供程序最常用于安装邮件预处理器。</span><span class="sxs-lookup"><span data-stu-id="5ba43-146">Transport providers of this type are most commonly used to install a message preprocessor.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="5ba43-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5ba43-147">See also</span></span>



[<span data-ttu-id="5ba43-148">IXPLogon::TransportLogoff</span><span class="sxs-lookup"><span data-stu-id="5ba43-148">IXPLogon::TransportLogoff</span></span>](ixplogon-transportlogoff.md)
  
[<span data-ttu-id="5ba43-149">IXPProvider::TransportLogon</span><span class="sxs-lookup"><span data-stu-id="5ba43-149">IXPProvider::TransportLogon</span></span>](ixpprovider-transportlogon.md)
  
[<span data-ttu-id="5ba43-150">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="5ba43-150">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="5ba43-151">IXPLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="5ba43-151">IXPLogon : IUnknown</span></span>](ixplogoniunknown.md)

