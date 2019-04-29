---
title: 检索 MAPI 属性
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: bd3f9f59-9020-46e6-9560-86a7a0eeca20
description: 上次修改时间：2015 年 12 月 7 日
ms.openlocfilehash: 9666c551543cefd12ee8c902db1a2372aab20632
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417082"
---
# <a name="retrieving-mapi-properties"></a><span data-ttu-id="ae501-103">检索 MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ae501-103">Retrieving MAPI Properties</span></span>

 
  
<span data-ttu-id="ae501-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ae501-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ae501-105">当客户端或服务提供程序从对象中检索属性时, 该对象可提供该属性的值、类型和标识符。</span><span class="sxs-lookup"><span data-stu-id="ae501-105">When a client or service provider retrieves a property from an object, the object makes available the property's value, type, and identifier.</span></span> 
  
<span data-ttu-id="ae501-106">客户端和服务提供程序可以通过调用以下项之一来检索对象的属性:</span><span class="sxs-lookup"><span data-stu-id="ae501-106">Clients and service providers can retrieve an object's properties by calling one of the following:</span></span>
  
[<span data-ttu-id="ae501-107">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="ae501-107">IMAPIProp::GetProps</span></span>](imapiprop-getprops.md)
  
[<span data-ttu-id="ae501-108">IMAPIProp::OpenProperty</span><span class="sxs-lookup"><span data-stu-id="ae501-108">IMAPIProp::OpenProperty</span></span>](imapiprop-openproperty.md)
  
[<span data-ttu-id="ae501-109">HrGetOneProp</span><span class="sxs-lookup"><span data-stu-id="ae501-109">HrGetOneProp</span></span>](hrgetoneprop.md)
  
<span data-ttu-id="ae501-110">**GetProps**方法用于检索一个或多个不需要专用或备用接口进行访问的属性。</span><span class="sxs-lookup"><span data-stu-id="ae501-110">The **GetProps** method is used to retrieve one or more properties that do not need a specialized or alternate interface for access.</span></span> <span data-ttu-id="ae501-111">这意味着**GetProps**中可用的属性很小, 例如整数和布尔值。</span><span class="sxs-lookup"><span data-stu-id="ae501-111">This implies that the properties available with **GetProps** are small, such as integers and Boolean values.</span></span> 
  
 <span data-ttu-id="ae501-112">**检索多个属性**</span><span class="sxs-lookup"><span data-stu-id="ae501-112">**To retrieve multiple properties**</span></span>
  
1. <span data-ttu-id="ae501-113">分配一个足够大的[SPropTagArray](sproptagarray.md)结构, 以容纳要检索的属性的数量。</span><span class="sxs-lookup"><span data-stu-id="ae501-113">Allocate an [SPropTagArray](sproptagarray.md) structure large enough to hold the number of properties to be retrieved.</span></span> 
    
2. <span data-ttu-id="ae501-114">将**SPropTagArray**结构的**cValues**成员设置为要检索的属性的数量, 并将每个**aulPropTag**成员设置为 "标识符" 和 "类型" (如果可能) 其中一个目标属性。</span><span class="sxs-lookup"><span data-stu-id="ae501-114">Set the **cValues** member of the **SPropTagArray** structure to the number of properties to be retrieved and set each **aulPropTag** member to the identifier and type, if possible, of one of the target properties.</span></span> <span data-ttu-id="ae501-115">如果类型未知, 请将其设置为 PT_UNSPECIFIED。</span><span class="sxs-lookup"><span data-stu-id="ae501-115">If the type is unknown, set it to PT_UNSPECIFIED.</span></span> <span data-ttu-id="ae501-116">如果类型和标识符都是未知的, 则通过调用[IMAPIProp:: GetPropList](imapiprop-getproplist.md)查找此信息。</span><span class="sxs-lookup"><span data-stu-id="ae501-116">If both the type and the identifier are unknown, locate this information by calling [IMAPIProp::GetPropList](imapiprop-getproplist.md).</span></span> <span data-ttu-id="ae501-117">**GetPropList**返回具有对象的所有支持属性的属性标记数组。</span><span class="sxs-lookup"><span data-stu-id="ae501-117">**GetPropList** returns a property tag array with all of the object's supported properties.</span></span> <span data-ttu-id="ae501-118">如果仅有属性名称可用, 则调用[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)以访问关联的标识符。</span><span class="sxs-lookup"><span data-stu-id="ae501-118">If only a property name is available, call [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) to access the associated identifier.</span></span> 
    
3. <span data-ttu-id="ae501-119">调用[IMAPIProp:: GetProps](imapiprop-getprops.md)打开属性或属性。</span><span class="sxs-lookup"><span data-stu-id="ae501-119">Call [IMAPIProp::GetProps](imapiprop-getprops.md) to open the property or properties.</span></span> 
    
