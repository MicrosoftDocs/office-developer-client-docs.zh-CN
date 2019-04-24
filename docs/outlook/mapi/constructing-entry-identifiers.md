---
title: 构建条目标识符
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: bc2a9116-948e-4da3-96b8-26d73bcd63c4
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 8d48c2584fa5b7e862102e401ea8165821607f77
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335089"
---
# <a name="constructing-entry-identifiers"></a><span data-ttu-id="9876f-103">构建条目标识符</span><span class="sxs-lookup"><span data-stu-id="9876f-103">Constructing Entry Identifiers</span></span>

  
  
<span data-ttu-id="9876f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9876f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9876f-105">条目标识符是使用[ENTRYID](entryid.md)结构构造的。</span><span class="sxs-lookup"><span data-stu-id="9876f-105">Entry identifiers are constructed with the [ENTRYID](entryid.md) structure.</span></span> <span data-ttu-id="9876f-106">**ENTRYID**结构由描述条目标识符和实际条目标识符的属性的标志组成。</span><span class="sxs-lookup"><span data-stu-id="9876f-106">The **ENTRYID** structure is composed of a flag that describes the attributes of the entry identifier and the actual entry identifier.</span></span> 
  
## <a name="entryid-structure"></a><span data-ttu-id="9876f-107">ENTRYID 结构</span><span class="sxs-lookup"><span data-stu-id="9876f-107">ENTRYID Structure</span></span>

<span data-ttu-id="9876f-108">**ENTRYID**结构定义如下:</span><span class="sxs-lookup"><span data-stu-id="9876f-108">The **ENTRYID** structure is defined as follows:</span></span> 
  
```cpp
typedef struct
{
    BYTE        abFlags[4];
    BYTE        ab[MAPI_DIM];
}  ENTRYID, FAR *LPENTRYID;
 
```

<span data-ttu-id="9876f-109">MAPI_DIM 是在 mapidefs.h 头文件中定义的常量。</span><span class="sxs-lookup"><span data-stu-id="9876f-109">MAPI_DIM is a constant that is defined in the MapiDefs.h header file.</span></span> 
  
<span data-ttu-id="9876f-110">4字节**abFlags**成员的第一个字节描述了条目标识符的类型和使用, 并且可以具有以下值:</span><span class="sxs-lookup"><span data-stu-id="9876f-110">The first byte of the 4-byte **abFlags** member describes the type and use of the entry identifier and can have the following values:</span></span> 
  
- <span data-ttu-id="9876f-111">MAPI_NOTRECI —指示不能将条目标识符用作邮件的收件人。</span><span class="sxs-lookup"><span data-stu-id="9876f-111">MAPI_NOTRECI — Indicates the entry identifier cannot be used as a recipient on a message.</span></span>
    
- <span data-ttu-id="9876f-112">MAPI_NOTRESERVED —指示其他用户无法访问条目标识符。</span><span class="sxs-lookup"><span data-stu-id="9876f-112">MAPI_NOTRESERVED — Indicates that other users cannot access the entry identifier.</span></span>
    
- <span data-ttu-id="9876f-113">MAPI_NOW —指示不能在其他时间使用条目标识符。</span><span class="sxs-lookup"><span data-stu-id="9876f-113">MAPI_NOW — Indicates that the entry identifier cannot be used at other times.</span></span>
    
- <span data-ttu-id="9876f-114">MAPI_SHORTTERM —指示条目标识符是短期的。</span><span class="sxs-lookup"><span data-stu-id="9876f-114">MAPI_SHORTTERM — Indicates that the entry identifier is short-term.</span></span> <span data-ttu-id="9876f-115">除非允许其他使用条目标识符, 否则必须设置此字节中的所有其他值。</span><span class="sxs-lookup"><span data-stu-id="9876f-115">All other values in this byte must be set unless other uses of the entry identifier are allowed.</span></span>
    
- <span data-ttu-id="9876f-116">MAPI_THISSESSION —指示条目标识符不能用于其他会话。</span><span class="sxs-lookup"><span data-stu-id="9876f-116">MAPI_THISSESSION — Indicates that the entry identifier cannot be used on other sessions.</span></span>
    
- <span data-ttu-id="9876f-117">MAPI_NOTRESERVED —指示其他对象的其他服务提供程序可以使用条目标识符。</span><span class="sxs-lookup"><span data-stu-id="9876f-117">MAPI_NOTRESERVED — Indicates that the entry identifier can be used by other service providers for other objects.</span></span>
    
<span data-ttu-id="9876f-118">由通讯簿和邮件存储提供程序创建的条目标识符的**ab**成员由两部分组成: 一个标识服务提供程序的16字节[MAPIUID](mapiuid.md)结构, 以及一个标识该对象的部分。</span><span class="sxs-lookup"><span data-stu-id="9876f-118">The **ab** member of entry identifiers that is created by address book and message store providers is composed of two pieces: a 16-byte [MAPIUID](mapiuid.md) structure that identifies the service provider, and a piece to identify the object.</span></span> <span data-ttu-id="9876f-119">**MAPIUID**是一个包含全局唯一标识符或 GUID 的结构。</span><span class="sxs-lookup"><span data-stu-id="9876f-119">**MAPIUID** is a structure that contains a globally unique identifier, or GUID.</span></span> <span data-ttu-id="9876f-120">GUID 是一种独立于字节顺序的标识符, 可以使用 Microsoft Visual Studio*Create GUID*\* 工具创建。</span><span class="sxs-lookup"><span data-stu-id="9876f-120">A GUID is a byte-order-independent identifier that can be created by using the Microsoft Visual Studio*Create GUID*\* tool.</span></span> 
  
