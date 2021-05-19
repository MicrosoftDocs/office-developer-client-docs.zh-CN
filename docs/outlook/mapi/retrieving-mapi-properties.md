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
# <a name="retrieving-mapi-properties"></a><span data-ttu-id="1111b-103">检索 MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="1111b-103">Retrieving MAPI Properties</span></span>

 
  
<span data-ttu-id="1111b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1111b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1111b-105">当客户端或服务提供商从对象检索属性时，对象会提供属性的值、类型和标识符。</span><span class="sxs-lookup"><span data-stu-id="1111b-105">When a client or service provider retrieves a property from an object, the object makes available the property's value, type, and identifier.</span></span> 
  
<span data-ttu-id="1111b-106">客户端和服务提供商可以通过调用下列方法之一检索对象的属性：</span><span class="sxs-lookup"><span data-stu-id="1111b-106">Clients and service providers can retrieve an object's properties by calling one of the following:</span></span>
  
[<span data-ttu-id="1111b-107">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="1111b-107">IMAPIProp::GetProps</span></span>](imapiprop-getprops.md)
  
[<span data-ttu-id="1111b-108">IMAPIProp::OpenProperty</span><span class="sxs-lookup"><span data-stu-id="1111b-108">IMAPIProp::OpenProperty</span></span>](imapiprop-openproperty.md)
  
[<span data-ttu-id="1111b-109">HrGetOneProp</span><span class="sxs-lookup"><span data-stu-id="1111b-109">HrGetOneProp</span></span>](hrgetoneprop.md)
  
<span data-ttu-id="1111b-110">**GetProps** 方法用于检索一个或多个属性，这些属性不需要专用接口或备用接口来访问。</span><span class="sxs-lookup"><span data-stu-id="1111b-110">The **GetProps** method is used to retrieve one or more properties that do not need a specialized or alternate interface for access.</span></span> <span data-ttu-id="1111b-111">这意味着 **GetProps** 可用的属性较小，如整数和布尔值。</span><span class="sxs-lookup"><span data-stu-id="1111b-111">This implies that the properties available with **GetProps** are small, such as integers and Boolean values.</span></span> 
  
 <span data-ttu-id="1111b-112">**检索多个属性**</span><span class="sxs-lookup"><span data-stu-id="1111b-112">**To retrieve multiple properties**</span></span>
  
1. <span data-ttu-id="1111b-113">分配 [一个足够大的 SPropTagArray](sproptagarray.md) 结构，以容纳要检索的属性数。</span><span class="sxs-lookup"><span data-stu-id="1111b-113">Allocate an [SPropTagArray](sproptagarray.md) structure large enough to hold the number of properties to be retrieved.</span></span> 
    
2. <span data-ttu-id="1111b-114">将 **SPropTagArray** 结构的 **cValues** 成员设置为要检索的属性数，将每个 **aulPropTag** 成员设置为目标属性之一的标识符和类型（如果可能）。</span><span class="sxs-lookup"><span data-stu-id="1111b-114">Set the **cValues** member of the **SPropTagArray** structure to the number of properties to be retrieved and set each **aulPropTag** member to the identifier and type, if possible, of one of the target properties.</span></span> <span data-ttu-id="1111b-115">如果类型未知，请设置为PT_UNSPECIFIED。</span><span class="sxs-lookup"><span data-stu-id="1111b-115">If the type is unknown, set it to PT_UNSPECIFIED.</span></span> <span data-ttu-id="1111b-116">如果类型和标识符都未知，请通过调用 [IMAPIProp：：GetPropList](imapiprop-getproplist.md)找到此信息。</span><span class="sxs-lookup"><span data-stu-id="1111b-116">If both the type and the identifier are unknown, locate this information by calling [IMAPIProp::GetPropList](imapiprop-getproplist.md).</span></span> <span data-ttu-id="1111b-117">**GetPropList** 返回一个属性标记数组，该数组包含对象的所有受支持属性。</span><span class="sxs-lookup"><span data-stu-id="1111b-117">**GetPropList** returns a property tag array with all of the object's supported properties.</span></span> <span data-ttu-id="1111b-118">如果只有属性名称可用，请调用 [IMAPIProp：：GetIDsFromNames](imapiprop-getidsfromnames.md) 以访问关联的标识符。</span><span class="sxs-lookup"><span data-stu-id="1111b-118">If only a property name is available, call [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) to access the associated identifier.</span></span> 
    
3. <span data-ttu-id="1111b-119">调用 [IMAPIProp：：GetProps](imapiprop-getprops.md) 以打开属性。</span><span class="sxs-lookup"><span data-stu-id="1111b-119">Call [IMAPIProp::GetProps](imapiprop-getprops.md) to open the property or properties.</span></span> 
    
