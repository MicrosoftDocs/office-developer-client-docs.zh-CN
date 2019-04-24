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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357209"
---
# <a name="ixplogonaddresstypes"></a><span data-ttu-id="50995-103">IXPLogon::AddressTypes</span><span class="sxs-lookup"><span data-stu-id="50995-103">IXPLogon::AddressTypes</span></span>

  
  
<span data-ttu-id="50995-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="50995-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="50995-105">返回传输提供程序处理的收件人的类型。</span><span class="sxs-lookup"><span data-stu-id="50995-105">Returns the types of recipients that the transport provider handles.</span></span>
  
```cpp
HRESULT AddressTypes(
  ULONG FAR * lpulFlags,
  ULONG FAR * lpcAdrType,
  LPSTR FAR * FAR * lpppszAdrTypeArray,
  ULONG FAR * lpcMAPIUID,
  LPUID FAR * FAR * lpppUIDArray
);
```

## <a name="parameters"></a><span data-ttu-id="50995-106">参数</span><span class="sxs-lookup"><span data-stu-id="50995-106">Parameters</span></span>

 <span data-ttu-id="50995-107">_lpulFlags_</span><span class="sxs-lookup"><span data-stu-id="50995-107">_lpulFlags_</span></span>
  
> <span data-ttu-id="50995-108">排除用于控制返回的字符串类型的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="50995-108">[out] A bitmask of flags that controls the type of strings returned.</span></span> <span data-ttu-id="50995-109">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="50995-109">The following flag can be set:</span></span>
    
<span data-ttu-id="50995-110">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="50995-110">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="50995-111">返回的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="50995-111">The returned strings are in Unicode format.</span></span> <span data-ttu-id="50995-112">如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="50995-112">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="50995-113">_lpcAdrType_</span><span class="sxs-lookup"><span data-stu-id="50995-113">_lpcAdrType_</span></span>
  
> <span data-ttu-id="50995-114">排除一个指针, 指向由_lpppszAdrTypeArray_参数指向的数组中的项的计数。</span><span class="sxs-lookup"><span data-stu-id="50995-114">[out] A pointer to the count of entries in the array pointed to by the  _lpppszAdrTypeArray_ parameter.</span></span> 
    
 <span data-ttu-id="50995-115">_lpppszAdrTypeArray_</span><span class="sxs-lookup"><span data-stu-id="50995-115">_lpppszAdrTypeArray_</span></span>
  
> <span data-ttu-id="50995-116">排除指向标识收件人类型的字符串数组的指针。</span><span class="sxs-lookup"><span data-stu-id="50995-116">[out] A pointer to a pointer to an array of strings that identify recipient types.</span></span>
    
 <span data-ttu-id="50995-117">_lpcMAPIUID_</span><span class="sxs-lookup"><span data-stu-id="50995-117">_lpcMAPIUID_</span></span>
  
> <span data-ttu-id="50995-118">排除一个指针, 指向由_lpppUIDArray_参数指向的数组中的项的计数。</span><span class="sxs-lookup"><span data-stu-id="50995-118">[out] A pointer to the count of entries in the array pointed to by the  _lpppUIDArray_ parameter.</span></span> 
    
 <span data-ttu-id="50995-119">_lpppUIDArray_</span><span class="sxs-lookup"><span data-stu-id="50995-119">_lpppUIDArray_</span></span>
  
> <span data-ttu-id="50995-120">排除指向指向[MAPIUID](mapiuid.md)结构的指针的指针的指针, 该数组标识收件人类型。</span><span class="sxs-lookup"><span data-stu-id="50995-120">[out] A pointer to a pointer to an array of pointers to [MAPIUID](mapiuid.md) structures that identify recipient types.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="50995-121">返回值</span><span class="sxs-lookup"><span data-stu-id="50995-121">Return value</span></span>

<span data-ttu-id="50995-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="50995-122">S_OK</span></span> 
  
> <span data-ttu-id="50995-123">传输提供程序已成功指示其可以处理的收件人类型。</span><span class="sxs-lookup"><span data-stu-id="50995-123">The transport provider successfully indicated the types of recipients that it can handle.</span></span>
    
## <a name="notes-to-implementers"></a><span data-ttu-id="50995-124">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="50995-124">Notes to implementers</span></span>