<span data-ttu-id="9876f-121">在登录过程中, 服务提供商在调用[IMAPISupport:: SetProviderUID](imapisupport-setprovideruid.md)方法期间, 在登录过程中向 MAPI 注册其**MAPIUID**结构。</span><span class="sxs-lookup"><span data-stu-id="9876f-121">A service provider registers its **MAPIUID** structure with MAPI during the logon process in a call to the [IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md) method.</span></span> <span data-ttu-id="9876f-122">当客户端调用**OpenEntry**方法访问对象时, MAPI 将使用**MAPIUID**结构来确定哪些服务提供商可以提供该访问权限。</span><span class="sxs-lookup"><span data-stu-id="9876f-122">When a client calls an **OpenEntry** method to access an object, MAPI uses the **MAPIUID** structure to determine which service provider can provide that access.</span></span> <span data-ttu-id="9876f-123">服务提供程序应对其 DLL 的所有版本使用相同的**MAPIUID**结构。</span><span class="sxs-lookup"><span data-stu-id="9876f-123">Service providers should use the same **MAPIUID** structure for all versions of their DLL.</span></span> <span data-ttu-id="9876f-124">这使具有较新版本的客户端能够响应随旧版本发送和保存的邮件。</span><span class="sxs-lookup"><span data-stu-id="9876f-124">This enables clients with the newer version to respond to messages sent and saved with the older version.</span></span> 
  
<span data-ttu-id="9876f-125">16字节**MAPIUID**后面的**ab**成员的其余部分包含用于标识特定对象的特定于服务提供程序的二进制数据。</span><span class="sxs-lookup"><span data-stu-id="9876f-125">The rest of the **ab** member after the 16-byte **MAPIUID** contains service-provider-specific binary data for identifying particular objects.</span></span> <span data-ttu-id="9876f-126">此部分条目标识符没有固定大小。</span><span class="sxs-lookup"><span data-stu-id="9876f-126">There is no fixed size for this portion of the entry identifier.</span></span> <span data-ttu-id="9876f-127">它可以是任何大小, 在某个原因内。</span><span class="sxs-lookup"><span data-stu-id="9876f-127">It can be any size, within reason.</span></span> <span data-ttu-id="9876f-128">服务提供程序通常在此部分的条目标识符中包含以下信息:</span><span class="sxs-lookup"><span data-stu-id="9876f-128">A service provider typically includes the following information in this part of its entry identifiers:</span></span> 
  
- <span data-ttu-id="9876f-129">版本信息-由于服务提供程序会将其条目标识符的格式从版本更改为版本, 因此存储版本信息可以快速确定如何解密任何条目标识符。</span><span class="sxs-lookup"><span data-stu-id="9876f-129">Version information — Because it is common for a service provider to change the format of its entry identifiers from version to version, storing version information makes it possible to quickly determine how to decipher any entry identifier.</span></span>
    
- <span data-ttu-id="9876f-130">位置信息—位置信息是为服务提供商提供一个指标的数据, 该指标指示如何查找条目标识符所代表的对象。</span><span class="sxs-lookup"><span data-stu-id="9876f-130">Location information — Location information is data that gives a service provider an indicator of how to locate the object represented by the entry identifier.</span></span> <span data-ttu-id="9876f-131">例如, 服务提供程序可以将磁盘偏移量存储在存储对象的数据文件中的最后一个位置。</span><span class="sxs-lookup"><span data-stu-id="9876f-131">For example, a service provider can store the disk offset for the last place in a data file that the object was stored.</span></span> <span data-ttu-id="9876f-132">由于此类信息可以随着时间的推移而发生变化, 因此服务提供商应提供多种方法来查找其条目标识符中的对象。</span><span class="sxs-lookup"><span data-stu-id="9876f-132">Because this type of information can change over time, service providers should provide multiple ways for locating objects in their entry identifiers.</span></span>
    
<span data-ttu-id="9876f-133">尽管服务提供商可以回收其条目标识符, 但应避免这种做法。</span><span class="sxs-lookup"><span data-stu-id="9876f-133">Although service providers can recycle their entry identifiers, they should avoid this practice.</span></span> <span data-ttu-id="9876f-134">如果需要重用条目标识符, 则服务提供商应将初始使用和重用之间的时间间隔设置为尽可能长的时间。</span><span class="sxs-lookup"><span data-stu-id="9876f-134">If it is necessary to reuse an entry identifier, service providers should make the time period that elapses between the initial use and the reuse as long as possible.</span></span> <span data-ttu-id="9876f-135">此外, 还应将条目标识符重新分配给同一类型的另一个对象。</span><span class="sxs-lookup"><span data-stu-id="9876f-135">Also, the entry identifier should be reassigned to another object of the same type.</span></span> <span data-ttu-id="9876f-136">也就是说, 特定条目标识符不应首先与邮件相关联, 然后再与文件夹相关联。</span><span class="sxs-lookup"><span data-stu-id="9876f-136">That is, a particular entry identifier should not be associated first with a message and then with a folder.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9876f-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9876f-137">See also</span></span>



[<span data-ttu-id="9876f-138">MAPI 条目标识符</span><span class="sxs-lookup"><span data-stu-id="9876f-138">MAPI Entry Identifiers</span></span>](mapi-entry-identifiers.md)

