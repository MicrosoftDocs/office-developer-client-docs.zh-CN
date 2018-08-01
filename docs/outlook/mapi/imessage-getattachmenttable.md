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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 275dc17a141f1c002f62a43824174458e591d4de
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775758"
---
# <a name="imessagegetattachmenttable"></a><span data-ttu-id="5de1e-103">IMessage::GetAttachmentTable</span><span class="sxs-lookup"><span data-stu-id="5de1e-103">IMessage::GetAttachmentTable</span></span>

  
  
<span data-ttu-id="5de1e-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="5de1e-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="5de1e-105">返回邮件的附件表。</span><span class="sxs-lookup"><span data-stu-id="5de1e-105">Returns the message's attachment table.</span></span>
  
```cpp
HRESULT GetAttachmentTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a><span data-ttu-id="5de1e-106">参数</span><span class="sxs-lookup"><span data-stu-id="5de1e-106">Parameters</span></span>

 <span data-ttu-id="5de1e-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="5de1e-107">_ulFlags_</span></span>
  
> <span data-ttu-id="5de1e-108">[in]创建表与相关的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="5de1e-108">[in] Bitmask of flags that relate to the creation of the table.</span></span> <span data-ttu-id="5de1e-109">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="5de1e-109">The following flag can be set:</span></span> 
    
<span data-ttu-id="5de1e-110">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="5de1e-110">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="5de1e-111">字符串列的 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="5de1e-111">The string columns are in Unicode format.</span></span> <span data-ttu-id="5de1e-112">如果未设置 MAPI_UNICODE 标志，字符串列的 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="5de1e-112">If the MAPI_UNICODE flag is not set, the string columns are in ANSI format.</span></span>
    
<span data-ttu-id="5de1e-113">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="5de1e-113">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="5de1e-114">允许**GetAttachmentTable**返回成功，原因可能是完全可调用客户端表之前。</span><span class="sxs-lookup"><span data-stu-id="5de1e-114">Allows **GetAttachmentTable** to return successfully, possibly before the table is fully available to the calling client.</span></span> <span data-ttu-id="5de1e-115">如果表不可用，请进行后续呼叫到它会导致出错。</span><span class="sxs-lookup"><span data-stu-id="5de1e-115">If the table is not available, making a subsequent call to it can cause an error.</span></span> 
    
 <span data-ttu-id="5de1e-116">_lppTable_</span><span class="sxs-lookup"><span data-stu-id="5de1e-116">_lppTable_</span></span>
  
> <span data-ttu-id="5de1e-117">[输出]为附件表指针的指针。</span><span class="sxs-lookup"><span data-stu-id="5de1e-117">[out] Pointer to a pointer to the attachment table.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="5de1e-118">返回值</span><span class="sxs-lookup"><span data-stu-id="5de1e-118">Return value</span></span>

<span data-ttu-id="5de1e-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="5de1e-119">S_OK</span></span> 
  
> <span data-ttu-id="5de1e-120">已成功检索附件表。</span><span class="sxs-lookup"><span data-stu-id="5de1e-120">The attachment table was successfully retrieved.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="5de1e-121">说明</span><span class="sxs-lookup"><span data-stu-id="5de1e-121">Remarks</span></span>

<span data-ttu-id="5de1e-122">**IMessage::GetAttachmentTable**方法返回到邮件的附件表，其中包括有关的所有附件信息消息中的指针。</span><span class="sxs-lookup"><span data-stu-id="5de1e-122">The **IMessage::GetAttachmentTable** method returns a pointer to the message's attachment table, which includes information about all of the attachments in the message.</span></span> <span data-ttu-id="5de1e-123">客户端可以获取对仅通过附件表附件的访问。</span><span class="sxs-lookup"><span data-stu-id="5de1e-123">Clients can get access to an attachment only through the attachment table.</span></span> <span data-ttu-id="5de1e-124">通过检索的附件数其**PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 属性客户端可以使用几个**IMessage**方法来处理附件。</span><span class="sxs-lookup"><span data-stu-id="5de1e-124">By retrieving an attachment's number its **PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) property a client can use several of the **IMessage** methods to work with the attachment.</span></span> 
  
<span data-ttu-id="5de1e-125">没有每个附件的一行。</span><span class="sxs-lookup"><span data-stu-id="5de1e-125">There is one row for each attachment.</span></span> <span data-ttu-id="5de1e-126">附件表中的列的完整列表，请参阅[附件表](attachment-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="5de1e-126">For a complete list of the columns in an attachment table, see [Attachment Tables](attachment-tables.md).</span></span>
  
<span data-ttu-id="5de1e-127">附件通常不显示附件表中直到附件，邮件已保存到[IMAPIProp::SaveChanges](imapiprop-savechanges.md)呼叫。</span><span class="sxs-lookup"><span data-stu-id="5de1e-127">An attachment usually does not appear in the attachment table until both the attachment and the message have been saved with a call to [IMAPIProp::SaveChanges](imapiprop-savechanges.md).</span></span> <span data-ttu-id="5de1e-128">附件表是动态的。</span><span class="sxs-lookup"><span data-stu-id="5de1e-128">Attachment tables are dynamic.</span></span> <span data-ttu-id="5de1e-129">如果客户端创建一个新附件、 删除现有附件，或更改一个或多个属性，对邮件附件进行了**SaveChanges**呼叫后，将更新附件表，以反映新的信息。</span><span class="sxs-lookup"><span data-stu-id="5de1e-129">If a client creates a new attachment, deletes an existing attachment, or changes one or more properties once the **SaveChanges** calls have been made on the attachment on the message, the attachment table will be updated to reflect the new information.</span></span> 
  
<span data-ttu-id="5de1e-130">某些附件表支持多种限制;有些则没有。</span><span class="sxs-lookup"><span data-stu-id="5de1e-130">Some attachment tables support a wide variety of restrictions; others do not.</span></span> <span data-ttu-id="5de1e-131">限制对支持取决于消息存储提供程序的实现。</span><span class="sxs-lookup"><span data-stu-id="5de1e-131">Support for restrictions depends on the message store provider's implementation.</span></span> 
  
<span data-ttu-id="5de1e-132">最初打开时，附件表不一定是任何特定顺序排序。</span><span class="sxs-lookup"><span data-stu-id="5de1e-132">When initially opened, attachment tables are not necessarily sorted in any particular order.</span></span> 
  
<span data-ttu-id="5de1e-133">_UlFlags_参数中设置 MAPI_UNICODE 标志会影响对附件表的以下调用：</span><span class="sxs-lookup"><span data-stu-id="5de1e-133">Setting the MAPI_UNICODE flag in the  _ulFlags_ parameter affects the following calls to the attachment table:</span></span> 
  
- <span data-ttu-id="5de1e-134">[IMAPITable::QueryColumns](imapitable-querycolumns.md)检索列集。</span><span class="sxs-lookup"><span data-stu-id="5de1e-134">[IMAPITable::QueryColumns](imapitable-querycolumns.md) to retrieve the column set.</span></span> 
    
- <span data-ttu-id="5de1e-135">[IMAPITable::QueryRows](imapitable-queryrows.md)检索行。</span><span class="sxs-lookup"><span data-stu-id="5de1e-135">[IMAPITable::QueryRows](imapitable-queryrows.md) to retrieve rows.</span></span> 
    
- <span data-ttu-id="5de1e-136">[IMAPITable::QuerySortOrder](imapitable-querysortorder.md) ，若要检索的排序次序。</span><span class="sxs-lookup"><span data-stu-id="5de1e-136">[IMAPITable::QuerySortOrder](imapitable-querysortorder.md) to retrieve the sort order.</span></span> 
    
<span data-ttu-id="5de1e-137">设置与这些呼叫返回任何字符串列的信息将 Unicode 格式的 Unicode 标志请求。</span><span class="sxs-lookup"><span data-stu-id="5de1e-137">Setting the Unicode flag requests that the information for any string columns returned from these calls be in Unicode format.</span></span> <span data-ttu-id="5de1e-138">但是，因为不是所有的消息存储提供程序支持 Unicode，设置此标志是仅的请求。</span><span class="sxs-lookup"><span data-stu-id="5de1e-138">However, because not all message store providers support Unicode, setting this flag is only a request.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5de1e-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5de1e-139">See also</span></span>



[<span data-ttu-id="5de1e-140">IMessage::CreateAttach</span><span class="sxs-lookup"><span data-stu-id="5de1e-140">IMessage::CreateAttach</span></span>](imessage-createattach.md)
  
[<span data-ttu-id="5de1e-141">IMessage::DeleteAttach</span><span class="sxs-lookup"><span data-stu-id="5de1e-141">IMessage::DeleteAttach</span></span>](imessage-deleteattach.md)
  
[<span data-ttu-id="5de1e-142">IMessage::OpenAttach</span><span class="sxs-lookup"><span data-stu-id="5de1e-142">IMessage::OpenAttach</span></span>](imessage-openattach.md)
  
[<span data-ttu-id="5de1e-143">IMessage : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="5de1e-143">IMessage : IMAPIProp</span></span>](imessageimapiprop.md)