<span data-ttu-id="50995-125">MAPI 后台处理程序在从对[IXPProvider:: TransportLogon](ixpprovider-transportlogon.md)方法的调用返回后立即调用**IXPLogon:: AddressTypes**方法, 以便传输提供程序可以指示其处理的收件人类型。</span><span class="sxs-lookup"><span data-stu-id="50995-125">The MAPI spooler calls the **IXPLogon::AddressTypes** method immediately after a transport provider returns from a call to the [IXPProvider::TransportLogon](ixpprovider-transportlogon.md) method so the transport provider can indicate what types of recipients it handles.</span></span> <span data-ttu-id="50995-126">若要指明这一点, 传输提供程序应在_lpppszAdrTypeArray_参数中传递指向指向字符串的指针的指针, 或在_lpppUIDArray_参数中传回指向**MAPIUID**的指针的指针。结构或传递两个参数中的值。</span><span class="sxs-lookup"><span data-stu-id="50995-126">To indicate this, the transport provider should pass back in the  _lpppszAdrTypeArray_ parameter a pointer to an array of pointers to strings, or pass back in the  _lpppUIDArray_ parameter a pointer to an array of pointers to **MAPIUID** structures, or pass values in both parameters.</span></span> 
  
<span data-ttu-id="50995-127">这两个数组用于不同的标识过程。</span><span class="sxs-lookup"><span data-stu-id="50995-127">These two arrays are used for different identification processes.</span></span> <span data-ttu-id="50995-128">mapi 和 mapi 后台处理程序使用_lpppUIDArray_数组中的[MAPIUID](mapiuid.md)结构来标识那些由传输提供程序或由传输提供程序连接的邮件系统直接处理的收件人条目标识符。.</span><span class="sxs-lookup"><span data-stu-id="50995-128">MAPI and the MAPI spooler use the [MAPIUID](mapiuid.md) structures in the  _lpppUIDArray_ array to identify those recipient entry identifiers that are directly handled by the transport provider or by the messaging system to which the transport provider connects.</span></span> <span data-ttu-id="50995-129">mapi 和 mapi 后台处理程序都不通过使用其中任何一个**MAPIUID**结构中包含的条目标识符来展开地址;这些结构仅用于收件人类型标识。</span><span class="sxs-lookup"><span data-stu-id="50995-129">Neither MAPI nor the MAPI spooler expands addresses by using entry identifiers contained in any of these **MAPIUID** structures; these structures are used only for recipient type identification.</span></span> 
  
<span data-ttu-id="50995-130">MAPI 后台处理程序使用_lpppszAdrTypeArray_参数中的每个字符串进行比较, 以便在决定哪种传输提供程序处理出站邮件的收件人时进行比较测试。</span><span class="sxs-lookup"><span data-stu-id="50995-130">The MAPI spooler uses each of the strings in the  _lpppszAdrTypeArray_ parameter for a comparison test when it decides which transport provider should handle which recipients for an outbound message.</span></span> <span data-ttu-id="50995-131">如果邮件收件人的**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) 属性与标识传输提供程序提供的邮件地址类型之一的字符串完全匹配, 则提供程序可以将邮件传递给该收件人。</span><span class="sxs-lookup"><span data-stu-id="50995-131">If a message recipient's **PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) property exactly matches a string that identifies one of the messaging address types that the transport provider supplies, the provider can deliver the message to that recipient.</span></span>
  
<span data-ttu-id="50995-132">如果多个传输提供程序可以处理相同类型的收件人, MAPI 将根据客户端应用程序配置文件中指示的传输优先级顺序选择传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="50995-132">If multiple transport providers can handle the same type of recipient, MAPI selects a transport provider based on the transport priority order indicated in the client application's profile.</span></span> <span data-ttu-id="50995-133">若要确定要使用的传输提供程序, MAPI 后台处理程序将按优先级顺序扫描所有提供程序指定的**MAPIUID**结构, 然后按优先级顺序扫描所有提供程序指定的地址类型值。</span><span class="sxs-lookup"><span data-stu-id="50995-133">To determine which transport provider to use, the MAPI spooler scans all provider-specified **MAPIUID** structures in priority order, and then all provider-specified address type values in priority order.</span></span> <span data-ttu-id="50995-134">第一个与此扫描中的特定收件人相匹配的传输提供程序将获得第一个处理此收件人的机会。</span><span class="sxs-lookup"><span data-stu-id="50995-134">The first transport provider to match a particular recipient in this scan gets the first opportunity to handle this recipient.</span></span> <span data-ttu-id="50995-135">如果该提供程序未处理收件人, MAPI 后台处理程序将继续扫描, 以查找任何尚未处理的收件人的传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="50995-135">If that provider does not handle the recipient, the MAPI spooler continues the scan to find a transport provider for any recipient not yet handled.</span></span> <span data-ttu-id="50995-136">扫描将继续下去, 直到找不到更多的匹配项, 此时将为未处理的任何收件人生成 nondelivery 报告。</span><span class="sxs-lookup"><span data-stu-id="50995-136">The scan continues until no further matches are found, at which point a nondelivery report is generated for any recipient that was not handled.</span></span> 
  