<span data-ttu-id="1111b-120">**OpenProperty** 方法用于打开需要备用接口（如 **IStream** 或 [IMAPITable）](imapitableiunknown.md)进行访问的较大属性。</span><span class="sxs-lookup"><span data-stu-id="1111b-120">The **OpenProperty** method is used to open larger properties that require an alternate interface such as **IStream** or [IMAPITable](imapitableiunknown.md) for access.</span></span> <span data-ttu-id="1111b-121">**OpenProperty** 通常用于打开大字符串、二进制和对象属性，并且一次只能打开一个属性。</span><span class="sxs-lookup"><span data-stu-id="1111b-121">**OpenProperty** is typically used to open large character string, binary, and object properties and can only open one property at a time.</span></span> <span data-ttu-id="1111b-122">调用方将所需的其他接口的标识符作为输入参数之一进行传递。</span><span class="sxs-lookup"><span data-stu-id="1111b-122">Callers pass in the identifier of the additional interface that is required as one of the input parameters.</span></span> 
  
<span data-ttu-id="1111b-123">**OpenProperty** 的一些常见用途包括PR_BODY ([PidTagBody](pidtagbody-canonical-property.md)) ， 属性（包含基于文本的邮件的正文 **、PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) 、保留 OLE 对象或邮件附件的属性）和 **PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) （保留文件夹或通讯簿容器内容表的属性）。 </span><span class="sxs-lookup"><span data-stu-id="1111b-123">Some of the common uses of **OpenProperty** include opening **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)), the property that holds the body of a text-based message, **PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)), the property that holds an OLE object or message attachment, and **PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)), the property that holds a folder or address book container contents table.</span></span> 
  
<span data-ttu-id="1111b-124">根据 属性，从 **OpenProperty** 请求不同的接口。</span><span class="sxs-lookup"><span data-stu-id="1111b-124">Depending on the property, a different interface is requested from **OpenProperty**.</span></span> <span data-ttu-id="1111b-125">**IStream** 是一个允许读取属性数据并作为字节流写入的接口，它通常用于访问 **PR_BODY。**</span><span class="sxs-lookup"><span data-stu-id="1111b-125">**IStream**, an interface that allows property data to be read and written as a stream of bytes, is typically used to access **PR_BODY**.</span></span> <span data-ttu-id="1111b-126">[IMessage 或](imessageimapiprop.md) **IStream** 可用于访问PR_ATTACH_DATA_OBJ **。**</span><span class="sxs-lookup"><span data-stu-id="1111b-126">Either [IMessage](imessageimapiprop.md) or **IStream** can be used to access **PR_ATTACH_DATA_OBJ**.</span></span> <span data-ttu-id="1111b-127">作为标准邮件的嵌入邮件附件使用 **IMessage，** 而 TNEF 格式的邮件使用 **IStream**。</span><span class="sxs-lookup"><span data-stu-id="1111b-127">Embedded message attachments that are standard messages use **IMessage** whereas messages in the TNEF format use **IStream**.</span></span> <span data-ttu-id="1111b-128">由于 **PR_CONTAINER_CONTENTS** 表对象，因此它通过 [IMAPITable 访问](imapitableiunknown.md)。</span><span class="sxs-lookup"><span data-stu-id="1111b-128">Because **PR_CONTAINER_CONTENTS** is a table object, it is accessed with [IMAPITable](imapitableiunknown.md).</span></span>
  
 <span data-ttu-id="1111b-129">**检索附件的 PR_ATTACH_DATA_BIN 属性**</span><span class="sxs-lookup"><span data-stu-id="1111b-129">**To retrieve an attachment's PR_ATTACH_DATA_BIN property**</span></span>
  
1. <span data-ttu-id="1111b-130">调用 [OpenStreamOnFile](openstreamonfile.md) 函数以打开文件的流。</span><span class="sxs-lookup"><span data-stu-id="1111b-130">Call the [OpenStreamOnFile](openstreamonfile.md) function to open a stream for the file.</span></span> 
    
2. <span data-ttu-id="1111b-131">调用邮件的 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md)方法，以使用 **IStream** 接口检索 **PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="1111b-131">Call the message's [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method to retrieve the **PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) property with the **IStream** interface.</span></span> <span data-ttu-id="1111b-132">同时设置 MAPI_MODIFY 和 MAPI_CREATE 标志。</span><span class="sxs-lookup"><span data-stu-id="1111b-132">Set both the MAPI_MODIFY and MAPI_CREATE flags.</span></span> 
    
3. <span data-ttu-id="1111b-133">分配 **STATSTG** 结构，并通过调用文件流的 **IStream：：Stat** 方法来确定其大小。</span><span class="sxs-lookup"><span data-stu-id="1111b-133">Allocate a **STATSTG** structure and pass it in a call to the file stream's **IStream::Stat** method to determine its size.</span></span> <span data-ttu-id="1111b-134">确定流大小的另一个方法为使用标志调用 **IStream：：Seek** STREAM_SEEK_END。</span><span class="sxs-lookup"><span data-stu-id="1111b-134">Another way to determine stream size is to call **IStream::Seek** with the flag STREAM_SEEK_END.</span></span> 
    
