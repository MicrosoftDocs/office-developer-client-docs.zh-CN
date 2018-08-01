---
title: 构建条目标识符
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: bc2a9116-948e-4da3-96b8-26d73bcd63c4
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 1d38c0ac7ddbd24123dd51d7315644f3ad786d15
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774676"
---
# <a name="constructing-entry-identifiers"></a><span data-ttu-id="3ee4d-103">构建条目标识符</span><span class="sxs-lookup"><span data-stu-id="3ee4d-103">Constructing Entry Identifiers</span></span>

  
  
<span data-ttu-id="3ee4d-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="3ee4d-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="3ee4d-105">使用[ENTRYID](entryid.md)结构构建条目标识符。</span><span class="sxs-lookup"><span data-stu-id="3ee4d-105">Entry identifiers are constructed with the [ENTRYID](entryid.md) structure.</span></span> <span data-ttu-id="3ee4d-106">**ENTRYID**结构组成描述的项标识符和实际的项标识符的属性的标志。</span><span class="sxs-lookup"><span data-stu-id="3ee4d-106">The **ENTRYID** structure is composed of a flag that describes the attributes of the entry identifier and the actual entry identifier.</span></span> 
  
## <a name="entryid-structure"></a><span data-ttu-id="3ee4d-107">ENTRYID 结构</span><span class="sxs-lookup"><span data-stu-id="3ee4d-107">ENTRYID Structure</span></span>

<span data-ttu-id="3ee4d-108">**ENTRYID**结构定义如下：</span><span class="sxs-lookup"><span data-stu-id="3ee4d-108">The **ENTRYID** structure is defined as follows:</span></span> 
  
```cpp
typedef struct
{
    BYTE        abFlags[4];
    BYTE        ab[MAPI_DIM];
}  ENTRYID, FAR *LPENTRYID;
 
```

<span data-ttu-id="3ee4d-109">MAPI_DIM 是 MapiDefs.h 标头文件中定义的常量。</span><span class="sxs-lookup"><span data-stu-id="3ee4d-109">MAPI_DIM is a constant that is defined in the MapiDefs.h header file.</span></span> 
  
<span data-ttu-id="3ee4d-110">4 字节**abFlags**成员的第一个字节描述的类型和使用的项标识符可以具有下列值：</span><span class="sxs-lookup"><span data-stu-id="3ee4d-110">The first byte of the 4-byte **abFlags** member describes the type and use of the entry identifier and can have the following values:</span></span> 
  
- <span data-ttu-id="3ee4d-111">MAPI_NOTRECI — 指示条目标识符不能用作邮件收件人。</span><span class="sxs-lookup"><span data-stu-id="3ee4d-111">MAPI_NOTRECI — Indicates the entry identifier cannot be used as a recipient on a message.</span></span>
    
- <span data-ttu-id="3ee4d-112">MAPI_NOTRESERVED — 指示其他用户无法访问的项标识符。</span><span class="sxs-lookup"><span data-stu-id="3ee4d-112">MAPI_NOTRESERVED — Indicates that other users cannot access the entry identifier.</span></span>
    
- <span data-ttu-id="3ee4d-113">在其他情况下不能使用的项标识符的 MAPI_NOW — 指示。</span><span class="sxs-lookup"><span data-stu-id="3ee4d-113">MAPI_NOW — Indicates that the entry identifier cannot be used at other times.</span></span>
    
- <span data-ttu-id="3ee4d-114">项标识符是短期 MAPI_SHORTTERM — 指示。</span><span class="sxs-lookup"><span data-stu-id="3ee4d-114">MAPI_SHORTTERM — Indicates that the entry identifier is short-term.</span></span> <span data-ttu-id="3ee4d-115">必须设置此字节中的所有其他值，除非在内的项标识符的其他用途。</span><span class="sxs-lookup"><span data-stu-id="3ee4d-115">All other values in this byte must be set unless other uses of the entry identifier are allowed.</span></span>
    
- <span data-ttu-id="3ee4d-116">MAPI_THISSESSION — 指示上其他会话不能使用的项标识符的。</span><span class="sxs-lookup"><span data-stu-id="3ee4d-116">MAPI_THISSESSION — Indicates that the entry identifier cannot be used on other sessions.</span></span>
    
- <span data-ttu-id="3ee4d-117">MAPI_NOTRESERVED — 指示的项标识符可用于其他服务提供程序的其他对象。</span><span class="sxs-lookup"><span data-stu-id="3ee4d-117">MAPI_NOTRESERVED — Indicates that the entry identifier can be used by other service providers for other objects.</span></span>
    
<span data-ttu-id="3ee4d-118">地址簿和消息存储提供程序创建的项标识符的**ab**成员是两个部分组成： 标识服务提供商和一段来标识对象的 16 字节[MAPIUID](mapiuid.md)结构。</span><span class="sxs-lookup"><span data-stu-id="3ee4d-118">The **ab** member of entry identifiers that is created by address book and message store providers is composed of two pieces: a 16-byte [MAPIUID](mapiuid.md) structure that identifies the service provider, and a piece to identify the object.</span></span> <span data-ttu-id="3ee4d-119">**MAPIUID**是包含的全局唯一标识符或 GUID 的结构。</span><span class="sxs-lookup"><span data-stu-id="3ee4d-119">**MAPIUID** is a structure that contains a globally unique identifier, or GUID.</span></span> <span data-ttu-id="3ee4d-120">GUID 是一个独立于字节的顺序的标识符，可以使用 Microsoft Visual Studio*创建 GUID*创建 \* 工具。</span><span class="sxs-lookup"><span data-stu-id="3ee4d-120">A GUID is a byte-order-independent identifier that can be created by using the Microsoft Visual Studio*Create GUID*\* tool.</span></span> 
  
