---
title: ENTRYID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.ENTRYID
api_type:
- COM
ms.assetid: 8ebb21ca-5ad1-4dcc-97b6-2390664b5d8d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8540176b7675917dde7c618c40142605e9622282
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22586219"
---
# <a name="entryid"></a><span data-ttu-id="65bde-103">ENTRYID</span><span class="sxs-lookup"><span data-stu-id="65bde-103">ENTRYID</span></span>

  
  
<span data-ttu-id="65bde-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="65bde-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="65bde-105">包含一个 MAPI 对象的项标识符。</span><span class="sxs-lookup"><span data-stu-id="65bde-105">Contains an entry identifier for a MAPI object.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="65bde-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="65bde-106">Header file:</span></span>  <br/> |<span data-ttu-id="65bde-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="65bde-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="65bde-108">相关的宏：</span><span class="sxs-lookup"><span data-stu-id="65bde-108">Related macros:</span></span>  <br/> |<span data-ttu-id="65bde-109">[CbNewENTRYID](cbnewentryid.md) [SizedENTRYID](sizedentryid.md)</span><span class="sxs-lookup"><span data-stu-id="65bde-109">[CbNewENTRYID](cbnewentryid.md), [SizedENTRYID](sizedentryid.md)</span></span> <br/> |
   
```cpp
typedef struct
{
  BYTE abFlags[4];
  BYTE ab[MAPI_DIM];
} ENTRYID, FAR *LPENTRYID;

```

## <a name="members"></a><span data-ttu-id="65bde-110">Members</span><span class="sxs-lookup"><span data-stu-id="65bde-110">Members</span></span>

 <span data-ttu-id="65bde-111">**abFlags**</span><span class="sxs-lookup"><span data-stu-id="65bde-111">**abFlags**</span></span>
  
> <span data-ttu-id="65bde-112">提供描述对象的信息的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="65bde-112">Bitmask of flags that provide information that describes the object.</span></span> <span data-ttu-id="65bde-113">仅的第一个字节的标志， **abFlags [0]**，可以设置提供程序;保留其他三个。</span><span class="sxs-lookup"><span data-stu-id="65bde-113">Only the first byte of the flags, **abFlags[0]**, may be set by the provider; the other three are reserved.</span></span> <span data-ttu-id="65bde-114">永久的项标识符; 不能设置这些标志它们仅短期项标识符的设置。</span><span class="sxs-lookup"><span data-stu-id="65bde-114">These flags must not be set for permanent entry identifiers; they are only set for short-term entry identifiers.</span></span> <span data-ttu-id="65bde-115">向客户端，此结构是只读的。</span><span class="sxs-lookup"><span data-stu-id="65bde-115">To clients, this structure is read-only.</span></span> <span data-ttu-id="65bde-116">可以在**abFlags [0]** 设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="65bde-116">The following flags can be set in **abFlags[0]**:</span></span>
    
<span data-ttu-id="65bde-117">MAPI_NOTRECIP</span><span class="sxs-lookup"><span data-stu-id="65bde-117">MAPI_NOTRECIP</span></span> 
  
> <span data-ttu-id="65bde-118">项标识符不能用作邮件收件人。</span><span class="sxs-lookup"><span data-stu-id="65bde-118">The entry identifier cannot be used as a recipient on a message.</span></span>
    
<span data-ttu-id="65bde-119">MAPI_NOTRESERVED</span><span class="sxs-lookup"><span data-stu-id="65bde-119">MAPI_NOTRESERVED</span></span> 
  
> <span data-ttu-id="65bde-120">其他用户无法访问的项标识符。</span><span class="sxs-lookup"><span data-stu-id="65bde-120">Other users cannot access the entry identifier.</span></span>
    
<span data-ttu-id="65bde-121">MAPI_NOW</span><span class="sxs-lookup"><span data-stu-id="65bde-121">MAPI_NOW</span></span> 
  
> <span data-ttu-id="65bde-122">不能在其他情况下使用的项标识符。</span><span class="sxs-lookup"><span data-stu-id="65bde-122">The entry identifier cannot be used at other times.</span></span>
    
<span data-ttu-id="65bde-123">MAPI_SHORTTERM</span><span class="sxs-lookup"><span data-stu-id="65bde-123">MAPI_SHORTTERM</span></span> 
  
