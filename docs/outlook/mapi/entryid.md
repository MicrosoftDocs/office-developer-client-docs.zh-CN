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
ms.openlocfilehash: c77acb5226361ce31a7f6b1694de7fe23f8dd71b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315986"
---
# <a name="entryid"></a><span data-ttu-id="45e99-103">ENTRYID</span><span class="sxs-lookup"><span data-stu-id="45e99-103">ENTRYID</span></span>

  
  
<span data-ttu-id="45e99-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="45e99-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="45e99-105">包含 MAPI 对象的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="45e99-105">Contains an entry identifier for a MAPI object.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="45e99-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="45e99-106">Header file:</span></span>  <br/> |<span data-ttu-id="45e99-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="45e99-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="45e99-108">相关宏:</span><span class="sxs-lookup"><span data-stu-id="45e99-108">Related macros:</span></span>  <br/> |<span data-ttu-id="45e99-109">[CbNewENTRYID](cbnewentryid.md)、 [SizedENTRYID](sizedentryid.md)</span><span class="sxs-lookup"><span data-stu-id="45e99-109">[CbNewENTRYID](cbnewentryid.md), [SizedENTRYID](sizedentryid.md)</span></span> <br/> |
   
```cpp
typedef struct
{
  BYTE abFlags[4];
  BYTE ab[MAPI_DIM];
} ENTRYID, FAR *LPENTRYID;

```

## <a name="members"></a><span data-ttu-id="45e99-110">Members</span><span class="sxs-lookup"><span data-stu-id="45e99-110">Members</span></span>

 <span data-ttu-id="45e99-111">**abFlags**</span><span class="sxs-lookup"><span data-stu-id="45e99-111">**abFlags**</span></span>
  
> <span data-ttu-id="45e99-112">提供描述对象的信息的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="45e99-112">Bitmask of flags that provide information that describes the object.</span></span> <span data-ttu-id="45e99-113">仅可由提供程序设置**abFlags [0]** 标志的第一个字节;另外三个是保留的。</span><span class="sxs-lookup"><span data-stu-id="45e99-113">Only the first byte of the flags, **abFlags[0]**, may be set by the provider; the other three are reserved.</span></span> <span data-ttu-id="45e99-114">不得为永久条目标识符设置这些标志;仅对短期条目标识符设置这些设置。</span><span class="sxs-lookup"><span data-stu-id="45e99-114">These flags must not be set for permanent entry identifiers; they are only set for short-term entry identifiers.</span></span> <span data-ttu-id="45e99-115">对于客户端, 此结构是只读的。</span><span class="sxs-lookup"><span data-stu-id="45e99-115">To clients, this structure is read-only.</span></span> <span data-ttu-id="45e99-116">可以在**abFlags [0]** 中设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="45e99-116">The following flags can be set in **abFlags[0]**:</span></span>
    
<span data-ttu-id="45e99-117">MAPI_NOTRECIP</span><span class="sxs-lookup"><span data-stu-id="45e99-117">MAPI_NOTRECIP</span></span> 
  
> <span data-ttu-id="45e99-118">条目标识符不能用作邮件的收件人。</span><span class="sxs-lookup"><span data-stu-id="45e99-118">The entry identifier cannot be used as a recipient on a message.</span></span>
    
<span data-ttu-id="45e99-119">MAPI_NOTRESERVED</span><span class="sxs-lookup"><span data-stu-id="45e99-119">MAPI_NOTRESERVED</span></span> 
  
> <span data-ttu-id="45e99-120">其他用户无法访问条目标识符。</span><span class="sxs-lookup"><span data-stu-id="45e99-120">Other users cannot access the entry identifier.</span></span>
    
<span data-ttu-id="45e99-121">MAPI_NOW</span><span class="sxs-lookup"><span data-stu-id="45e99-121">MAPI_NOW</span></span> 
  
> <span data-ttu-id="45e99-122">不能在其他时间使用条目标识符。</span><span class="sxs-lookup"><span data-stu-id="45e99-122">The entry identifier cannot be used at other times.</span></span>
    
<span data-ttu-id="45e99-123">MAPI_SHORTTERM</span><span class="sxs-lookup"><span data-stu-id="45e99-123">MAPI_SHORTTERM</span></span> 
  
