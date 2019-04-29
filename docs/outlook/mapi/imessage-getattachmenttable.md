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
# <a name="imessagegetattachmenttable"></a><span data-ttu-id="6d060-103">IMessage::GetAttachmentTable</span><span class="sxs-lookup"><span data-stu-id="6d060-103">IMessage::GetAttachmentTable</span></span>

  
  
<span data-ttu-id="6d060-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6d060-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6d060-105">返回邮件的附件表。</span><span class="sxs-lookup"><span data-stu-id="6d060-105">Returns the message's attachment table.</span></span>
  
```cpp
HRESULT GetAttachmentTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a><span data-ttu-id="6d060-106">参数</span><span class="sxs-lookup"><span data-stu-id="6d060-106">Parameters</span></span>

 <span data-ttu-id="6d060-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="6d060-107">_ulFlags_</span></span>
  
> <span data-ttu-id="6d060-108">实时与表创建相关的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="6d060-108">[in] Bitmask of flags that relate to the creation of the table.</span></span> <span data-ttu-id="6d060-109">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="6d060-109">The following flag can be set:</span></span> 
    
<span data-ttu-id="6d060-110">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="6d060-110">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="6d060-111">字符串列采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="6d060-111">The string columns are in Unicode format.</span></span> <span data-ttu-id="6d060-112">如果未设置 MAPI_UNICODE 标志, 则字符串列的格式为 ANSI。</span><span class="sxs-lookup"><span data-stu-id="6d060-112">If the MAPI_UNICODE flag is not set, the string columns are in ANSI format.</span></span>
    
<span data-ttu-id="6d060-113">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="6d060-113">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="6d060-114">允许**GetAttachmentTable**成功返回, 这可能在表完全可用于调用客户端之前。</span><span class="sxs-lookup"><span data-stu-id="6d060-114">Allows **GetAttachmentTable** to return successfully, possibly before the table is fully available to the calling client.</span></span> <span data-ttu-id="6d060-115">如果该表不可用, 则对其进行后续调用可能会导致出错。</span><span class="sxs-lookup"><span data-stu-id="6d060-115">If the table is not available, making a subsequent call to it can cause an error.</span></span> 
    
 <span data-ttu-id="6d060-116">_lppTable_</span><span class="sxs-lookup"><span data-stu-id="6d060-116">_lppTable_</span></span>
  
> <span data-ttu-id="6d060-117">排除指向附件表的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="6d060-117">[out] Pointer to a pointer to the attachment table.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="6d060-118">返回值</span><span class="sxs-lookup"><span data-stu-id="6d060-118">Return value</span></span>

<span data-ttu-id="6d060-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="6d060-119">S_OK</span></span> 
  
> <span data-ttu-id="6d060-120">已成功检索附件表。</span><span class="sxs-lookup"><span data-stu-id="6d060-120">The attachment table was successfully retrieved.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="6d060-121">说明</span><span class="sxs-lookup"><span data-stu-id="6d060-121">Remarks</span></span>

<span data-ttu-id="6d060-122">**IMessage:: GetAttachmentTable**方法返回指向邮件附件表的指针, 其中包含有关邮件中所有附件的信息。</span><span class="sxs-lookup"><span data-stu-id="6d060-122">The **IMessage::GetAttachmentTable** method returns a pointer to the message's attachment table, which includes information about all of the attachments in the message.</span></span> <span data-ttu-id="6d060-123">客户端只能通过附件表获取附件的访问权限。</span><span class="sxs-lookup"><span data-stu-id="6d060-123">Clients can get access to an attachment only through the attachment table.</span></span> <span data-ttu-id="6d060-124">通过检索附件编号的**PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 属性, 客户端可以使用多个**IMessage**方法来处理附件。</span><span class="sxs-lookup"><span data-stu-id="6d060-124">By retrieving an attachment's number its **PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) property a client can use several of the **IMessage** methods to work with the attachment.</span></span> 
  
<span data-ttu-id="6d060-125">每个附件都有一个行。</span><span class="sxs-lookup"><span data-stu-id="6d060-125">There is one row for each attachment.</span></span> <span data-ttu-id="6d060-126">有关附件表中的列的完整列表, 请参阅[附件表](attachment-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="6d060-126">For a complete list of the columns in an attachment table, see [Attachment Tables](attachment-tables.md).</span></span>
  
<span data-ttu-id="6d060-127">附件通常不会显示在附件表格中, 直到附件和邮件均已通过调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)保存。</span><span class="sxs-lookup"><span data-stu-id="6d060-127">An attachment usually does not appear in the attachment table until both the attachment and the message have been saved with a call to [IMAPIProp::SaveChanges](imapiprop-savechanges.md).</span></span> <span data-ttu-id="6d060-128">附件表是动态的。</span><span class="sxs-lookup"><span data-stu-id="6d060-128">Attachment tables are dynamic.</span></span> <span data-ttu-id="6d060-129">如果客户端创建新附件、删除现有附件或更改一个或多个属性, 则在对邮件上的附件进行**SaveChanges**调用之后, 附件表将进行更新以反映新的信息。</span><span class="sxs-lookup"><span data-stu-id="6d060-129">If a client creates a new attachment, deletes an existing attachment, or changes one or more properties once the **SaveChanges** calls have been made on the attachment on the message, the attachment table will be updated to reflect the new information.</span></span> 
  
<span data-ttu-id="6d060-130">某些附件表支持各种限制;而不是其他人。</span><span class="sxs-lookup"><span data-stu-id="6d060-130">Some attachment tables support a wide variety of restrictions; others do not.</span></span> <span data-ttu-id="6d060-131">对限制的支持取决于邮件存储提供程序的实现。</span><span class="sxs-lookup"><span data-stu-id="6d060-131">Support for restrictions depends on the message store provider's implementation.</span></span> 
  
<span data-ttu-id="6d060-132">最初打开时, 附件表不一定以任何特定的顺序进行排序。</span><span class="sxs-lookup"><span data-stu-id="6d060-132">When initially opened, attachment tables are not necessarily sorted in any particular order.</span></span> 
  
<span data-ttu-id="6d060-133">在_ulFlags_参数中设置 MAPI_UNICODE 标志将影响对附件表的以下调用:</span><span class="sxs-lookup"><span data-stu-id="6d060-133">Setting the MAPI_UNICODE flag in the  _ulFlags_ parameter affects the following calls to the attachment table:</span></span> 
  
- <span data-ttu-id="6d060-134">[IMAPITable:: QueryColumns](imapitable-querycolumns.md)检索列集。</span><span class="sxs-lookup"><span data-stu-id="6d060-134">[IMAPITable::QueryColumns](imapitable-querycolumns.md) to retrieve the column set.</span></span> 
    
- <span data-ttu-id="6d060-135">[IMAPITable:: QueryRows](imapitable-queryrows.md)检索行。</span><span class="sxs-lookup"><span data-stu-id="6d060-135">[IMAPITable::QueryRows](imapitable-queryrows.md) to retrieve rows.</span></span> 
    
- <span data-ttu-id="6d060-136">[IMAPITable:: QuerySortOrder](imapitable-querysortorder.md)检索排序顺序。</span><span class="sxs-lookup"><span data-stu-id="6d060-136">[IMAPITable::QuerySortOrder](imapitable-querysortorder.md) to retrieve the sort order.</span></span> 
    
<span data-ttu-id="6d060-137">设置 unicode 标志请求从这些调用返回的任何字符串列的信息都是 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="6d060-137">Setting the Unicode flag requests that the information for any string columns returned from these calls be in Unicode format.</span></span> <span data-ttu-id="6d060-138">但是, 由于并非所有邮件存储提供程序都支持 Unicode, 因此设置此标志只是一个请求。</span><span class="sxs-lookup"><span data-stu-id="6d060-138">However, because not all message store providers support Unicode, setting this flag is only a request.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6d060-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6d060-139">See also</span></span>



[<span data-ttu-id="6d060-140">IMessage::CreateAttach</span><span class="sxs-lookup"><span data-stu-id="6d060-140">IMessage::CreateAttach</span></span>](imessage-createattach.md)
  
[<span data-ttu-id="6d060-141">IMessage::DeleteAttach</span><span class="sxs-lookup"><span data-stu-id="6d060-141">IMessage::DeleteAttach</span></span>](imessage-deleteattach.md)
  
[<span data-ttu-id="6d060-142">IMessage::OpenAttach</span><span class="sxs-lookup"><span data-stu-id="6d060-142">IMessage::OpenAttach</span></span>](imessage-openattach.md)
  
[<span data-ttu-id="6d060-143">IMessage : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="6d060-143">IMessage : IMAPIProp</span></span>](imessageimapiprop.md)