<span data-ttu-id="ae501-120">**OpenProperty**方法用于打开需要备用接口 (如**IStream**或[IMAPITable](imapitableiunknown.md) for access) 的较大属性。</span><span class="sxs-lookup"><span data-stu-id="ae501-120">The **OpenProperty** method is used to open larger properties that require an alternate interface such as **IStream** or [IMAPITable](imapitableiunknown.md) for access.</span></span> <span data-ttu-id="ae501-121">**OpenProperty**通常用于打开大型字符串、二进制文件和对象属性, 并且一次只能打开一个属性。</span><span class="sxs-lookup"><span data-stu-id="ae501-121">**OpenProperty** is typically used to open large character string, binary, and object properties and can only open one property at a time.</span></span> <span data-ttu-id="ae501-122">调用方传入作为输入参数之一所需的其他接口的标识符。</span><span class="sxs-lookup"><span data-stu-id="ae501-122">Callers pass in the identifier of the additional interface that is required as one of the input parameters.</span></span> 
  
<span data-ttu-id="ae501-123">**OpenProperty**的一些常见用途包括打开**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md))、保存基于文本的邮件正文的属性、 **PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md))、保存的属性OLE 对象或邮件附件以及**PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)), 它是保存文件夹或通讯簿容器内容表的属性。</span><span class="sxs-lookup"><span data-stu-id="ae501-123">Some of the common uses of **OpenProperty** include opening **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)), the property that holds the body of a text-based message, **PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)), the property that holds an OLE object or message attachment, and **PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)), the property that holds a folder or address book container contents table.</span></span> 
  
<span data-ttu-id="ae501-124">根据属性的不同, 从**OpenProperty**请求不同的接口。</span><span class="sxs-lookup"><span data-stu-id="ae501-124">Depending on the property, a different interface is requested from **OpenProperty**.</span></span> <span data-ttu-id="ae501-125">**IStream**是一个接口, 它允许以字节流的形式读取和写入属性数据, 通常用于访问**PR_BODY**。</span><span class="sxs-lookup"><span data-stu-id="ae501-125">**IStream**, an interface that allows property data to be read and written as a stream of bytes, is typically used to access **PR_BODY**.</span></span> <span data-ttu-id="ae501-126">[IMessage](imessageimapiprop.md)或**IStream**可用于访问**PR_ATTACH_DATA_OBJ**。</span><span class="sxs-lookup"><span data-stu-id="ae501-126">Either [IMessage](imessageimapiprop.md) or **IStream** can be used to access **PR_ATTACH_DATA_OBJ**.</span></span> <span data-ttu-id="ae501-127">作为标准邮件的嵌入邮件附件使用**IMessage** , 而 TNEF 格式的邮件使用**IStream**。</span><span class="sxs-lookup"><span data-stu-id="ae501-127">Embedded message attachments that are standard messages use **IMessage** whereas messages in the TNEF format use **IStream**.</span></span> <span data-ttu-id="ae501-128">因为**PR_CONTAINER_CONTENTS**是 table 对象, 所以可以使用[IMAPITable](imapitableiunknown.md)进行访问。</span><span class="sxs-lookup"><span data-stu-id="ae501-128">Because **PR_CONTAINER_CONTENTS** is a table object, it is accessed with [IMAPITable](imapitableiunknown.md).</span></span>
  
 <span data-ttu-id="ae501-129">**检索附件的 PR_ATTACH_DATA_BIN 属性**</span><span class="sxs-lookup"><span data-stu-id="ae501-129">**To retrieve an attachment's PR_ATTACH_DATA_BIN property**</span></span>
  
1. <span data-ttu-id="ae501-130">调用[OpenStreamOnFile](openstreamonfile.md)函数打开文件的流。</span><span class="sxs-lookup"><span data-stu-id="ae501-130">Call the [OpenStreamOnFile](openstreamonfile.md) function to open a stream for the file.</span></span> 
    
