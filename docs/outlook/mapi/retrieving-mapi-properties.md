---
title: 检索 MAPI 属性
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: bd3f9f59-9020-46e6-9560-86a7a0eeca20
description: 上次修改时间： 2015 年 12 月 7 日
ms.openlocfilehash: 41157b97eb28787deaf19c2e974da23dfb77e0be
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778634"
---
# <a name="retrieving-mapi-properties"></a><span data-ttu-id="b44b6-103">检索 MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b44b6-103">Retrieving MAPI Properties</span></span>

 
  
<span data-ttu-id="b44b6-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="b44b6-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="b44b6-105">当客户端或服务提供程序检索的对象的属性时，该对象可提供，该属性的值、 类型和标识符。</span><span class="sxs-lookup"><span data-stu-id="b44b6-105">When a client or service provider retrieves a property from an object, the object makes available the property's value, type, and identifier.</span></span> 
  
<span data-ttu-id="b44b6-106">客户端和服务提供商可以检索对象的属性，通过调用下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="b44b6-106">Clients and service providers can retrieve an object's properties by calling one of the following:</span></span>
  
[<span data-ttu-id="b44b6-107">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="b44b6-107">IMAPIProp::GetProps</span></span>](imapiprop-getprops.md)
  
[<span data-ttu-id="b44b6-108">IMAPIProp::OpenProperty</span><span class="sxs-lookup"><span data-stu-id="b44b6-108">IMAPIProp::OpenProperty</span></span>](imapiprop-openproperty.md)
  
[<span data-ttu-id="b44b6-109">HrGetOneProp</span><span class="sxs-lookup"><span data-stu-id="b44b6-109">HrGetOneProp</span></span>](hrgetoneprop.md)
  
<span data-ttu-id="b44b6-110">**GetProps**方法用于检索一个或多个不需要专门或备用界面进行访问的属性。</span><span class="sxs-lookup"><span data-stu-id="b44b6-110">The **GetProps** method is used to retrieve one or more properties that do not need a specialized or alternate interface for access.</span></span> <span data-ttu-id="b44b6-111">这意味着提供**GetProps**属性也小，如整数和布尔值。</span><span class="sxs-lookup"><span data-stu-id="b44b6-111">This implies that the properties available with **GetProps** are small, such as integers and Boolean values.</span></span> 
  
 <span data-ttu-id="b44b6-112">**若要检索多个属性**</span><span class="sxs-lookup"><span data-stu-id="b44b6-112">**To retrieve multiple properties**</span></span>
  
1. <span data-ttu-id="b44b6-113">分配[SPropTagArray](sproptagarray.md)结构足以容纳要检索的属性的数目。</span><span class="sxs-lookup"><span data-stu-id="b44b6-113">Allocate an [SPropTagArray](sproptagarray.md) structure large enough to hold the number of properties to be retrieved.</span></span> 
    
2. <span data-ttu-id="b44b6-114">设置为属性可检索和如果可能，之一的目标属性设置为标识符和类型，每个**aulPropTag**成员数量**cValues** **SPropTagArray**结构的成员。</span><span class="sxs-lookup"><span data-stu-id="b44b6-114">Set the **cValues** member of the **SPropTagArray** structure to the number of properties to be retrieved and set each **aulPropTag** member to the identifier and type, if possible, of one of the target properties.</span></span> <span data-ttu-id="b44b6-115">如果类型是未知，则将其设置为 PT_UNSPECIFIED。</span><span class="sxs-lookup"><span data-stu-id="b44b6-115">If the type is unknown, set it to PT_UNSPECIFIED.</span></span> <span data-ttu-id="b44b6-116">如果类型和标识符是未知，通过调用[IMAPIProp::GetPropList](imapiprop-getproplist.md)查找此信息。</span><span class="sxs-lookup"><span data-stu-id="b44b6-116">If both the type and the identifier are unknown, locate this information by calling [IMAPIProp::GetPropList](imapiprop-getproplist.md).</span></span> <span data-ttu-id="b44b6-117">**GetPropList**返回所有对象的支持属性的属性标记数组。</span><span class="sxs-lookup"><span data-stu-id="b44b6-117">**GetPropList** returns a property tag array with all of the object's supported properties.</span></span> <span data-ttu-id="b44b6-118">如果只有属性名称，则调用[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)访问关联的标识符。</span><span class="sxs-lookup"><span data-stu-id="b44b6-118">If only a property name is available, call [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) to access the associated identifier.</span></span> 
    
3. <span data-ttu-id="b44b6-119">调用[IMAPIProp::GetProps](imapiprop-getprops.md)打开或多个属性。</span><span class="sxs-lookup"><span data-stu-id="b44b6-119">Call [IMAPIProp::GetProps](imapiprop-getprops.md) to open the property or properties.</span></span> 
    