> <span data-ttu-id="65bde-124">短期的项标识符。</span><span class="sxs-lookup"><span data-stu-id="65bde-124">The entry identifier is short-term.</span></span> <span data-ttu-id="65bde-125">必须设置此字节中的所有其他值，除非已启用的项标识符的其他用途。</span><span class="sxs-lookup"><span data-stu-id="65bde-125">All other values in this byte must be set unless other uses of the entry identifier are enabled.</span></span>
    
<span data-ttu-id="65bde-126">MAPI_THISSESSION</span><span class="sxs-lookup"><span data-stu-id="65bde-126">MAPI_THISSESSION</span></span> 
  
> <span data-ttu-id="65bde-127">不能在其他会话上使用的项标识符。</span><span class="sxs-lookup"><span data-stu-id="65bde-127">The entry identifier cannot be used on other sessions.</span></span>
    
 <span data-ttu-id="65bde-128">**ab**</span><span class="sxs-lookup"><span data-stu-id="65bde-128">**ab**</span></span>
  
> <span data-ttu-id="65bde-129">指示由服务提供商的二进制数据的数组。</span><span class="sxs-lookup"><span data-stu-id="65bde-129">Indicates an array of binary data that is used by service providers.</span></span> <span data-ttu-id="65bde-130">客户端应用程序不能使用此数组。</span><span class="sxs-lookup"><span data-stu-id="65bde-130">The client application cannot use this array.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="65bde-131">注解</span><span class="sxs-lookup"><span data-stu-id="65bde-131">Remarks</span></span>

<span data-ttu-id="65bde-132">**ENTRYID**结构由消息存储和通讯簿提供程序来构造为它们的对象的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="65bde-132">The **ENTRYID** structure is used by message store and address book providers to construct unique identifiers for their objects.</span></span> <span data-ttu-id="65bde-133">条目标识符可用于确定以下类型的对象：</span><span class="sxs-lookup"><span data-stu-id="65bde-133">Entry identifiers are used to identify the following types of objects:</span></span> 
  
- <span data-ttu-id="65bde-134">消息存储库</span><span class="sxs-lookup"><span data-stu-id="65bde-134">Message stores</span></span>
    
- <span data-ttu-id="65bde-135">Folders</span><span class="sxs-lookup"><span data-stu-id="65bde-135">Folders</span></span>
    
- <span data-ttu-id="65bde-136">邮件</span><span class="sxs-lookup"><span data-stu-id="65bde-136">Messages</span></span>
    
- <span data-ttu-id="65bde-137">通讯簿容器</span><span class="sxs-lookup"><span data-stu-id="65bde-137">Address book containers</span></span>
    
- <span data-ttu-id="65bde-138">通讯组列表</span><span class="sxs-lookup"><span data-stu-id="65bde-138">Distribution lists</span></span>
    
- <span data-ttu-id="65bde-139">邮件用户</span><span class="sxs-lookup"><span data-stu-id="65bde-139">Messaging users</span></span>
    
- <span data-ttu-id="65bde-140">状态对象</span><span class="sxs-lookup"><span data-stu-id="65bde-140">Status objects</span></span>
    
- <span data-ttu-id="65bde-141">配置文件节</span><span class="sxs-lookup"><span data-stu-id="65bde-141">Profile sections</span></span>
    
<span data-ttu-id="65bde-142">每个提供程序使用的提供程序有意义的**ENTRYID**结构格式。</span><span class="sxs-lookup"><span data-stu-id="65bde-142">Each provider uses a format for the **ENTRYID** structure that makes sense for that provider.</span></span> 
  
<span data-ttu-id="65bde-143">不能直接对条目标识符进行比较，因为一个对象可以由两个不同的二进制值表示。</span><span class="sxs-lookup"><span data-stu-id="65bde-143">Entry identifiers cannot be compared directly because one object can be represented by two different binary values.</span></span> <span data-ttu-id="65bde-144">若要确定两个条目标识符是否表示同一个对象，调用[IMAPISession::CompareEntryIDs](imapisession-compareentryids.md)方法。</span><span class="sxs-lookup"><span data-stu-id="65bde-144">To determine whether two entry identifiers represent the same object, call the [IMAPISession::CompareEntryIDs](imapisession-compareentryids.md) method.</span></span> 
  
