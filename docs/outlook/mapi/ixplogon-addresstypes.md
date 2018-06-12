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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: a7bb1aca501e24843950114bb76b6a09b20f2467
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776119"
---
# <a name="ixplogonaddresstypes"></a><span data-ttu-id="7a787-103">IXPLogon::AddressTypes</span><span class="sxs-lookup"><span data-stu-id="7a787-103">IXPLogon::AddressTypes</span></span>

  
  
<span data-ttu-id="7a787-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="7a787-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="7a787-105">返回的收件人的传输提供程序处理的类型。</span><span class="sxs-lookup"><span data-stu-id="7a787-105">Returns the types of recipients that the transport provider handles.</span></span>
  
```cpp
HRESULT AddressTypes(
  ULONG FAR * lpulFlags,
  ULONG FAR * lpcAdrType,
  LPSTR FAR * FAR * lpppszAdrTypeArray,
  ULONG FAR * lpcMAPIUID,
  LPUID FAR * FAR * lpppUIDArray
);
```

## <a name="parameters"></a><span data-ttu-id="7a787-106">参数</span><span class="sxs-lookup"><span data-stu-id="7a787-106">Parameters</span></span>

 <span data-ttu-id="7a787-107">_lpulFlags_</span><span class="sxs-lookup"><span data-stu-id="7a787-107">_lpulFlags_</span></span>
  
> <span data-ttu-id="7a787-108">[输出]返回控制的字符串类型的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="7a787-108">[out] A bitmask of flags that controls the type of strings returned.</span></span> <span data-ttu-id="7a787-109">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="7a787-109">The following flag can be set:</span></span>
    
<span data-ttu-id="7a787-110">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="7a787-110">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="7a787-111">返回的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="7a787-111">The returned strings are in Unicode format.</span></span> <span data-ttu-id="7a787-112">如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="7a787-112">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="7a787-113">_lpcAdrType_</span><span class="sxs-lookup"><span data-stu-id="7a787-113">_lpcAdrType_</span></span>
  
> <span data-ttu-id="7a787-114">[输出]一个指向_lpppszAdrTypeArray_参数指向该数组中的条目数。</span><span class="sxs-lookup"><span data-stu-id="7a787-114">[out] A pointer to the count of entries in the array pointed to by the  _lpppszAdrTypeArray_ parameter.</span></span> 
    
 <span data-ttu-id="7a787-115">_lpppszAdrTypeArray_</span><span class="sxs-lookup"><span data-stu-id="7a787-115">_lpppszAdrTypeArray_</span></span>
  
> <span data-ttu-id="7a787-116">[输出]指向为标识的收件人类型的字符串数组的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="7a787-116">[out] A pointer to a pointer to an array of strings that identify recipient types.</span></span>
    
 <span data-ttu-id="7a787-117">_lpcMAPIUID_</span><span class="sxs-lookup"><span data-stu-id="7a787-117">_lpcMAPIUID_</span></span>
  
> <span data-ttu-id="7a787-118">[输出]一个指向_lpppUIDArray_参数指向该数组中的条目数。</span><span class="sxs-lookup"><span data-stu-id="7a787-118">[out] A pointer to the count of entries in the array pointed to by the  _lpppUIDArray_ parameter.</span></span> 
    
 <span data-ttu-id="7a787-119">_lpppUIDArray_</span><span class="sxs-lookup"><span data-stu-id="7a787-119">_lpppUIDArray_</span></span>
  
> <span data-ttu-id="7a787-120">[输出]指向为数组指向[MAPIUID](mapiuid.md)结构标识的收件人类型的指针的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="7a787-120">[out] A pointer to a pointer to an array of pointers to [MAPIUID](mapiuid.md) structures that identify recipient types.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="7a787-121">返回值</span><span class="sxs-lookup"><span data-stu-id="7a787-121">Return value</span></span>

<span data-ttu-id="7a787-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="7a787-122">S_OK</span></span> 
  
> <span data-ttu-id="7a787-123">传输提供程序成功指明它可以处理的收件人的类型。</span><span class="sxs-lookup"><span data-stu-id="7a787-123">The transport provider successfully indicated the types of recipients that it can handle.</span></span>
    
## <a name="notes-to-implementers"></a><span data-ttu-id="7a787-124">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="7a787-124">Notes to implementers</span></span>

