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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415269"
---
# <a name="entryid"></a><span data-ttu-id="f01ba-103">ENTRYID</span><span class="sxs-lookup"><span data-stu-id="f01ba-103">ENTRYID</span></span>

  
  
<span data-ttu-id="f01ba-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f01ba-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f01ba-105">包含 MAPI 对象的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="f01ba-105">Contains an entry identifier for a MAPI object.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f01ba-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="f01ba-106">Header file:</span></span>  <br/> |<span data-ttu-id="f01ba-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="f01ba-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="f01ba-108">相关宏：</span><span class="sxs-lookup"><span data-stu-id="f01ba-108">Related macros:</span></span>  <br/> |<span data-ttu-id="f01ba-109">[CbNewENTRYID](cbnewentryid.md) [、SizedENTRYID](sizedentryid.md)</span><span class="sxs-lookup"><span data-stu-id="f01ba-109">[CbNewENTRYID](cbnewentryid.md), [SizedENTRYID](sizedentryid.md)</span></span> <br/> |
   
```cpp
typedef struct
{
  BYTE abFlags[4];
  BYTE ab[MAPI_DIM];
} ENTRYID, FAR *LPENTRYID;

```

## <a name="members"></a><span data-ttu-id="f01ba-110">Members</span><span class="sxs-lookup"><span data-stu-id="f01ba-110">Members</span></span>

 <span data-ttu-id="f01ba-111">**abFlags**</span><span class="sxs-lookup"><span data-stu-id="f01ba-111">**abFlags**</span></span>
  
> <span data-ttu-id="f01ba-112">提供描述对象的信息的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="f01ba-112">Bitmask of flags that provide information that describes the object.</span></span> <span data-ttu-id="f01ba-113">提供程序只能设置标志的第一个字节 **abFlags[0]**;其他三个已保留。</span><span class="sxs-lookup"><span data-stu-id="f01ba-113">Only the first byte of the flags, **abFlags[0]**, may be set by the provider; the other three are reserved.</span></span> <span data-ttu-id="f01ba-114">不得为永久条目标识符设置这些标志;它们仅为短期条目标识符设置。</span><span class="sxs-lookup"><span data-stu-id="f01ba-114">These flags must not be set for permanent entry identifiers; they are only set for short-term entry identifiers.</span></span> <span data-ttu-id="f01ba-115">对于客户端，此结构是只读的。</span><span class="sxs-lookup"><span data-stu-id="f01ba-115">To clients, this structure is read-only.</span></span> <span data-ttu-id="f01ba-116">可以在 **abFlags[0] 中设置以下标志**：</span><span class="sxs-lookup"><span data-stu-id="f01ba-116">The following flags can be set in **abFlags[0]**:</span></span>
    
<span data-ttu-id="f01ba-117">MAPI_NOTRECIP</span><span class="sxs-lookup"><span data-stu-id="f01ba-117">MAPI_NOTRECIP</span></span> 
  
> <span data-ttu-id="f01ba-118">条目标识符不能用作邮件上的收件人。</span><span class="sxs-lookup"><span data-stu-id="f01ba-118">The entry identifier cannot be used as a recipient on a message.</span></span>
    
<span data-ttu-id="f01ba-119">MAPI_NOTRESERVED</span><span class="sxs-lookup"><span data-stu-id="f01ba-119">MAPI_NOTRESERVED</span></span> 
  
> <span data-ttu-id="f01ba-120">其他用户无法访问条目标识符。</span><span class="sxs-lookup"><span data-stu-id="f01ba-120">Other users cannot access the entry identifier.</span></span>
    
<span data-ttu-id="f01ba-121">MAPI_NOW</span><span class="sxs-lookup"><span data-stu-id="f01ba-121">MAPI_NOW</span></span> 
  
> <span data-ttu-id="f01ba-122">不能在其他时间使用条目标识符。</span><span class="sxs-lookup"><span data-stu-id="f01ba-122">The entry identifier cannot be used at other times.</span></span>
    
<span data-ttu-id="f01ba-123">MAPI_SHORTTERM</span><span class="sxs-lookup"><span data-stu-id="f01ba-123">MAPI_SHORTTERM</span></span> 
  