<span data-ttu-id="3ee4d-121">服务提供商注册 MAPI 登录过程中对[IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md)方法的调用中其**MAPIUID**结构。</span><span class="sxs-lookup"><span data-stu-id="3ee4d-121">A service provider registers its **MAPIUID** structure with MAPI during the logon process in a call to the [IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md) method.</span></span> <span data-ttu-id="3ee4d-122">当客户端调用**OpenEntry**方法来访问的对象时，MAPI 使用**MAPIUID**结构确定哪项服务提供程序可以提供访问。</span><span class="sxs-lookup"><span data-stu-id="3ee4d-122">When a client calls an **OpenEntry** method to access an object, MAPI uses the **MAPIUID** structure to determine which service provider can provide that access.</span></span> <span data-ttu-id="3ee4d-123">服务提供商应使用相同的**MAPIUID**结构的所有版本的其 DLL。</span><span class="sxs-lookup"><span data-stu-id="3ee4d-123">Service providers should use the same **MAPIUID** structure for all versions of their DLL.</span></span> <span data-ttu-id="3ee4d-124">这样，客户端与新版本以响应发送和使用较旧版本保存的邮件。</span><span class="sxs-lookup"><span data-stu-id="3ee4d-124">This enables clients with the newer version to respond to messages sent and saved with the older version.</span></span> 
  
<span data-ttu-id="3ee4d-125">**Ab**成员后 16 字节**MAPIUID**包含特定对象标识服务提供程序特定二进制数据的其余部分。</span><span class="sxs-lookup"><span data-stu-id="3ee4d-125">The rest of the **ab** member after the 16-byte **MAPIUID** contains service-provider-specific binary data for identifying particular objects.</span></span> <span data-ttu-id="3ee4d-126">没有固定的大小的项标识符的此部分。</span><span class="sxs-lookup"><span data-stu-id="3ee4d-126">There is no fixed size for this portion of the entry identifier.</span></span> <span data-ttu-id="3ee4d-127">它可以是任何大小、 内原因。</span><span class="sxs-lookup"><span data-stu-id="3ee4d-127">It can be any size, within reason.</span></span> <span data-ttu-id="3ee4d-128">服务提供商通常包括其条目标识符本部分中的以下信息：</span><span class="sxs-lookup"><span data-stu-id="3ee4d-128">A service provider typically includes the following information in this part of its entry identifiers:</span></span> 
  
- <span data-ttu-id="3ee4d-129">版本信息 — 的情况很常见的服务提供商，若要更改其条目标识符格式版本之间的差异，因为存储版本信息使得快速确定如何解密任何条目标识符。</span><span class="sxs-lookup"><span data-stu-id="3ee4d-129">Version information — Because it is common for a service provider to change the format of its entry identifiers from version to version, storing version information makes it possible to quickly determine how to decipher any entry identifier.</span></span>
    
- <span data-ttu-id="3ee4d-130">位置信息 — 位置信息是提供如何查找所表示的项标识符的对象的指示符的服务提供商的数据。</span><span class="sxs-lookup"><span data-stu-id="3ee4d-130">Location information — Location information is data that gives a service provider an indicator of how to locate the object represented by the entry identifier.</span></span> <span data-ttu-id="3ee4d-131">例如，服务提供商可以存储的数据文件已存储对象中的最后一个地方偏移的磁盘。</span><span class="sxs-lookup"><span data-stu-id="3ee4d-131">For example, a service provider can store the disk offset for the last place in a data file that the object was stored.</span></span> <span data-ttu-id="3ee4d-132">此类型的信息可随时间变化的因为服务提供商应为其条目 identifiers 中查找对象提供多种方式。</span><span class="sxs-lookup"><span data-stu-id="3ee4d-132">Because this type of information can change over time, service providers should provide multiple ways for locating objects in their entry identifiers.</span></span>
    
<span data-ttu-id="3ee4d-133">尽管服务提供商可以回收站其条目标识符，但它们应避免这种做法。</span><span class="sxs-lookup"><span data-stu-id="3ee4d-133">Although service providers can recycle their entry identifiers, they should avoid this practice.</span></span> <span data-ttu-id="3ee4d-134">如有必要可重用的项标识符，服务提供商应进行回拨此前初始使用和重用尽可能长时间之间的时间段。</span><span class="sxs-lookup"><span data-stu-id="3ee4d-134">If it is necessary to reuse an entry identifier, service providers should make the time period that elapses between the initial use and the reuse as long as possible.</span></span> <span data-ttu-id="3ee4d-135">此外，条目标识符应重新分配给同一类型的另一个对象。</span><span class="sxs-lookup"><span data-stu-id="3ee4d-135">Also, the entry identifier should be reassigned to another object of the same type.</span></span> <span data-ttu-id="3ee4d-136">即一个特定的项标识符不应首先使用一条消息，然后与文件夹关联。</span><span class="sxs-lookup"><span data-stu-id="3ee4d-136">That is, a particular entry identifier should not be associated first with a message and then with a folder.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3ee4d-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3ee4d-137">See also</span></span>



[<span data-ttu-id="3ee4d-138">MAPI 条目标识符</span><span class="sxs-lookup"><span data-stu-id="3ee4d-138">MAPI Entry Identifiers</span></span>](mapi-entry-identifiers.md)