<span data-ttu-id="7a787-125">MAPI 后台处理程序调用**IXPLogon::AddressTypes**方法，以便传输提供程序可以指示处理哪些类型的收件人的传输提供程序返回从调用[IXPProvider::TransportLogon](ixpprovider-transportlogon.md)方法后立即。</span><span class="sxs-lookup"><span data-stu-id="7a787-125">The MAPI spooler calls the **IXPLogon::AddressTypes** method immediately after a transport provider returns from a call to the [IXPProvider::TransportLogon](ixpprovider-transportlogon.md) method so the transport provider can indicate what types of recipients it handles.</span></span> <span data-ttu-id="7a787-126">指示此，传输提供程序应_lpppszAdrTypeArray_参数中后将指针传递给数组指针为字符串，或_lpppUIDArray_参数中后将指针传递给数组指向**MAPIUID**结构或在这两个参数传递值。</span><span class="sxs-lookup"><span data-stu-id="7a787-126">To indicate this, the transport provider should pass back in the  _lpppszAdrTypeArray_ parameter a pointer to an array of pointers to strings, or pass back in the  _lpppUIDArray_ parameter a pointer to an array of pointers to **MAPIUID** structures, or pass values in both parameters.</span></span> 
  
<span data-ttu-id="7a787-127">以下两个数组用于不同标识过程。</span><span class="sxs-lookup"><span data-stu-id="7a787-127">These two arrays are used for different identification processes.</span></span> <span data-ttu-id="7a787-128">MAPI 和 MAPI 后台处理程序用于[MAPIUID](mapiuid.md)结构_lpppUIDArray_数组中标识的直接处理通过传输提供程序或消息系统传输提供程序连接到这些收件人的项标识符.</span><span class="sxs-lookup"><span data-stu-id="7a787-128">MAPI and the MAPI spooler use the [MAPIUID](mapiuid.md) structures in the  _lpppUIDArray_ array to identify those recipient entry identifiers that are directly handled by the transport provider or by the messaging system to which the transport provider connects.</span></span> <span data-ttu-id="7a787-129">MAPI 和 MAPI 后台处理程序都不使用任何这些**MAPIUID**结构; 中包含的项标识符展开地址这些结构仅用于收件人类型标识。</span><span class="sxs-lookup"><span data-stu-id="7a787-129">Neither MAPI nor the MAPI spooler expands addresses by using entry identifiers contained in any of these **MAPIUID** structures; these structures are used only for recipient type identification.</span></span> 
  
<span data-ttu-id="7a787-130">MAPI 后台处理程序使用每个字符串_lpppszAdrTypeArray_参数中的比较测试在决定哪些传输提供程序应处理出站邮件的收件人。</span><span class="sxs-lookup"><span data-stu-id="7a787-130">The MAPI spooler uses each of the strings in the  _lpppszAdrTypeArray_ parameter for a comparison test when it decides which transport provider should handle which recipients for an outbound message.</span></span> <span data-ttu-id="7a787-131">如果邮件收件人的**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) 属性与标识消息传输提供程序提供的地址类型之一的字符串完全匹配，提供程序可以将邮件传递给该收件人。</span><span class="sxs-lookup"><span data-stu-id="7a787-131">If a message recipient's **PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) property exactly matches a string that identifies one of the messaging address types that the transport provider supplies, the provider can deliver the message to that recipient.</span></span>
  
<span data-ttu-id="7a787-132">如果多个传输提供程序可以处理相同类型的收件人，MAPI 选择基于客户端应用程序的配置文件中所指示的传输优先级顺序传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="7a787-132">If multiple transport providers can handle the same type of recipient, MAPI selects a transport provider based on the transport priority order indicated in the client application's profile.</span></span> <span data-ttu-id="7a787-133">若要确定要使用的传输提供程序，MAPI 后台处理程序扫描优先级顺序中的所有提供程序指定**MAPIUID**结构，然后所有提供程序指定的地址类型值的优先级顺序。</span><span class="sxs-lookup"><span data-stu-id="7a787-133">To determine which transport provider to use, the MAPI spooler scans all provider-specified **MAPIUID** structures in priority order, and then all provider-specified address type values in priority order.</span></span> <span data-ttu-id="7a787-134">要匹配此扫描中的特定收件人的第一个传输提供程序获取处理此收件人的第一个机会。</span><span class="sxs-lookup"><span data-stu-id="7a787-134">The first transport provider to match a particular recipient in this scan gets the first opportunity to handle this recipient.</span></span> <span data-ttu-id="7a787-135">如果该提供商并不处理收件人，MAPI 后台处理程序将继续扫描尚未处理任何收件人查找传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="7a787-135">If that provider does not handle the recipient, the MAPI spooler continues the scan to find a transport provider for any recipient not yet handled.</span></span> <span data-ttu-id="7a787-136">直到找到没有进一步的匹配项，此时原件报告生成的未处理任何收件人，将继续扫描。</span><span class="sxs-lookup"><span data-stu-id="7a787-136">The scan continues until no further matches are found, at which point a nondelivery report is generated for any recipient that was not handled.</span></span> 
  
