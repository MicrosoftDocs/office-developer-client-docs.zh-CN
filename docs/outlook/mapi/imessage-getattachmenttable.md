---
title: IMessageGetAttachmentTable
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMessage.GetAttachmentTable
api_type:
- COM
ms.assetid: e568917e-6085-4094-8728-89ba90a78c40
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 9a77d335f3c8980de29dab6e14079c83bd711b43
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421170"
---
# <a name="imessagegetattachmenttable"></a><span data-ttu-id="27a09-103">IMessage::GetAttachmentTable</span><span class="sxs-lookup"><span data-stu-id="27a09-103">IMessage::GetAttachmentTable</span></span>

  
  
<span data-ttu-id="27a09-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="27a09-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="27a09-105">返回邮件的附件表。</span><span class="sxs-lookup"><span data-stu-id="27a09-105">Returns the message's attachment table.</span></span>
  
```cpp
HRESULT GetAttachmentTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a><span data-ttu-id="27a09-106">参数</span><span class="sxs-lookup"><span data-stu-id="27a09-106">Parameters</span></span>

 <span data-ttu-id="27a09-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="27a09-107">_ulFlags_</span></span>
  
> <span data-ttu-id="27a09-108">[in]与表的创建相关的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="27a09-108">[in] Bitmask of flags that relate to the creation of the table.</span></span> <span data-ttu-id="27a09-109">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="27a09-109">The following flag can be set:</span></span> 
    
<span data-ttu-id="27a09-110">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="27a09-110">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="27a09-111">字符串列采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="27a09-111">The string columns are in Unicode format.</span></span> <span data-ttu-id="27a09-112">如果未MAPI_UNICODE，则字符串列采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="27a09-112">If the MAPI_UNICODE flag is not set, the string columns are in ANSI format.</span></span>
    
<span data-ttu-id="27a09-113">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="27a09-113">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="27a09-114">允许在表完全可供调用客户端使用之前，成功返回 **GetAttachmentTable。**</span><span class="sxs-lookup"><span data-stu-id="27a09-114">Allows **GetAttachmentTable** to return successfully, possibly before the table is fully available to the calling client.</span></span> <span data-ttu-id="27a09-115">如果表不可用，则对该表进行后续调用会导致错误。</span><span class="sxs-lookup"><span data-stu-id="27a09-115">If the table is not available, making a subsequent call to it can cause an error.</span></span> 
    
 <span data-ttu-id="27a09-116">_lppTable_</span><span class="sxs-lookup"><span data-stu-id="27a09-116">_lppTable_</span></span>
  
> <span data-ttu-id="27a09-117">[out]指向指向附件表的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="27a09-117">[out] Pointer to a pointer to the attachment table.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="27a09-118">返回值</span><span class="sxs-lookup"><span data-stu-id="27a09-118">Return value</span></span>

<span data-ttu-id="27a09-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="27a09-119">S_OK</span></span> 
  
> <span data-ttu-id="27a09-120">已成功检索附件表。</span><span class="sxs-lookup"><span data-stu-id="27a09-120">The attachment table was successfully retrieved.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="27a09-121">备注</span><span class="sxs-lookup"><span data-stu-id="27a09-121">Remarks</span></span>

<span data-ttu-id="27a09-122">**IMessage：：GetAttachmentTable** 方法返回一个指向邮件附件表的指针，其中包括有关邮件中所有附件的信息。</span><span class="sxs-lookup"><span data-stu-id="27a09-122">The **IMessage::GetAttachmentTable** method returns a pointer to the message's attachment table, which includes information about all of the attachments in the message.</span></span> <span data-ttu-id="27a09-123">客户端只能通过附件表访问附件。</span><span class="sxs-lookup"><span data-stu-id="27a09-123">Clients can get access to an attachment only through the attachment table.</span></span> <span data-ttu-id="27a09-124">通过检索附件的编号PR_ATTACH_NUM ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 属性，客户端可以使用多种 **IMessage** 方法处理附件。 </span><span class="sxs-lookup"><span data-stu-id="27a09-124">By retrieving an attachment's number its **PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) property a client can use several of the **IMessage** methods to work with the attachment.</span></span> 
  
<span data-ttu-id="27a09-125">每个附件有一行。</span><span class="sxs-lookup"><span data-stu-id="27a09-125">There is one row for each attachment.</span></span> <span data-ttu-id="27a09-126">有关附件表中的列的完整列表，请参阅附件 [表](attachment-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="27a09-126">For a complete list of the columns in an attachment table, see [Attachment Tables](attachment-tables.md).</span></span>
  
<span data-ttu-id="27a09-127">附件通常不会显示在附件表中，直到通过 [调用 IMAPIProp：：SaveChanges](imapiprop-savechanges.md)保存附件和邮件。</span><span class="sxs-lookup"><span data-stu-id="27a09-127">An attachment usually does not appear in the attachment table until both the attachment and the message have been saved with a call to [IMAPIProp::SaveChanges](imapiprop-savechanges.md).</span></span> <span data-ttu-id="27a09-128">附件表是动态的。</span><span class="sxs-lookup"><span data-stu-id="27a09-128">Attachment tables are dynamic.</span></span> <span data-ttu-id="27a09-129">如果客户端在邮件的附件上执行 **SaveChanges** 调用后创建新附件、删除现有附件或更改一个或多个属性，附件表将进行更新以反映新信息。</span><span class="sxs-lookup"><span data-stu-id="27a09-129">If a client creates a new attachment, deletes an existing attachment, or changes one or more properties once the **SaveChanges** calls have been made on the attachment on the message, the attachment table will be updated to reflect the new information.</span></span> 
  
<span data-ttu-id="27a09-130">某些附件表支持各种限制;其他则不允许。</span><span class="sxs-lookup"><span data-stu-id="27a09-130">Some attachment tables support a wide variety of restrictions; others do not.</span></span> <span data-ttu-id="27a09-131">对限制的支持取决于邮件存储提供程序的实现。</span><span class="sxs-lookup"><span data-stu-id="27a09-131">Support for restrictions depends on the message store provider's implementation.</span></span> 
  
<span data-ttu-id="27a09-132">初次打开时，附件表不一定按任何特定顺序排序。</span><span class="sxs-lookup"><span data-stu-id="27a09-132">When initially opened, attachment tables are not necessarily sorted in any particular order.</span></span> 
  
<span data-ttu-id="27a09-133">在  _ulFlags_ MAPI_UNICODE设置值标记会影响对附件表的以下调用：</span><span class="sxs-lookup"><span data-stu-id="27a09-133">Setting the MAPI_UNICODE flag in the  _ulFlags_ parameter affects the following calls to the attachment table:</span></span> 
  
- <span data-ttu-id="27a09-134">[IMAPITable：：QueryColumns，](imapitable-querycolumns.md) 用于检索列集。</span><span class="sxs-lookup"><span data-stu-id="27a09-134">[IMAPITable::QueryColumns](imapitable-querycolumns.md) to retrieve the column set.</span></span> 
    
- <span data-ttu-id="27a09-135">[IMAPITable：：QueryRows，](imapitable-queryrows.md) 用于检索行。</span><span class="sxs-lookup"><span data-stu-id="27a09-135">[IMAPITable::QueryRows](imapitable-queryrows.md) to retrieve rows.</span></span> 
    
- <span data-ttu-id="27a09-136">[IMAPITable：：QuerySortOrder，](imapitable-querysortorder.md) 用于检索排序顺序。</span><span class="sxs-lookup"><span data-stu-id="27a09-136">[IMAPITable::QuerySortOrder](imapitable-querysortorder.md) to retrieve the sort order.</span></span> 
    
<span data-ttu-id="27a09-137">设置 Unicode 标志请求从这些调用返回的任何字符串列的信息采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="27a09-137">Setting the Unicode flag requests that the information for any string columns returned from these calls be in Unicode format.</span></span> <span data-ttu-id="27a09-138">但是，由于并非所有邮件存储提供程序都支持 Unicode，因此设置此标志只是一个请求。</span><span class="sxs-lookup"><span data-stu-id="27a09-138">However, because not all message store providers support Unicode, setting this flag is only a request.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="27a09-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="27a09-139">See also</span></span>



[<span data-ttu-id="27a09-140">IMessage::CreateAttach</span><span class="sxs-lookup"><span data-stu-id="27a09-140">IMessage::CreateAttach</span></span>](imessage-createattach.md)
  
[<span data-ttu-id="27a09-141">IMessage::DeleteAttach</span><span class="sxs-lookup"><span data-stu-id="27a09-141">IMessage::DeleteAttach</span></span>](imessage-deleteattach.md)
  
[<span data-ttu-id="27a09-142">IMessage::OpenAttach</span><span class="sxs-lookup"><span data-stu-id="27a09-142">IMessage::OpenAttach</span></span>](imessage-openattach.md)
  
[<span data-ttu-id="27a09-143">IMessage : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="27a09-143">IMessage : IMAPIProp</span></span>](imessageimapiprop.md)