> <span data-ttu-id="45e99-124">条目标识符是短期的。</span><span class="sxs-lookup"><span data-stu-id="45e99-124">The entry identifier is short-term.</span></span> <span data-ttu-id="45e99-125">除非启用了条目标识符的其他使用, 否则必须设置此字节中的所有其他值。</span><span class="sxs-lookup"><span data-stu-id="45e99-125">All other values in this byte must be set unless other uses of the entry identifier are enabled.</span></span>
    
<span data-ttu-id="45e99-126">MAPI_THISSESSION</span><span class="sxs-lookup"><span data-stu-id="45e99-126">MAPI_THISSESSION</span></span> 
  
> <span data-ttu-id="45e99-127">条目标识符不能用于其他会话。</span><span class="sxs-lookup"><span data-stu-id="45e99-127">The entry identifier cannot be used on other sessions.</span></span>
    
 <span data-ttu-id="45e99-128">**ab**</span><span class="sxs-lookup"><span data-stu-id="45e99-128">**ab**</span></span>
  
> <span data-ttu-id="45e99-129">指示服务提供程序使用的二进制数据数组。</span><span class="sxs-lookup"><span data-stu-id="45e99-129">Indicates an array of binary data that is used by service providers.</span></span> <span data-ttu-id="45e99-130">客户端应用程序无法使用此数组。</span><span class="sxs-lookup"><span data-stu-id="45e99-130">The client application cannot use this array.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="45e99-131">注解</span><span class="sxs-lookup"><span data-stu-id="45e99-131">Remarks</span></span>

<span data-ttu-id="45e99-132">" **ENTRYID** " 结构由邮件存储和通讯簿提供程序用于为其对象构造唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="45e99-132">The **ENTRYID** structure is used by message store and address book providers to construct unique identifiers for their objects.</span></span> <span data-ttu-id="45e99-133">条目标识符用于标识以下类型的对象:</span><span class="sxs-lookup"><span data-stu-id="45e99-133">Entry identifiers are used to identify the following types of objects:</span></span> 
  
- <span data-ttu-id="45e99-134">邮件存储</span><span class="sxs-lookup"><span data-stu-id="45e99-134">Message stores</span></span>
    
- <span data-ttu-id="45e99-135">文件夹</span><span class="sxs-lookup"><span data-stu-id="45e99-135">Folders</span></span>
    
- <span data-ttu-id="45e99-136">邮件</span><span class="sxs-lookup"><span data-stu-id="45e99-136">Messages</span></span>
    
- <span data-ttu-id="45e99-137">通讯簿容器</span><span class="sxs-lookup"><span data-stu-id="45e99-137">Address book containers</span></span>
    
- <span data-ttu-id="45e99-138">通讯组列表</span><span class="sxs-lookup"><span data-stu-id="45e99-138">Distribution lists</span></span>
    
- <span data-ttu-id="45e99-139">邮件用户</span><span class="sxs-lookup"><span data-stu-id="45e99-139">Messaging users</span></span>
    
- <span data-ttu-id="45e99-140">状态对象</span><span class="sxs-lookup"><span data-stu-id="45e99-140">Status objects</span></span>
    
- <span data-ttu-id="45e99-141">配置文件节</span><span class="sxs-lookup"><span data-stu-id="45e99-141">Profile sections</span></span>
    
<span data-ttu-id="45e99-142">每个提供程序都使用对该提供商有意义的**ENTRYID**结构的格式。</span><span class="sxs-lookup"><span data-stu-id="45e99-142">Each provider uses a format for the **ENTRYID** structure that makes sense for that provider.</span></span> 
  
<span data-ttu-id="45e99-143">不能直接对条目标识符进行比较，因为一个对象可以由两个不同的二进制值表示。</span><span class="sxs-lookup"><span data-stu-id="45e99-143">Entry identifiers cannot be compared directly because one object can be represented by two different binary values.</span></span> <span data-ttu-id="45e99-144">若要确定两个条目标识符是否表示同一个对象, 请调用[IMAPISession:: CompareEntryIDs](imapisession-compareentryids.md)方法。</span><span class="sxs-lookup"><span data-stu-id="45e99-144">To determine whether two entry identifiers represent the same object, call the [IMAPISession::CompareEntryIDs](imapisession-compareentryids.md) method.</span></span> 
  