2. <span data-ttu-id="ae501-131">调用邮件的[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法以检索**IStream**接口的**PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="ae501-131">Call the message's [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method to retrieve the **PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) property with the **IStream** interface.</span></span> <span data-ttu-id="ae501-132">同时设置 MAPI_MODIFY 和 MAPI_CREATE 标志。</span><span class="sxs-lookup"><span data-stu-id="ae501-132">Set both the MAPI_MODIFY and MAPI_CREATE flags.</span></span> 
    
3. <span data-ttu-id="ae501-133">分配一个**STATSTG**结构, 并在调用文件流的**IStream:: Stat**方法以确定其大小时传递该结构。</span><span class="sxs-lookup"><span data-stu-id="ae501-133">Allocate a **STATSTG** structure and pass it in a call to the file stream's **IStream::Stat** method to determine its size.</span></span> <span data-ttu-id="ae501-134">确定流大小的另一种方法是调用**IStream:: Seek** with 标志 STREAM_SEEK_END。</span><span class="sxs-lookup"><span data-stu-id="ae501-134">Another way to determine stream size is to call **IStream::Seek** with the flag STREAM_SEEK_END.</span></span> 
    
4. <span data-ttu-id="ae501-135">调用流的**IStream:: CopyTo**方法将数据从文件的流复制到附件流。</span><span class="sxs-lookup"><span data-stu-id="ae501-135">Call the stream's **IStream::CopyTo** method to copy the data from the file's stream into the attachment stream.</span></span> 
    
5. <span data-ttu-id="ae501-136">复制操作完成后, 通过调用其**IUnknown:: release**方法来释放两个流。</span><span class="sxs-lookup"><span data-stu-id="ae501-136">When the copy operation is finished, release both streams by calling their **IUnknown::Release** methods.</span></span> 
    
<span data-ttu-id="ae501-137">当将**IStream**用于属性访问时, 某些服务提供程序会自动将该属性的大小与流一起发送回来。</span><span class="sxs-lookup"><span data-stu-id="ae501-137">When **IStream** is used for property access, some service providers automatically send the size of the property back with the stream.</span></span> <span data-ttu-id="ae501-138">使用 MAPI_DEFERRED_ERRORS 标志调用**OpenProperty**会延迟属性的打开和流大小的返回。</span><span class="sxs-lookup"><span data-stu-id="ae501-138">Calling **OpenProperty** with the MAPI_DEFERRED_ERRORS flag can delay the opening of the property and the return of the stream size.</span></span> <span data-ttu-id="ae501-139">如果调用**IStream:: Stat**以在使用 MAPI_DEFERRED_ERRORS 标志集的**OpenProperty**之后检索此大小, 则性能将受到影响, 因为此调用序列将强制执行额外的远程过程调用。</span><span class="sxs-lookup"><span data-stu-id="ae501-139">If **IStream::Stat** is called to retrieve this size after **OpenProperty** with the MAPI_DEFERRED_ERRORS flag set, performance will be impacted because this sequence of calls forces an extra remote procedure call.</span></span> <span data-ttu-id="ae501-140">若要避免性能下降, 客户端可以调用对**OpenProperty**和**Stat**的调用之间的任何 MAPI 方法。</span><span class="sxs-lookup"><span data-stu-id="ae501-140">To avoid the performance hit, clients can call any MAPI method between the calls to **OpenProperty** and to **Stat**.</span></span>
  
<span data-ttu-id="ae501-141">[HrGetOneProp](hrgetoneprop.md)函数 (如**OpenProperty**) 一次打开一个属性。</span><span class="sxs-lookup"><span data-stu-id="ae501-141">The [HrGetOneProp](hrgetoneprop.md) function, like **OpenProperty**, opens one property at a time.</span></span> <span data-ttu-id="ae501-142">仅当本地计算机上存在目标对象时, 才应使用**HrGetOneProp** 。</span><span class="sxs-lookup"><span data-stu-id="ae501-142">**HrGetOneProp** should only be used when the target object exists on the local machine.</span></span> <span data-ttu-id="ae501-143">如果目标对象不是本地可用的, 则重复使用**HrGetOneProp**会导致多个远程过程调用, 并导致性能下降。</span><span class="sxs-lookup"><span data-stu-id="ae501-143">When the target object is not locally available, using **HrGetOneProp** repeatedly can result in multiple remote procedure calls and a performance degradation.</span></span> 
  
<span data-ttu-id="ae501-144">需要多个属性的调用方可以在循环中调用**HrGetOneProp**或**OpenProperty** , 也可以调用**GetProps**的一个调用。</span><span class="sxs-lookup"><span data-stu-id="ae501-144">Callers that need several properties can either call **HrGetOneProp** or **OpenProperty** in a loop or make one call to **GetProps**.</span></span> <span data-ttu-id="ae501-145">调用**GetProps**一次效率更高。</span><span class="sxs-lookup"><span data-stu-id="ae501-145">Calling **GetProps** once is more efficient.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ae501-146">安全属性不会自动与**GetProps**、 **HrGetOneProp**或**GetPropList**调用中的其他属性一起使用。</span><span class="sxs-lookup"><span data-stu-id="ae501-146">Secure properties are not automatically available with other properties in a **GetProps**, **HrGetOneProp**, or **GetPropList** call.</span></span> <span data-ttu-id="ae501-147">必须使用属性标识符显式请求安全属性。</span><span class="sxs-lookup"><span data-stu-id="ae501-147">Secure properties must be explicitly requested using their property identifiers.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ae501-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ae501-148">See also</span></span>



[<span data-ttu-id="ae501-149">MAPI 属性概述</span><span class="sxs-lookup"><span data-stu-id="ae501-149">MAPI Property Overview</span></span>](mapi-property-overview.md)