<span data-ttu-id="65bde-145">当客户端调用对象的[IMAPIProp::GetProps](imapiprop-getprops.md)方法来检索其条目标识符时，该对象返回的项标识符的最永久窗体。</span><span class="sxs-lookup"><span data-stu-id="65bde-145">When a client calls an object's [IMAPIProp::GetProps](imapiprop-getprops.md) method to retrieve its entry identifier, the object returns the most permanent form of the entry identifier.</span></span> <span data-ttu-id="65bde-146">客户端可以确认条目标识符长期通过检查**abFlags**成员的第一个字节设置任何标志。</span><span class="sxs-lookup"><span data-stu-id="65bde-146">A client can verify that an entry identifier is long-term by checking that none of the flags are set in the first byte of the **abFlags** member.</span></span> 
  
<span data-ttu-id="65bde-147">当客户端访问条目标识符通过最可能此条目标识符是短期而不是长期表中的列。</span><span class="sxs-lookup"><span data-stu-id="65bde-147">When a client accesses an entry identifier through a column in a table, most likely this entry identifier is short-term instead of long-term.</span></span> <span data-ttu-id="65bde-148">短期条目标识符可用于仅在当前的 MAPI 会话中打开其相应的对象。</span><span class="sxs-lookup"><span data-stu-id="65bde-148">Short-term entry identifiers can be used to open their corresponding objects only in the current MAPI session.</span></span> <span data-ttu-id="65bde-149">客户端可以确认条目标识符短期通过检查所有标记中的第一个字节**abFlags**成员的设置。</span><span class="sxs-lookup"><span data-stu-id="65bde-149">A client can verify that an entry identifier is short-term by checking that all of the flags are set in the first byte of the **abFlags** member.</span></span> 
  
<span data-ttu-id="65bde-150">某些条目标识符短期，但具有长期使用。</span><span class="sxs-lookup"><span data-stu-id="65bde-150">Some entry identifiers are short-term, but have long-term use.</span></span> <span data-ttu-id="65bde-151">此类条目标识符将有一个或多个设置其**abFlags**成员的第一个字节中的相应标志。</span><span class="sxs-lookup"><span data-stu-id="65bde-151">Such an entry identifier will have one or more of the appropriate flags set in the first byte of its **abFlags** member.</span></span> 
  
<span data-ttu-id="65bde-152">**ENTRYID**结构类似于[FLATENTRY](flatentry.md)结构。</span><span class="sxs-lookup"><span data-stu-id="65bde-152">An **ENTRYID** structure resembles a [FLATENTRY](flatentry.md) structure.</span></span> <span data-ttu-id="65bde-153">但是，有一些区别：</span><span class="sxs-lookup"><span data-stu-id="65bde-153">However, there are some differences:</span></span> 
  
- <span data-ttu-id="65bde-154">**ENTRYID**结构不存储的项标识符; 的大小**FLATENTRY**结构执行。</span><span class="sxs-lookup"><span data-stu-id="65bde-154">An **ENTRYID** structure does not store the size of the entry identifier; a **FLATENTRY** structure does.</span></span> 
    
- <span data-ttu-id="65bde-155">**ENTRYID**结构单独; 存储标志数据和项标识符的其余部分**FLATENTRY**结构用于存储与项标识符的其余部分标志数据。</span><span class="sxs-lookup"><span data-stu-id="65bde-155">An **ENTRYID** structure stores the flag data and the rest of the entry identifier separately; a **FLATENTRY** structure stores the flag data with the rest of the entry identifier.</span></span> 
    
- <span data-ttu-id="65bde-156">到[IMAPIProp](imapipropiunknown.md)接口的方法和以下**OpenEntry**方法，作为参数传递的**ENTRYID**结构： [IABLogon::OpenEntry](iablogon-openentry.md)， [IAddrBook::OpenEntry](iaddrbook-openentry.md)， [IMAPIContainer::OpenEntry](imapicontainer-openentry.md)， [IMAPISession::OpenEntry](imapisession-openentry.md) [IMAPISupport::OpenEntry](imapisupport-openentry.md)、 [IMsgStore::OpenEntry](imsgstore-openentry.md)、 [IMSLogon::OpenEntry](imslogon-openentry.md)</span><span class="sxs-lookup"><span data-stu-id="65bde-156">An **ENTRYID** structure is passed as a parameter to the methods of the [IMAPIProp](imapipropiunknown.md) interface and to the following **OpenEntry** methods: [IABLogon::OpenEntry](iablogon-openentry.md), [IAddrBook::OpenEntry](iaddrbook-openentry.md), [IMAPIContainer::OpenEntry](imapicontainer-openentry.md), [IMAPISession::OpenEntry](imapisession-openentry.md), [IMAPISupport::OpenEntry](imapisupport-openentry.md), [IMsgStore::OpenEntry](imsgstore-openentry.md), [IMSLogon::OpenEntry](imslogon-openentry.md)</span></span>
    