> <span data-ttu-id="f01ba-124">条目标识符为短期标识符。</span><span class="sxs-lookup"><span data-stu-id="f01ba-124">The entry identifier is short-term.</span></span> <span data-ttu-id="f01ba-125">必须设置此字节中的所有其他值，除非启用条目标识符的其他用法。</span><span class="sxs-lookup"><span data-stu-id="f01ba-125">All other values in this byte must be set unless other uses of the entry identifier are enabled.</span></span>
    
<span data-ttu-id="f01ba-126">MAPI_THISSESSION</span><span class="sxs-lookup"><span data-stu-id="f01ba-126">MAPI_THISSESSION</span></span> 
  
> <span data-ttu-id="f01ba-127">条目标识符不能用于其他会话。</span><span class="sxs-lookup"><span data-stu-id="f01ba-127">The entry identifier cannot be used on other sessions.</span></span>
    
 <span data-ttu-id="f01ba-128">**ab**</span><span class="sxs-lookup"><span data-stu-id="f01ba-128">**ab**</span></span>
  
> <span data-ttu-id="f01ba-129">指示服务提供商使用的二进制数据数组。</span><span class="sxs-lookup"><span data-stu-id="f01ba-129">Indicates an array of binary data that is used by service providers.</span></span> <span data-ttu-id="f01ba-130">客户端应用程序无法使用此数组。</span><span class="sxs-lookup"><span data-stu-id="f01ba-130">The client application cannot use this array.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="f01ba-131">备注</span><span class="sxs-lookup"><span data-stu-id="f01ba-131">Remarks</span></span>

<span data-ttu-id="f01ba-132">邮件存储和通讯簿提供程序使用 **ENTRYID** 结构来构造其对象的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="f01ba-132">The **ENTRYID** structure is used by message store and address book providers to construct unique identifiers for their objects.</span></span> <span data-ttu-id="f01ba-133">条目标识符用于标识以下类型的对象：</span><span class="sxs-lookup"><span data-stu-id="f01ba-133">Entry identifiers are used to identify the following types of objects:</span></span> 
  
- <span data-ttu-id="f01ba-134">邮件存储</span><span class="sxs-lookup"><span data-stu-id="f01ba-134">Message stores</span></span>
    
- <span data-ttu-id="f01ba-135">Folders</span><span class="sxs-lookup"><span data-stu-id="f01ba-135">Folders</span></span>
    
- <span data-ttu-id="f01ba-136">邮件</span><span class="sxs-lookup"><span data-stu-id="f01ba-136">Messages</span></span>
    
- <span data-ttu-id="f01ba-137">通讯簿容器</span><span class="sxs-lookup"><span data-stu-id="f01ba-137">Address book containers</span></span>
    
- <span data-ttu-id="f01ba-138">通讯组列表</span><span class="sxs-lookup"><span data-stu-id="f01ba-138">Distribution lists</span></span>
    
- <span data-ttu-id="f01ba-139">邮件用户</span><span class="sxs-lookup"><span data-stu-id="f01ba-139">Messaging users</span></span>
    
- <span data-ttu-id="f01ba-140">状态对象</span><span class="sxs-lookup"><span data-stu-id="f01ba-140">Status objects</span></span>
    
- <span data-ttu-id="f01ba-141">配置文件部分</span><span class="sxs-lookup"><span data-stu-id="f01ba-141">Profile sections</span></span>
    
<span data-ttu-id="f01ba-142">每个提供程序都对 **ENTRYID** 结构使用一种格式，该格式对于该提供程序有意义。</span><span class="sxs-lookup"><span data-stu-id="f01ba-142">Each provider uses a format for the **ENTRYID** structure that makes sense for that provider.</span></span> 
  