<span data-ttu-id="b44b6-120">**OpenProperty**方法用于打开较大访问需要如**IStream**或[IMAPITable](imapitableiunknown.md)备用接口的属性。</span><span class="sxs-lookup"><span data-stu-id="b44b6-120">The **OpenProperty** method is used to open larger properties that require an alternate interface such as **IStream** or [IMAPITable](imapitableiunknown.md) for access.</span></span> <span data-ttu-id="b44b6-121">**OpenProperty**通常用于将打开大型字符串、 二进制、 和对象的属性和一次只能打开一个属性。</span><span class="sxs-lookup"><span data-stu-id="b44b6-121">**OpenProperty** is typically used to open large character string, binary, and object properties and can only open one property at a time.</span></span> <span data-ttu-id="b44b6-122">呼叫者传入的其他接口所需的输入参数之一的标识符。</span><span class="sxs-lookup"><span data-stu-id="b44b6-122">Callers pass in the identifier of the additional interface that is required as one of the input parameters.</span></span> 
  
<span data-ttu-id="b44b6-123">一些**OpenProperty**的常见用途包括打开**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md))，包含**PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) 的属性包含基于文本的邮件正文的属性OLE 对象或邮件附件，并**PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md))，包含文件夹或通讯簿容器内容表的属性。</span><span class="sxs-lookup"><span data-stu-id="b44b6-123">Some of the common uses of **OpenProperty** include opening **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)), the property that holds the body of a text-based message, **PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)), the property that holds an OLE object or message attachment, and **PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)), the property that holds a folder or address book container contents table.</span></span> 
  
<span data-ttu-id="b44b6-124">具体取决于该属性，从**OpenProperty**请求时使用不同的接口。</span><span class="sxs-lookup"><span data-stu-id="b44b6-124">Depending on the property, a different interface is requested from **OpenProperty**.</span></span> <span data-ttu-id="b44b6-125">**IStream**，一个接口，允许属性数据读取和写入的字节流的形式通常用于访问**PR_BODY**。</span><span class="sxs-lookup"><span data-stu-id="b44b6-125">**IStream**, an interface that allows property data to be read and written as a stream of bytes, is typically used to access **PR_BODY**.</span></span> <span data-ttu-id="b44b6-126">[IMessage](imessageimapiprop.md)或**IStream**可用于访问**PR_ATTACH_DATA_OBJ**。</span><span class="sxs-lookup"><span data-stu-id="b44b6-126">Either [IMessage](imessageimapiprop.md) or **IStream** can be used to access **PR_ATTACH_DATA_OBJ**.</span></span> <span data-ttu-id="b44b6-127">嵌入的邮件附件的标准的邮件使用**IMessage**而 TNEF 格式中的邮件使用**IStream**。</span><span class="sxs-lookup"><span data-stu-id="b44b6-127">Embedded message attachments that are standard messages use **IMessage** whereas messages in the TNEF format use **IStream**.</span></span> <span data-ttu-id="b44b6-128">由于**PR_CONTAINER_CONTENTS** table 对象，它是使用[IMAPITable](imapitableiunknown.md)进行访问。</span><span class="sxs-lookup"><span data-stu-id="b44b6-128">Because **PR_CONTAINER_CONTENTS** is a table object, it is accessed with [IMAPITable](imapitableiunknown.md).</span></span>
  
 <span data-ttu-id="b44b6-129">**若要检索的附件 PR_ATTACH_DATA_BIN 属性**</span><span class="sxs-lookup"><span data-stu-id="b44b6-129">**To retrieve an attachment's PR_ATTACH_DATA_BIN property**</span></span>
  
1. <span data-ttu-id="b44b6-130">调用[OpenStreamOnFile](openstreamonfile.md)函数打开的文件流。</span><span class="sxs-lookup"><span data-stu-id="b44b6-130">Call the [OpenStreamOnFile](openstreamonfile.md) function to open a stream for the file.</span></span> 
    
