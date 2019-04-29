---
title: IMessageGetRecipientTable
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMessage.GetRecipientTable
api_type:
- COM
ms.assetid: a335dfca-44da-452e-b16f-25d314b1758f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ca42e91528cdb7e61ae3620989c4a89966db1061
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424607"
---
# <a name="imessagegetrecipienttable"></a><span data-ttu-id="917ee-103">IMessage::GetRecipientTable</span><span class="sxs-lookup"><span data-stu-id="917ee-103">IMessage::GetRecipientTable</span></span>

  
  
<span data-ttu-id="917ee-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="917ee-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="917ee-105">返回邮件的收件人表。</span><span class="sxs-lookup"><span data-stu-id="917ee-105">Returns the message's recipient table.</span></span>
  
```cpp
HRESULT GetRecipientTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a><span data-ttu-id="917ee-106">参数</span><span class="sxs-lookup"><span data-stu-id="917ee-106">Parameters</span></span>

 <span data-ttu-id="917ee-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="917ee-107">_ulFlags_</span></span>
  
> <span data-ttu-id="917ee-108">实时控制表的返回的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="917ee-108">[in] Bitmask of flags that controls the return of the table.</span></span> <span data-ttu-id="917ee-109">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="917ee-109">The following flags can be set:</span></span>
    
<span data-ttu-id="917ee-110">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="917ee-110">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="917ee-111">允许**GetRecipientTable**成功返回, 这可能在表完全可用于调用客户端之前。</span><span class="sxs-lookup"><span data-stu-id="917ee-111">Allows **GetRecipientTable** to return successfully, possibly before the table is fully available to the calling client.</span></span> <span data-ttu-id="917ee-112">如果该表不可用, 则对其进行后续调用可能会导致出错。</span><span class="sxs-lookup"><span data-stu-id="917ee-112">If the table is not available, making a subsequent call to it can cause an error.</span></span> 
    
<span data-ttu-id="917ee-113">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="917ee-113">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="917ee-114">字符串列应采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="917ee-114">String columns should be in Unicode format.</span></span> <span data-ttu-id="917ee-115">如果未设置 MAPI_UNICODE 标志, 则字符串列应为 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="917ee-115">If the MAPI_UNICODE flag is not set, the string columns should be in ANSI format.</span></span>
    
 <span data-ttu-id="917ee-116">_lppTable_</span><span class="sxs-lookup"><span data-stu-id="917ee-116">_lppTable_</span></span>
  
> <span data-ttu-id="917ee-117">排除指向收件人表的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="917ee-117">[out] Pointer to a pointer to the recipient table.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="917ee-118">返回值</span><span class="sxs-lookup"><span data-stu-id="917ee-118">Return value</span></span>

<span data-ttu-id="917ee-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="917ee-119">S_OK</span></span> 
  
> <span data-ttu-id="917ee-120">已成功返回收件人表。</span><span class="sxs-lookup"><span data-stu-id="917ee-120">The recipient table was returned successfully.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="917ee-121">说明</span><span class="sxs-lookup"><span data-stu-id="917ee-121">Remarks</span></span>

<span data-ttu-id="917ee-122">**IMessage:: GetRecipientTable**方法返回指向邮件的收件人表的指针, 其中包含有关邮件的所有收件人的信息。</span><span class="sxs-lookup"><span data-stu-id="917ee-122">The **IMessage::GetRecipientTable** method returns a pointer to the message's recipient table, which includes information about all of the recipients for the message.</span></span> <span data-ttu-id="917ee-123">每个收件人都有一个行。</span><span class="sxs-lookup"><span data-stu-id="917ee-123">There is one row for every recipient.</span></span> 
  
<span data-ttu-id="917ee-124">收件人表根据邮件是否已提交而设置了不同的列。</span><span class="sxs-lookup"><span data-stu-id="917ee-124">Recipient tables have a different column set depending on whether the message has been submitted.</span></span> <span data-ttu-id="917ee-125">有关收件人表中的列的完整列表, 请参阅[收件人表](recipient-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="917ee-125">For a complete list of the columns in a recipient table, see [Recipient Tables](recipient-tables.md).</span></span>
  
<span data-ttu-id="917ee-126">某些收件人表支持各种限制;而不是其他人。</span><span class="sxs-lookup"><span data-stu-id="917ee-126">Some recipient tables support a wide variety of restrictions; others do not.</span></span> <span data-ttu-id="917ee-127">对限制的支持取决于邮件存储提供程序的实现。</span><span class="sxs-lookup"><span data-stu-id="917ee-127">Support for restrictions depends on the message store provider's implementation.</span></span> 
  
<span data-ttu-id="917ee-128">在_ulFlags_参数中设置 MAPI_UNICODE 标志将影响对收件人表的以下调用:</span><span class="sxs-lookup"><span data-stu-id="917ee-128">Setting the MAPI_UNICODE flag in the  _ulFlags_ parameter affects the following calls to the recipient table:</span></span> 
  
- <span data-ttu-id="917ee-129">[IMAPITable:: QueryColumns](imapitable-querycolumns.md)检索列集。</span><span class="sxs-lookup"><span data-stu-id="917ee-129">[IMAPITable::QueryColumns](imapitable-querycolumns.md) to retrieve the column set.</span></span> 
    
- <span data-ttu-id="917ee-130">[IMAPITable:: QueryRows](imapitable-queryrows.md)检索行。</span><span class="sxs-lookup"><span data-stu-id="917ee-130">[IMAPITable::QueryRows](imapitable-queryrows.md) to retrieve rows.</span></span> 
    
- <span data-ttu-id="917ee-131">[IMAPITable:: QuerySortOrder](imapitable-querysortorder.md)检索排序顺序。</span><span class="sxs-lookup"><span data-stu-id="917ee-131">[IMAPITable::QuerySortOrder](imapitable-querysortorder.md) to retrieve the sort order.</span></span> 
    
<span data-ttu-id="917ee-132">设置 unicode 标志请求从这些调用返回的任何字符串列的信息都是 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="917ee-132">Setting the Unicode flag requests that the information for any string columns returned from these calls be in Unicode format.</span></span> <span data-ttu-id="917ee-133">但是, 由于并非所有邮件存储提供程序都支持 Unicode, 因此设置此标志只是一个请求。</span><span class="sxs-lookup"><span data-stu-id="917ee-133">However, because not all message store providers support Unicode, setting this flag is only a request.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="917ee-134">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="917ee-134">Notes to callers</span></span>

<span data-ttu-id="917ee-135">您可以通过调用[IMessage:: ModifyRecipients](imessage-modifyrecipients.md)方法来更改打开的收件人表。</span><span class="sxs-lookup"><span data-stu-id="917ee-135">You can change a recipient table while it is open by calling the [IMessage::ModifyRecipients](imessage-modifyrecipients.md) method.</span></span> <span data-ttu-id="917ee-136">**ModifyRecipients**添加收件人、删除收件人或修改收件人属性。</span><span class="sxs-lookup"><span data-stu-id="917ee-136">**ModifyRecipients** adds recipients, deletes recipients, or modifies recipient properties.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="917ee-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="917ee-137">See also</span></span>



[<span data-ttu-id="917ee-138">IMAPIProp::SaveChanges</span><span class="sxs-lookup"><span data-stu-id="917ee-138">IMAPIProp::SaveChanges</span></span>](imapiprop-savechanges.md)
  
[<span data-ttu-id="917ee-139">IMAPITable::QueryRows</span><span class="sxs-lookup"><span data-stu-id="917ee-139">IMAPITable::QueryRows</span></span>](imapitable-queryrows.md)
  
[<span data-ttu-id="917ee-140">IMessage::ModifyRecipients</span><span class="sxs-lookup"><span data-stu-id="917ee-140">IMessage::ModifyRecipients</span></span>](imessage-modifyrecipients.md)
  
[<span data-ttu-id="917ee-141">IMessage : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="917ee-141">IMessage : IMAPIProp</span></span>](imessageimapiprop.md)