- <span data-ttu-id="65bde-157">**ENTRYID**结构用于存储在磁盘上的项标识符。</span><span class="sxs-lookup"><span data-stu-id="65bde-157">An **ENTRYID** structure is used to store an entry identifier on disk.</span></span> <span data-ttu-id="65bde-158">**FLATENTRY**结构用于存储在文件中的项标识符，或将其传递中的字节流。</span><span class="sxs-lookup"><span data-stu-id="65bde-158">A **FLATENTRY** structure is used to store an entry identifier in a file or pass it in a stream of bytes.</span></span> 
    
<span data-ttu-id="65bde-159">客户端应始终传入自然地对齐的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="65bde-159">Clients should always pass in naturally aligned entry identifiers.</span></span> <span data-ttu-id="65bde-160">虽然提供程序应处理任意位置对齐的项标识符，但是客户端不应期望此行为。</span><span class="sxs-lookup"><span data-stu-id="65bde-160">Although providers should handle arbitrarily aligned entry identifiers, clients should not expect this behavior.</span></span> <span data-ttu-id="65bde-161">未能将良好对齐的条目标识符传递给方法会导致对齐错误 RISC 处理器。</span><span class="sxs-lookup"><span data-stu-id="65bde-161">Failure to pass a good aligned entry identifier to a method can cause an alignment fault on RISC processors.</span></span> 
  
<span data-ttu-id="65bde-162">自然对齐因素，通常为 8 个字节，是 CPU、 支持的最大数据类型和通常由系统内存分配程序相同的对齐方式系数。</span><span class="sxs-lookup"><span data-stu-id="65bde-162">The natural alignment factor, typically 8 bytes, is the largest data type supported by the CPU, and usually the same alignment factor used by the system memory allocator.</span></span> <span data-ttu-id="65bde-163">自然地对齐的内存地址允许 CPU 访问它支持在该地址不生成对齐错误任何数据类型。</span><span class="sxs-lookup"><span data-stu-id="65bde-163">A naturally aligned memory address allows the CPU to access any data type it supports at that address without generating an alignment fault.</span></span> <span data-ttu-id="65bde-164">为 RISC Cpu 大小 N 的字节数的数据类型必须通常对齐上 N 个字节，甚至多正在从偶数多的地址</span><span class="sxs-lookup"><span data-stu-id="65bde-164">For RISC CPUs, a data type of size N bytes must usually be aligned on an even multiple of N bytes, with the address being an even multiple of N.</span></span>
  
<span data-ttu-id="65bde-165">有关详细信息，请参阅[项标识符](mapi-entry-identifiers.md)。</span><span class="sxs-lookup"><span data-stu-id="65bde-165">For more information, see [Entry Identifiers](mapi-entry-identifiers.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="65bde-166">另请参阅</span><span class="sxs-lookup"><span data-stu-id="65bde-166">See also</span></span>



[<span data-ttu-id="65bde-167">FLATENTRY</span><span class="sxs-lookup"><span data-stu-id="65bde-167">FLATENTRY</span></span>](flatentry.md)
  
[<span data-ttu-id="65bde-168">IMAPISupport::CompareEntryIDs</span><span class="sxs-lookup"><span data-stu-id="65bde-168">IMAPISupport::CompareEntryIDs</span></span>](imapisupport-compareentryids.md)
  
[<span data-ttu-id="65bde-169">PidTagRecordKey 规范属性</span><span class="sxs-lookup"><span data-stu-id="65bde-169">PidTagRecordKey Canonical Property</span></span>](pidtagrecordkey-canonical-property.md)


[<span data-ttu-id="65bde-170">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="65bde-170">MAPI Structures</span></span>](mapi-structures.md)