<span data-ttu-id="45e99-145">当客户端调用对象的[IMAPIProp:: GetProps](imapiprop-getprops.md)方法以检索其条目标识符时, 该对象将返回条目标识符的最永久的形式。</span><span class="sxs-lookup"><span data-stu-id="45e99-145">When a client calls an object's [IMAPIProp::GetProps](imapiprop-getprops.md) method to retrieve its entry identifier, the object returns the most permanent form of the entry identifier.</span></span> <span data-ttu-id="45e99-146">客户端可以通过检查**abFlags**成员的第一个字节中是否未设置任何标志来验证条目标识符是否为长期。</span><span class="sxs-lookup"><span data-stu-id="45e99-146">A client can verify that an entry identifier is long-term by checking that none of the flags are set in the first byte of the **abFlags** member.</span></span> 
  
<span data-ttu-id="45e99-147">当客户端通过表中的列访问条目标识符时, 很可能此条目标识符是短期的, 而不是长期。</span><span class="sxs-lookup"><span data-stu-id="45e99-147">When a client accesses an entry identifier through a column in a table, most likely this entry identifier is short-term instead of long-term.</span></span> <span data-ttu-id="45e99-148">短期条目标识符可用于仅在当前 MAPI 会话中打开其对应的对象。</span><span class="sxs-lookup"><span data-stu-id="45e99-148">Short-term entry identifiers can be used to open their corresponding objects only in the current MAPI session.</span></span> <span data-ttu-id="45e99-149">客户端可以通过检查**abFlags**成员的第一个字节中是否设置了所有标志来验证条目标识符是否为短期。</span><span class="sxs-lookup"><span data-stu-id="45e99-149">A client can verify that an entry identifier is short-term by checking that all of the flags are set in the first byte of the **abFlags** member.</span></span> 
  
<span data-ttu-id="45e99-150">某些条目标识符是短期的, 但长期使用。</span><span class="sxs-lookup"><span data-stu-id="45e99-150">Some entry identifiers are short-term, but have long-term use.</span></span> <span data-ttu-id="45e99-151">这样的条目标识符将具有一个或多个在其**abFlags**成员的第一个字节中设置的合适的标志。</span><span class="sxs-lookup"><span data-stu-id="45e99-151">Such an entry identifier will have one or more of the appropriate flags set in the first byte of its **abFlags** member.</span></span> 
  
<span data-ttu-id="45e99-152">**ENTRYID**结构类似于[FLATENTRY](flatentry.md)结构。</span><span class="sxs-lookup"><span data-stu-id="45e99-152">An **ENTRYID** structure resembles a [FLATENTRY](flatentry.md) structure.</span></span> <span data-ttu-id="45e99-153">但是, 存在一些差异:</span><span class="sxs-lookup"><span data-stu-id="45e99-153">However, there are some differences:</span></span> 
  
- <span data-ttu-id="45e99-154">**ENTRYID**结构不存储条目标识符的大小;**FLATENTRY**结构。</span><span class="sxs-lookup"><span data-stu-id="45e99-154">An **ENTRYID** structure does not store the size of the entry identifier; a **FLATENTRY** structure does.</span></span> 
    
- <span data-ttu-id="45e99-155">**ENTRYID**结构单独存储项目标识符的标志数据和其余内容;**FLATENTRY**结构将标志数据与条目标识符的其余部分存储在一起。</span><span class="sxs-lookup"><span data-stu-id="45e99-155">An **ENTRYID** structure stores the flag data and the rest of the entry identifier separately; a **FLATENTRY** structure stores the flag data with the rest of the entry identifier.</span></span> 
    
- <span data-ttu-id="45e99-156">**ENTRYID**结构作为参数传递给[IMAPIProp](imapipropiunknown.md)接口的方法和以下**OpenEntry**方法: [IABLogon:: OpenEntry](iablogon-openentry.md), [IAddrBook:: OpenEntry](iaddrbook-openentry.md), [IMAPIContainer:: OpenEntry](imapicontainer-openentry.md), [IMAPISession:: OpenEntry](imapisession-openentry.md), [IMAPISupport:: OpenEntry](imapisupport-openentry.md), [IMsgStore:: OpenEntry](imsgstore-openentry.md), [IMSLogon:: OpenEntry](imslogon-openentry.md)</span><span class="sxs-lookup"><span data-stu-id="45e99-156">An **ENTRYID** structure is passed as a parameter to the methods of the [IMAPIProp](imapipropiunknown.md) interface and to the following **OpenEntry** methods: [IABLogon::OpenEntry](iablogon-openentry.md), [IAddrBook::OpenEntry](iaddrbook-openentry.md), [IMAPIContainer::OpenEntry](imapicontainer-openentry.md), [IMAPISession::OpenEntry](imapisession-openentry.md), [IMAPISupport::OpenEntry](imapisupport-openentry.md), [IMsgStore::OpenEntry](imsgstore-openentry.md), [IMSLogon::OpenEntry](imslogon-openentry.md)</span></span>
    
