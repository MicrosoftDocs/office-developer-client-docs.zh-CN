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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 5908069f5fa887fd9d2e3f8c0df75f2e3d69515c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579534"
---
# <a name="imessagegetrecipienttable"></a><span data-ttu-id="a1f60-103">IMessage::GetRecipientTable</span><span class="sxs-lookup"><span data-stu-id="a1f60-103">IMessage::GetRecipientTable</span></span>

  
  
<span data-ttu-id="a1f60-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a1f60-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a1f60-105">返回邮件的收件人表。</span><span class="sxs-lookup"><span data-stu-id="a1f60-105">Returns the message's recipient table.</span></span>
  
```cpp
HRESULT GetRecipientTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a><span data-ttu-id="a1f60-106">参数</span><span class="sxs-lookup"><span data-stu-id="a1f60-106">Parameters</span></span>

 <span data-ttu-id="a1f60-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="a1f60-107">_ulFlags_</span></span>
  
> <span data-ttu-id="a1f60-108">[in]位掩码的标志，控件返回的表。</span><span class="sxs-lookup"><span data-stu-id="a1f60-108">[in] Bitmask of flags that controls the return of the table.</span></span> <span data-ttu-id="a1f60-109">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="a1f60-109">The following flags can be set:</span></span>
    
<span data-ttu-id="a1f60-110">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="a1f60-110">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="a1f60-111">允许**GetRecipientTable**返回成功，原因可能是完全可调用客户端表之前。</span><span class="sxs-lookup"><span data-stu-id="a1f60-111">Allows **GetRecipientTable** to return successfully, possibly before the table is fully available to the calling client.</span></span> <span data-ttu-id="a1f60-112">如果表不可用，请进行后续呼叫到它会导致出错。</span><span class="sxs-lookup"><span data-stu-id="a1f60-112">If the table is not available, making a subsequent call to it can cause an error.</span></span> 
    
<span data-ttu-id="a1f60-113">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="a1f60-113">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="a1f60-114">字符串列应为 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="a1f60-114">String columns should be in Unicode format.</span></span> <span data-ttu-id="a1f60-115">如果未设置 MAPI_UNICODE 标志，应以 ANSI 格式为字符串列。</span><span class="sxs-lookup"><span data-stu-id="a1f60-115">If the MAPI_UNICODE flag is not set, the string columns should be in ANSI format.</span></span>
    
 <span data-ttu-id="a1f60-116">_lppTable_</span><span class="sxs-lookup"><span data-stu-id="a1f60-116">_lppTable_</span></span>
  
> <span data-ttu-id="a1f60-117">[输出]为收件人表指针的指针。</span><span class="sxs-lookup"><span data-stu-id="a1f60-117">[out] Pointer to a pointer to the recipient table.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="a1f60-118">返回值</span><span class="sxs-lookup"><span data-stu-id="a1f60-118">Return value</span></span>

<span data-ttu-id="a1f60-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="a1f60-119">S_OK</span></span> 
  
> <span data-ttu-id="a1f60-120">成功返回收件人的表。</span><span class="sxs-lookup"><span data-stu-id="a1f60-120">The recipient table was returned successfully.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="a1f60-121">注解</span><span class="sxs-lookup"><span data-stu-id="a1f60-121">Remarks</span></span>

<span data-ttu-id="a1f60-122">**IMessage::GetRecipientTable**方法返回到邮件的收件人的表，其中包括所有邮件的收件人信息的指针。</span><span class="sxs-lookup"><span data-stu-id="a1f60-122">The **IMessage::GetRecipientTable** method returns a pointer to the message's recipient table, which includes information about all of the recipients for the message.</span></span> <span data-ttu-id="a1f60-123">没有用于每个收件人的一行。</span><span class="sxs-lookup"><span data-stu-id="a1f60-123">There is one row for every recipient.</span></span> 
  
<span data-ttu-id="a1f60-124">收件人表具有一个不同的列，具体取决于是否已提交邮件设置。</span><span class="sxs-lookup"><span data-stu-id="a1f60-124">Recipient tables have a different column set depending on whether the message has been submitted.</span></span> <span data-ttu-id="a1f60-125">收件人的表中的列的完整列表，请参阅[收件人表](recipient-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="a1f60-125">For a complete list of the columns in a recipient table, see [Recipient Tables](recipient-tables.md).</span></span>
  
<span data-ttu-id="a1f60-126">某些收件人表支持多种限制;有些则没有。</span><span class="sxs-lookup"><span data-stu-id="a1f60-126">Some recipient tables support a wide variety of restrictions; others do not.</span></span> <span data-ttu-id="a1f60-127">限制对支持取决于消息存储提供程序的实现。</span><span class="sxs-lookup"><span data-stu-id="a1f60-127">Support for restrictions depends on the message store provider's implementation.</span></span> 
  
<span data-ttu-id="a1f60-128">_UlFlags_参数中设置 MAPI_UNICODE 标志会影响以下呼叫到收件人表：</span><span class="sxs-lookup"><span data-stu-id="a1f60-128">Setting the MAPI_UNICODE flag in the  _ulFlags_ parameter affects the following calls to the recipient table:</span></span> 
  
- <span data-ttu-id="a1f60-129">[IMAPITable::QueryColumns](imapitable-querycolumns.md)检索列集。</span><span class="sxs-lookup"><span data-stu-id="a1f60-129">[IMAPITable::QueryColumns](imapitable-querycolumns.md) to retrieve the column set.</span></span> 
    
- <span data-ttu-id="a1f60-130">[IMAPITable::QueryRows](imapitable-queryrows.md)检索行。</span><span class="sxs-lookup"><span data-stu-id="a1f60-130">[IMAPITable::QueryRows](imapitable-queryrows.md) to retrieve rows.</span></span> 
    
- <span data-ttu-id="a1f60-131">[IMAPITable::QuerySortOrder](imapitable-querysortorder.md) ，若要检索的排序次序。</span><span class="sxs-lookup"><span data-stu-id="a1f60-131">[IMAPITable::QuerySortOrder](imapitable-querysortorder.md) to retrieve the sort order.</span></span> 
    
<span data-ttu-id="a1f60-132">设置与这些呼叫返回任何字符串列的信息将 Unicode 格式的 Unicode 标志请求。</span><span class="sxs-lookup"><span data-stu-id="a1f60-132">Setting the Unicode flag requests that the information for any string columns returned from these calls be in Unicode format.</span></span> <span data-ttu-id="a1f60-133">但是，因为不是所有的消息存储提供程序支持 Unicode，设置此标志是仅的请求。</span><span class="sxs-lookup"><span data-stu-id="a1f60-133">However, because not all message store providers support Unicode, setting this flag is only a request.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="a1f60-134">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="a1f60-134">Notes to callers</span></span>

<span data-ttu-id="a1f60-135">打开时，调用[IMessage::ModifyRecipients](imessage-modifyrecipients.md)方法，您可以更改收件人的表。</span><span class="sxs-lookup"><span data-stu-id="a1f60-135">You can change a recipient table while it is open by calling the [IMessage::ModifyRecipients](imessage-modifyrecipients.md) method.</span></span> <span data-ttu-id="a1f60-136">**ModifyRecipients**将收件人添加、 删除收件人，或修改收件人的属性。</span><span class="sxs-lookup"><span data-stu-id="a1f60-136">**ModifyRecipients** adds recipients, deletes recipients, or modifies recipient properties.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="a1f60-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a1f60-137">See also</span></span>



[<span data-ttu-id="a1f60-138">IMAPIProp::SaveChanges</span><span class="sxs-lookup"><span data-stu-id="a1f60-138">IMAPIProp::SaveChanges</span></span>](imapiprop-savechanges.md)
  
[<span data-ttu-id="a1f60-139">IMAPITable::QueryRows</span><span class="sxs-lookup"><span data-stu-id="a1f60-139">IMAPITable::QueryRows</span></span>](imapitable-queryrows.md)
  
[<span data-ttu-id="a1f60-140">IMessage::ModifyRecipients</span><span class="sxs-lookup"><span data-stu-id="a1f60-140">IMessage::ModifyRecipients</span></span>](imessage-modifyrecipients.md)
  
[<span data-ttu-id="a1f60-141">IMessage : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="a1f60-141">IMessage : IMAPIProp</span></span>](imessageimapiprop.md)