<span data-ttu-id="50995-137">如果提供程序始终支持一组特定的收件人类型, 则传输提供程序传递的地址类型和**MAPIUID**数组可以是静态的。</span><span class="sxs-lookup"><span data-stu-id="50995-137">If the provider always supports a particular set of recipient types, the address type and **MAPIUID** arrays that the transport provider passed can be static.</span></span> <span data-ttu-id="50995-138">如果传输提供程序动态地构造这些数组, 则它可以使用之前在**TransportLogon**中传递的支持对象分配内存, 尽管这并不是必需的。</span><span class="sxs-lookup"><span data-stu-id="50995-138">If the transport provider dynamically constructs these arrays, it can allocate memory by using the support object that was previously passed in the call to **TransportLogon**, although this is not necessary.</span></span>
  
<span data-ttu-id="50995-139">用于地址类型和**MAPIUID**数组的内存应一直分配到[IXPLogon:: TransportLogoff](ixplogon-transportlogoff.md)方法的最后一次调用, 此时传输提供程序可以释放内存 (如有必要)。</span><span class="sxs-lookup"><span data-stu-id="50995-139">The memory used for the address type and **MAPIUID** arrays should remain allocated until the final call to the [IXPLogon::TransportLogoff](ixplogon-transportlogoff.md) method, at which time the transport provider can free the memory, if necessary.</span></span> <span data-ttu-id="50995-140">在从**TransportLogoff**调用返回之后, 传输提供程序不应更改这些数组的内容。</span><span class="sxs-lookup"><span data-stu-id="50995-140">The transport provider should not alter the contents of these arrays after it returns from the **TransportLogoff** call.</span></span> 
  
<span data-ttu-id="50995-141">可以处理任何类型的收件人的传输提供程序可以在_lpppszAdrTypeArray_参数中返回 NULL。</span><span class="sxs-lookup"><span data-stu-id="50995-141">A transport provider that can handle any type of recipient can return NULL in the  _lpppszAdrTypeArray_ parameter.</span></span> <span data-ttu-id="50995-142">使用中央服务器将传出邮件传递给各种外部邮件系统的基于 LAN 的邮件系统的传输提供程序通常会执行此操作。</span><span class="sxs-lookup"><span data-stu-id="50995-142">Transport providers for LAN-based messaging systems that use a central server to deliver outgoing messages to various foreign message systems commonly do this.</span></span> <span data-ttu-id="50995-143">此类型的传输提供程序应在配置文件中的传输提供程序的 mapi 和 mapi 后台处理程序优先级顺序中进行最后安装。</span><span class="sxs-lookup"><span data-stu-id="50995-143">This type of transport provider should be installed last in the MAPI and MAPI spooler priority order of transport providers in the profile.</span></span> 
  
<span data-ttu-id="50995-144">如果传输提供程序不支持根据地址类型为其分派的出站邮件, 则应在_lpppszAdrTypeArray_中返回单个零长度字符串。</span><span class="sxs-lookup"><span data-stu-id="50995-144">A transport provider that does not support outbound messages that are dispatched to it based on address type should return a single zero-length string in  _lpppszAdrTypeArray_.</span></span> <span data-ttu-id="50995-145">如果传输提供程序不支持任何收件人类型, 则它应为**MAPIUID**结构传递 NULL, 并为该地址类型传递一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="50995-145">If a transport provider supports no recipient types, it should pass NULL for the **MAPIUID** structure and an empty string for the address type.</span></span> <span data-ttu-id="50995-146">此类型的传输提供程序最常用于安装消息预处理器。</span><span class="sxs-lookup"><span data-stu-id="50995-146">Transport providers of this type are most commonly used to install a message preprocessor.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="50995-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="50995-147">See also</span></span>



[<span data-ttu-id="50995-148">IXPLogon::TransportLogoff</span><span class="sxs-lookup"><span data-stu-id="50995-148">IXPLogon::TransportLogoff</span></span>](ixplogon-transportlogoff.md)
  
[<span data-ttu-id="50995-149">IXPProvider::TransportLogon</span><span class="sxs-lookup"><span data-stu-id="50995-149">IXPProvider::TransportLogon</span></span>](ixpprovider-transportlogon.md)
  
[<span data-ttu-id="50995-150">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="50995-150">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="50995-151">IXPLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="50995-151">IXPLogon : IUnknown</span></span>](ixplogoniunknown.md)