2. <span data-ttu-id="b44b6-131">调用消息的[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法来检索**IStream**接口的**PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="b44b6-131">Call the message's [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method to retrieve the **PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) property with the **IStream** interface.</span></span> <span data-ttu-id="b44b6-132">设置的 MAPI_MODIFY 和 MAPI_CREATE 标志。</span><span class="sxs-lookup"><span data-stu-id="b44b6-132">Set both the MAPI_MODIFY and MAPI_CREATE flags.</span></span> 
    
3. <span data-ttu-id="b44b6-133">分配**STATSTG**结构并将其传递中调用的文件流**IStream::Stat**方法以确定其大小。</span><span class="sxs-lookup"><span data-stu-id="b44b6-133">Allocate a **STATSTG** structure and pass it in a call to the file stream's **IStream::Stat** method to determine its size.</span></span> <span data-ttu-id="b44b6-134">另一种方法确定流大小是与标志 STREAM_SEEK_END 调用**IStream::Seek** 。</span><span class="sxs-lookup"><span data-stu-id="b44b6-134">Another way to determine stream size is to call **IStream::Seek** with the flag STREAM_SEEK_END.</span></span> 
    
4. <span data-ttu-id="b44b6-135">调用的流**IStream::CopyTo**方法将数据从该文件流复制到附件流。</span><span class="sxs-lookup"><span data-stu-id="b44b6-135">Call the stream's **IStream::CopyTo** method to copy the data from the file's stream into the attachment stream.</span></span> 
    
5. <span data-ttu-id="b44b6-136">完成复制操作后，通过调用其**IUnknown::Release**方法释放两个流。</span><span class="sxs-lookup"><span data-stu-id="b44b6-136">When the copy operation is finished, release both streams by calling their **IUnknown::Release** methods.</span></span> 
    
<span data-ttu-id="b44b6-137">当**IStream**用于属性访问时，某些服务提供程序将自动发送流后的属性的大小。</span><span class="sxs-lookup"><span data-stu-id="b44b6-137">When **IStream** is used for property access, some service providers automatically send the size of the property back with the stream.</span></span> <span data-ttu-id="b44b6-138">调用**OpenProperty** MAPI_DEFERRED_ERRORS 与打开的属性和流大小的返回可以延迟标志。</span><span class="sxs-lookup"><span data-stu-id="b44b6-138">Calling **OpenProperty** with the MAPI_DEFERRED_ERRORS flag can delay the opening of the property and the return of the stream size.</span></span> <span data-ttu-id="b44b6-139">如果**IStream::Stat**调用来检索此大小与 MAPI_DEFERRED_ERRORS **OpenProperty**标记设置后，将会影响性能，因为此的调用序列强制额外远程过程调用。</span><span class="sxs-lookup"><span data-stu-id="b44b6-139">If **IStream::Stat** is called to retrieve this size after **OpenProperty** with the MAPI_DEFERRED_ERRORS flag set, performance will be impacted because this sequence of calls forces an extra remote procedure call.</span></span> <span data-ttu-id="b44b6-140">若要避免性能下降，客户端可以调用之间**OpenProperty**和**Stat**的调用任何 MAPI 方法。</span><span class="sxs-lookup"><span data-stu-id="b44b6-140">To avoid the performance hit, clients can call any MAPI method between the calls to **OpenProperty** and to **Stat**.</span></span>
  
<span data-ttu-id="b44b6-141">[HrGetOneProp](hrgetoneprop.md)函数，如**OpenProperty**，每次打开一个属性。</span><span class="sxs-lookup"><span data-stu-id="b44b6-141">The [HrGetOneProp](hrgetoneprop.md) function, like **OpenProperty**, opens one property at a time.</span></span> <span data-ttu-id="b44b6-142">在本地计算机上存在目标对象时，应仅使用**HrGetOneProp** 。</span><span class="sxs-lookup"><span data-stu-id="b44b6-142">**HrGetOneProp** should only be used when the target object exists on the local machine.</span></span> <span data-ttu-id="b44b6-143">不本地可用目标对象时，使用**HrGetOneProp**反复会导致多个远程过程调用和性能下降。</span><span class="sxs-lookup"><span data-stu-id="b44b6-143">When the target object is not locally available, using **HrGetOneProp** repeatedly can result in multiple remote procedure calls and a performance degradation.</span></span> 
  
<span data-ttu-id="b44b6-144">需要多个属性的呼叫者可以在一个循环呼叫**HrGetOneProp**或**OpenProperty**或进行一次调用**GetProps**。</span><span class="sxs-lookup"><span data-stu-id="b44b6-144">Callers that need several properties can either call **HrGetOneProp** or **OpenProperty** in a loop or make one call to **GetProps**.</span></span> <span data-ttu-id="b44b6-145">一次调用**GetProps**是更有效。</span><span class="sxs-lookup"><span data-stu-id="b44b6-145">Calling **GetProps** once is more efficient.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="b44b6-146">安全属性不是自动提供**GetProps**、 **HrGetOneProp**或**GetPropList**呼叫中的其他属性。</span><span class="sxs-lookup"><span data-stu-id="b44b6-146">Secure properties are not automatically available with other properties in a **GetProps**, **HrGetOneProp**, or **GetPropList** call.</span></span> <span data-ttu-id="b44b6-147">必须使用及其属性标识符显式请求安全属性。</span><span class="sxs-lookup"><span data-stu-id="b44b6-147">Secure properties must be explicitly requested using their property identifiers.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="b44b6-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b44b6-148">See also</span></span>



[<span data-ttu-id="b44b6-149">MAPI 属性概述</span><span class="sxs-lookup"><span data-stu-id="b44b6-149">MAPI Property Overview</span></span>](mapi-property-overview.md)