- <span data-ttu-id="45e99-157">**ENTRYID**结构用于在磁盘上存储条目标识符。</span><span class="sxs-lookup"><span data-stu-id="45e99-157">An **ENTRYID** structure is used to store an entry identifier on disk.</span></span> <span data-ttu-id="45e99-158">**FLATENTRY**结构用于将条目标识符存储在文件中, 或将其传递到字节流中。</span><span class="sxs-lookup"><span data-stu-id="45e99-158">A **FLATENTRY** structure is used to store an entry identifier in a file or pass it in a stream of bytes.</span></span> 
    
<span data-ttu-id="45e99-159">客户端应始终传递以自然对齐的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="45e99-159">Clients should always pass in naturally aligned entry identifiers.</span></span> <span data-ttu-id="45e99-160">虽然提供程序应处理任意对齐的条目标识符, 但客户端不应预期此行为。</span><span class="sxs-lookup"><span data-stu-id="45e99-160">Although providers should handle arbitrarily aligned entry identifiers, clients should not expect this behavior.</span></span> <span data-ttu-id="45e99-161">如果未能将正确的条目标识符传递给方法, 则会导致 RISC 处理器上的校准错误。</span><span class="sxs-lookup"><span data-stu-id="45e99-161">Failure to pass a good aligned entry identifier to a method can cause an alignment fault on RISC processors.</span></span> 
  
<span data-ttu-id="45e99-162">自然对齐因子 (通常为8个字节) 是 CPU 支持的最大数据类型, 通常与系统内存分配器使用相同的校准因子。</span><span class="sxs-lookup"><span data-stu-id="45e99-162">The natural alignment factor, typically 8 bytes, is the largest data type supported by the CPU, and usually the same alignment factor used by the system memory allocator.</span></span> <span data-ttu-id="45e99-163">通过自然对齐的内存地址, CPU 可以访问它在该地址支持的任何数据类型, 而不会生成对齐错误。</span><span class="sxs-lookup"><span data-stu-id="45e99-163">A naturally aligned memory address allows the CPU to access any data type it supports at that address without generating an alignment fault.</span></span> <span data-ttu-id="45e99-164">对于 RISC cpu, 大小为 n 个字节的数据类型通常必须在 n 个字节的偶数倍进行对齐, 且地址是 n 的偶数倍。</span><span class="sxs-lookup"><span data-stu-id="45e99-164">For RISC CPUs, a data type of size N bytes must usually be aligned on an even multiple of N bytes, with the address being an even multiple of N.</span></span>
  
<span data-ttu-id="45e99-165">有关详细信息, 请参阅[条目标识符](mapi-entry-identifiers.md)。</span><span class="sxs-lookup"><span data-stu-id="45e99-165">For more information, see [Entry Identifiers](mapi-entry-identifiers.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="45e99-166">另请参阅</span><span class="sxs-lookup"><span data-stu-id="45e99-166">See also</span></span>



[<span data-ttu-id="45e99-167">FLATENTRY</span><span class="sxs-lookup"><span data-stu-id="45e99-167">FLATENTRY</span></span>](flatentry.md)
  
[<span data-ttu-id="45e99-168">IMAPISupport::CompareEntryIDs</span><span class="sxs-lookup"><span data-stu-id="45e99-168">IMAPISupport::CompareEntryIDs</span></span>](imapisupport-compareentryids.md)
  
[<span data-ttu-id="45e99-169">PidTagRecordKey 规范属性</span><span class="sxs-lookup"><span data-stu-id="45e99-169">PidTagRecordKey Canonical Property</span></span>](pidtagrecordkey-canonical-property.md)


[<span data-ttu-id="45e99-170">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="45e99-170">MAPI Structures</span></span>](mapi-structures.md)