<span data-ttu-id="7a787-137">如果提供程序始终支持一组特定的收件人类型，可以是静态的地址类型和**MAPIUID**数组传递传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="7a787-137">If the provider always supports a particular set of recipient types, the address type and **MAPIUID** arrays that the transport provider passed can be static.</span></span> <span data-ttu-id="7a787-138">如果传输提供程序动态构造这些数组，它可以使用以前对**TransportLogon**的调用中传递的支持对象，尽管这是不必要分配内存。</span><span class="sxs-lookup"><span data-stu-id="7a787-138">If the transport provider dynamically constructs these arrays, it can allocate memory by using the support object that was previously passed in the call to **TransportLogon**, although this is not necessary.</span></span>
  
<span data-ttu-id="7a787-139">直到最后一个呼叫到[IXPLogon::TransportLogoff](ixplogon-transportlogoff.md)方法中，在这段时间传输提供程序可以释放内存，如有必要，用于地址类型和**MAPIUID**数组的内存应保持分配。</span><span class="sxs-lookup"><span data-stu-id="7a787-139">The memory used for the address type and **MAPIUID** arrays should remain allocated until the final call to the [IXPLogon::TransportLogoff](ixplogon-transportlogoff.md) method, at which time the transport provider can free the memory, if necessary.</span></span> <span data-ttu-id="7a787-140">返回从**TransportLogoff**呼叫之后，传输提供程序不应改变这些阵列的内容。</span><span class="sxs-lookup"><span data-stu-id="7a787-140">The transport provider should not alter the contents of these arrays after it returns from the **TransportLogoff** call.</span></span> 
  
<span data-ttu-id="7a787-141">传输提供程序可以处理任何类型的收件人可以在_lpppszAdrTypeArray_参数中返回 NULL。</span><span class="sxs-lookup"><span data-stu-id="7a787-141">A transport provider that can handle any type of recipient can return NULL in the  _lpppszAdrTypeArray_ parameter.</span></span> <span data-ttu-id="7a787-142">对于基于 LAN 的消息系统使用中央服务器通常将传出邮件传递到各种外部消息系统传输提供程序执行此操作。</span><span class="sxs-lookup"><span data-stu-id="7a787-142">Transport providers for LAN-based messaging systems that use a central server to deliver outgoing messages to various foreign message systems commonly do this.</span></span> <span data-ttu-id="7a787-143">此类型的传输提供程序应在 MAPI 和 MAPI 上次安装后台处理程序的配置文件中的传输提供程序的优先级顺序。</span><span class="sxs-lookup"><span data-stu-id="7a787-143">This type of transport provider should be installed last in the MAPI and MAPI spooler priority order of transport providers in the profile.</span></span> 
  
<span data-ttu-id="7a787-144">不支持与其根据地址类型调度的出站消息的传输提供程序应在_lpppszAdrTypeArray_中返回一个零长度字符串。</span><span class="sxs-lookup"><span data-stu-id="7a787-144">A transport provider that does not support outbound messages that are dispatched to it based on address type should return a single zero-length string in  _lpppszAdrTypeArray_.</span></span> <span data-ttu-id="7a787-145">如果传输提供程序支持无收件人类型，它应**MAPIUID**结构和地址类型为空字符串传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="7a787-145">If a transport provider supports no recipient types, it should pass NULL for the **MAPIUID** structure and an empty string for the address type.</span></span> <span data-ttu-id="7a787-146">此类型的传输提供程序通常用于安装消息预处理器。</span><span class="sxs-lookup"><span data-stu-id="7a787-146">Transport providers of this type are most commonly used to install a message preprocessor.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="7a787-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7a787-147">See also</span></span>



[<span data-ttu-id="7a787-148">IXPLogon::TransportLogoff</span><span class="sxs-lookup"><span data-stu-id="7a787-148">IXPLogon::TransportLogoff</span></span>](ixplogon-transportlogoff.md)
  
[<span data-ttu-id="7a787-149">IXPProvider::TransportLogon</span><span class="sxs-lookup"><span data-stu-id="7a787-149">IXPProvider::TransportLogon</span></span>](ixpprovider-transportlogon.md)
  
[<span data-ttu-id="7a787-150">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="7a787-150">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="7a787-151">IXPLogon: IUnknown</span><span class="sxs-lookup"><span data-stu-id="7a787-151">IXPLogon : IUnknown</span></span>](ixplogoniunknown.md)