4. <span data-ttu-id="1111b-135">调用流的 **IStream：：CopyTo** 方法将数据从文件流复制到附件流。</span><span class="sxs-lookup"><span data-stu-id="1111b-135">Call the stream's **IStream::CopyTo** method to copy the data from the file's stream into the attachment stream.</span></span> 
    
5. <span data-ttu-id="1111b-136">复制操作完成后，通过调用它们的 **IUnknown：：Release** 方法释放这两个流。</span><span class="sxs-lookup"><span data-stu-id="1111b-136">When the copy operation is finished, release both streams by calling their **IUnknown::Release** methods.</span></span> 
    
<span data-ttu-id="1111b-137">当 **IStream** 用于属性访问时，某些服务提供商会自动将属性的大小随流发送回。</span><span class="sxs-lookup"><span data-stu-id="1111b-137">When **IStream** is used for property access, some service providers automatically send the size of the property back with the stream.</span></span> <span data-ttu-id="1111b-138">调用具有 MAPI_DEFERRED_ERRORS 标志的 **OpenProperty** 可能会延迟属性的打开和流大小的返回。</span><span class="sxs-lookup"><span data-stu-id="1111b-138">Calling **OpenProperty** with the MAPI_DEFERRED_ERRORS flag can delay the opening of the property and the return of the stream size.</span></span> <span data-ttu-id="1111b-139">如果在设置了 MAPI_DEFERRED_ERRORS 标志的 **OpenProperty** 之后调用 **IStream：：Stat** 以检索此大小，则性能将受到影响，因为此调用序列会强制进行额外的远程过程调用。</span><span class="sxs-lookup"><span data-stu-id="1111b-139">If **IStream::Stat** is called to retrieve this size after **OpenProperty** with the MAPI_DEFERRED_ERRORS flag set, performance will be impacted because this sequence of calls forces an extra remote procedure call.</span></span> <span data-ttu-id="1111b-140">为了避免性能下降，客户端可以在调用 **OpenProperty** 和 **Stat** 之间调用任何 MAPI 方法。</span><span class="sxs-lookup"><span data-stu-id="1111b-140">To avoid the performance hit, clients can call any MAPI method between the calls to **OpenProperty** and to **Stat**.</span></span>
  
<span data-ttu-id="1111b-141">[HrGetOneProp](hrgetoneprop.md)函数（如 **OpenProperty）** 一次打开一个属性。</span><span class="sxs-lookup"><span data-stu-id="1111b-141">The [HrGetOneProp](hrgetoneprop.md) function, like **OpenProperty**, opens one property at a time.</span></span> <span data-ttu-id="1111b-142">只有当目标对象存在于本地计算机上时，才应使用 **HrGetOneProp。**</span><span class="sxs-lookup"><span data-stu-id="1111b-142">**HrGetOneProp** should only be used when the target object exists on the local machine.</span></span> <span data-ttu-id="1111b-143">当目标对象在本地不可用时，重复使用 **HrGetOneProp** 会导致多个远程过程调用和性能下降。</span><span class="sxs-lookup"><span data-stu-id="1111b-143">When the target object is not locally available, using **HrGetOneProp** repeatedly can result in multiple remote procedure calls and a performance degradation.</span></span> 
  
<span data-ttu-id="1111b-144">需要多个属性的调用方可以在循环中调用 **HrGetOneProp** 或 **OpenProperty，** 也可以对 **GetProps** 进行一次调用。</span><span class="sxs-lookup"><span data-stu-id="1111b-144">Callers that need several properties can either call **HrGetOneProp** or **OpenProperty** in a loop or make one call to **GetProps**.</span></span> <span data-ttu-id="1111b-145">调用 **GetProps 一** 次会更有效。</span><span class="sxs-lookup"><span data-stu-id="1111b-145">Calling **GetProps** once is more efficient.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1111b-146">安全属性不会自动与 **GetProps、HrGetOneProp** 或 **GetPropList** 调用中的其他属性一起提供。</span><span class="sxs-lookup"><span data-stu-id="1111b-146">Secure properties are not automatically available with other properties in a **GetProps**, **HrGetOneProp**, or **GetPropList** call.</span></span> <span data-ttu-id="1111b-147">必须使用安全属性的属性标识符显式请求。</span><span class="sxs-lookup"><span data-stu-id="1111b-147">Secure properties must be explicitly requested using their property identifiers.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="1111b-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1111b-148">See also</span></span>



[<span data-ttu-id="1111b-149">MAPI 属性概述</span><span class="sxs-lookup"><span data-stu-id="1111b-149">MAPI Property Overview</span></span>](mapi-property-overview.md)