<span data-ttu-id="f01ba-143">不能直接对条目标识符进行比较，因为一个对象可以由两个不同的二进制值表示。</span><span class="sxs-lookup"><span data-stu-id="f01ba-143">Entry identifiers cannot be compared directly because one object can be represented by two different binary values.</span></span> <span data-ttu-id="f01ba-144">若要确定两个条目标识符是否表示同一个对象，请调用 [IMAPISession：：CompareEntryIDs](imapisession-compareentryids.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="f01ba-144">To determine whether two entry identifiers represent the same object, call the [IMAPISession::CompareEntryIDs](imapisession-compareentryids.md) method.</span></span> 
  
<span data-ttu-id="f01ba-145">当客户端调用对象的 [IMAPIProp：：GetProps](imapiprop-getprops.md) 方法来检索其条目标识符时，该对象将返回条目标识符的最永久形式。</span><span class="sxs-lookup"><span data-stu-id="f01ba-145">When a client calls an object's [IMAPIProp::GetProps](imapiprop-getprops.md) method to retrieve its entry identifier, the object returns the most permanent form of the entry identifier.</span></span> <span data-ttu-id="f01ba-146">客户端可以通过检查 **abFlags** 成员的第一个字节中是否未设置任何标志来验证条目标识符是长期标识符。</span><span class="sxs-lookup"><span data-stu-id="f01ba-146">A client can verify that an entry identifier is long-term by checking that none of the flags are set in the first byte of the **abFlags** member.</span></span> 
  
<span data-ttu-id="f01ba-147">当客户端通过表中的列访问条目标识符时，很可能此条目标识符是短期标识符，而不是长期标识符。</span><span class="sxs-lookup"><span data-stu-id="f01ba-147">When a client accesses an entry identifier through a column in a table, most likely this entry identifier is short-term instead of long-term.</span></span> <span data-ttu-id="f01ba-148">短期条目标识符只能用于在当前 MAPI 会话中打开其相应的对象。</span><span class="sxs-lookup"><span data-stu-id="f01ba-148">Short-term entry identifiers can be used to open their corresponding objects only in the current MAPI session.</span></span> <span data-ttu-id="f01ba-149">客户端可以通过检查在 **abFlags** 成员的第一个字节中设置所有标志来验证条目标识符是短期的。</span><span class="sxs-lookup"><span data-stu-id="f01ba-149">A client can verify that an entry identifier is short-term by checking that all of the flags are set in the first byte of the **abFlags** member.</span></span> 
  
<span data-ttu-id="f01ba-150">某些条目标识符是短期的，但具有长期用途。</span><span class="sxs-lookup"><span data-stu-id="f01ba-150">Some entry identifiers are short-term, but have long-term use.</span></span> <span data-ttu-id="f01ba-151">此类条目标识符将在其 **abFlags** 成员的第一个字节中设置一个或多个相应标志。</span><span class="sxs-lookup"><span data-stu-id="f01ba-151">Such an entry identifier will have one or more of the appropriate flags set in the first byte of its **abFlags** member.</span></span> 
  
<span data-ttu-id="f01ba-152">**ENTRYID** 结构类似于 [FLATENTRY](flatentry.md)结构。</span><span class="sxs-lookup"><span data-stu-id="f01ba-152">An **ENTRYID** structure resembles a [FLATENTRY](flatentry.md) structure.</span></span> <span data-ttu-id="f01ba-153">但是，存在一些差异：</span><span class="sxs-lookup"><span data-stu-id="f01ba-153">However, there are some differences:</span></span> 
  
- <span data-ttu-id="f01ba-154">**ENTRYID** 结构不存储条目标识符的大小;**FLATENTRY** 结构有。</span><span class="sxs-lookup"><span data-stu-id="f01ba-154">An **ENTRYID** structure does not store the size of the entry identifier; a **FLATENTRY** structure does.</span></span> 
    
- <span data-ttu-id="f01ba-155">**ENTRYID** 结构单独存储标志数据和条目标识符的其余部分;**FLATENTRY** 结构使用条目标识符的其余部分存储标志数据。</span><span class="sxs-lookup"><span data-stu-id="f01ba-155">An **ENTRYID** structure stores the flag data and the rest of the entry identifier separately; a **FLATENTRY** structure stores the flag data with the rest of the entry identifier.</span></span> 
    
- <span data-ttu-id="f01ba-156">**ENTRYID** 结构作为参数传递给 [IMAPIProp](imapipropiunknown.md)接口的方法和以下 **OpenEntry** 方法：IABLogon：：OpenEntry、IAddrBook：：OpenEntry、IMAPIContainer：：OpenEntry、IMAPISession：：OpenEntry、IMAPISupport：：OpenEntry、IMsgStore：：OpenEntry、IMSLogon：：OpenEntry [](iablogon-openentry.md) [](iaddrbook-openentry.md) [](imapicontainer-openentry.md) [](imapisession-openentry.md) [](imapisupport-openentry.md) [](imsgstore-openentry.md) [](imslogon-openentry.md)</span><span class="sxs-lookup"><span data-stu-id="f01ba-156">An **ENTRYID** structure is passed as a parameter to the methods of the [IMAPIProp](imapipropiunknown.md) interface and to the following **OpenEntry** methods: [IABLogon::OpenEntry](iablogon-openentry.md), [IAddrBook::OpenEntry](iaddrbook-openentry.md), [IMAPIContainer::OpenEntry](imapicontainer-openentry.md), [IMAPISession::OpenEntry](imapisession-openentry.md), [IMAPISupport::OpenEntry](imapisupport-openentry.md), [IMsgStore::OpenEntry](imsgstore-openentry.md), [IMSLogon::OpenEntry](imslogon-openentry.md)</span></span>
    
- <span data-ttu-id="f01ba-157">**ENTRYID** 结构用于在磁盘上存储条目标识符。</span><span class="sxs-lookup"><span data-stu-id="f01ba-157">An **ENTRYID** structure is used to store an entry identifier on disk.</span></span> <span data-ttu-id="f01ba-158">**FLATENTRY** 结构用于将条目标识符存储在文件中或传递到字节流中。</span><span class="sxs-lookup"><span data-stu-id="f01ba-158">A **FLATENTRY** structure is used to store an entry identifier in a file or pass it in a stream of bytes.</span></span> 
    
<span data-ttu-id="f01ba-159">客户端应始终传递自然对齐的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="f01ba-159">Clients should always pass in naturally aligned entry identifiers.</span></span> <span data-ttu-id="f01ba-160">尽管提供程序应处理任意对齐的条目标识符，但客户端不应期望此行为。</span><span class="sxs-lookup"><span data-stu-id="f01ba-160">Although providers should handle arbitrarily aligned entry identifiers, clients should not expect this behavior.</span></span> <span data-ttu-id="f01ba-161">如果未能将对齐良好的条目标识符传递给方法，可能会导致 RISC 处理器出现对齐错误。</span><span class="sxs-lookup"><span data-stu-id="f01ba-161">Failure to pass a good aligned entry identifier to a method can cause an alignment fault on RISC processors.</span></span> 
  
<span data-ttu-id="f01ba-162">自然对齐因子（通常为 8 个字节）是 CPU 数据类型支持的最大对齐因子，并且通常是系统内存分配器使用的相同对齐因素。</span><span class="sxs-lookup"><span data-stu-id="f01ba-162">The natural alignment factor, typically 8 bytes, is the largest data type supported by the CPU, and usually the same alignment factor used by the system memory allocator.</span></span> <span data-ttu-id="f01ba-163">自然对齐的内存地址允许 CPU 访问它数据类型该地址上支持的任何地址，而不会生成对齐错误。</span><span class="sxs-lookup"><span data-stu-id="f01ba-163">A naturally aligned memory address allows the CPU to access any data type it supports at that address without generating an alignment fault.</span></span> <span data-ttu-id="f01ba-164">对于 RISC CPU，数据类型 N 字节的大小通常必须在 N 字节的甚至倍数上对齐，地址为 N 的倍数。</span><span class="sxs-lookup"><span data-stu-id="f01ba-164">For RISC CPUs, a data type of size N bytes must usually be aligned on an even multiple of N bytes, with the address being an even multiple of N.</span></span>
  
<span data-ttu-id="f01ba-165">有关详细信息，请参阅条目 [标识符](mapi-entry-identifiers.md)。</span><span class="sxs-lookup"><span data-stu-id="f01ba-165">For more information, see [Entry Identifiers](mapi-entry-identifiers.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f01ba-166">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f01ba-166">See also</span></span>



[<span data-ttu-id="f01ba-167">FLATENTRY</span><span class="sxs-lookup"><span data-stu-id="f01ba-167">FLATENTRY</span></span>](flatentry.md)
  
[<span data-ttu-id="f01ba-168">IMAPISupport::CompareEntryIDs</span><span class="sxs-lookup"><span data-stu-id="f01ba-168">IMAPISupport::CompareEntryIDs</span></span>](imapisupport-compareentryids.md)
  
[<span data-ttu-id="f01ba-169">PidTagRecordKey 规范属性</span><span class="sxs-lookup"><span data-stu-id="f01ba-169">PidTagRecordKey Canonical Property</span></span>](pidtagrecordkey-canonical-property.md)


[<span data-ttu-id="f01ba-170">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="f01ba-170">MAPI Structures</span></span>](mapi-structures.md)

