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
# <a name="imessagegetrecipienttable"></a><span data-ttu-id="44b60-103">IMessage::GetRecipientTable</span><span class="sxs-lookup"><span data-stu-id="44b60-103">IMessage::GetRecipientTable</span></span>

  
  
<span data-ttu-id="44b60-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="44b60-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="44b60-105">返回邮件的收件人表。</span><span class="sxs-lookup"><span data-stu-id="44b60-105">Returns the message's recipient table.</span></span>
  
```cpp
HRESULT GetRecipientTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a><span data-ttu-id="44b60-106">参数</span><span class="sxs-lookup"><span data-stu-id="44b60-106">Parameters</span></span>

 <span data-ttu-id="44b60-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="44b60-107">_ulFlags_</span></span>
  
> <span data-ttu-id="44b60-108">[in]控制表返回的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="44b60-108">[in] Bitmask of flags that controls the return of the table.</span></span> <span data-ttu-id="44b60-109">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="44b60-109">The following flags can be set:</span></span>
    
<span data-ttu-id="44b60-110">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="44b60-110">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="44b60-111">允许 **GetRecipientTable** 在表完全可供调用客户端使用之前成功返回。</span><span class="sxs-lookup"><span data-stu-id="44b60-111">Allows **GetRecipientTable** to return successfully, possibly before the table is fully available to the calling client.</span></span> <span data-ttu-id="44b60-112">如果表不可用，则对该表进行后续调用会导致错误。</span><span class="sxs-lookup"><span data-stu-id="44b60-112">If the table is not available, making a subsequent call to it can cause an error.</span></span> 
    
<span data-ttu-id="44b60-113">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="44b60-113">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="44b60-114">字符串列应为 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="44b60-114">String columns should be in Unicode format.</span></span> <span data-ttu-id="44b60-115">如果未MAPI_UNICODE，则字符串列应该采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="44b60-115">If the MAPI_UNICODE flag is not set, the string columns should be in ANSI format.</span></span>
    
 <span data-ttu-id="44b60-116">_lppTable_</span><span class="sxs-lookup"><span data-stu-id="44b60-116">_lppTable_</span></span>
  
> <span data-ttu-id="44b60-117">[out]指向收件人表的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="44b60-117">[out] Pointer to a pointer to the recipient table.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="44b60-118">返回值</span><span class="sxs-lookup"><span data-stu-id="44b60-118">Return value</span></span>

<span data-ttu-id="44b60-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="44b60-119">S_OK</span></span> 
  
> <span data-ttu-id="44b60-120">已成功返回收件人表。</span><span class="sxs-lookup"><span data-stu-id="44b60-120">The recipient table was returned successfully.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="44b60-121">备注</span><span class="sxs-lookup"><span data-stu-id="44b60-121">Remarks</span></span>

<span data-ttu-id="44b60-122">**IMessage：：GetRecipientTable** 方法返回一个指向邮件收件人表的指针，其中包括有关邮件的所有收件人的信息。</span><span class="sxs-lookup"><span data-stu-id="44b60-122">The **IMessage::GetRecipientTable** method returns a pointer to the message's recipient table, which includes information about all of the recipients for the message.</span></span> <span data-ttu-id="44b60-123">每个收件人有一行。</span><span class="sxs-lookup"><span data-stu-id="44b60-123">There is one row for every recipient.</span></span> 
  
<span data-ttu-id="44b60-124">收件人表具有不同的列集，具体取决于是否已提交邮件。</span><span class="sxs-lookup"><span data-stu-id="44b60-124">Recipient tables have a different column set depending on whether the message has been submitted.</span></span> <span data-ttu-id="44b60-125">有关收件人表中列的完整列表，请参阅 [收件人表](recipient-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="44b60-125">For a complete list of the columns in a recipient table, see [Recipient Tables](recipient-tables.md).</span></span>
  
<span data-ttu-id="44b60-126">某些收件人表支持各种限制;其他则不允许。</span><span class="sxs-lookup"><span data-stu-id="44b60-126">Some recipient tables support a wide variety of restrictions; others do not.</span></span> <span data-ttu-id="44b60-127">对限制的支持取决于邮件存储提供程序的实现。</span><span class="sxs-lookup"><span data-stu-id="44b60-127">Support for restrictions depends on the message store provider's implementation.</span></span> 
  
<span data-ttu-id="44b60-128">在  _ulFlags_ MAPI_UNICODE设置值标记会影响对收件人表的以下调用：</span><span class="sxs-lookup"><span data-stu-id="44b60-128">Setting the MAPI_UNICODE flag in the  _ulFlags_ parameter affects the following calls to the recipient table:</span></span> 
  
- <span data-ttu-id="44b60-129">[IMAPITable：：QueryColumns，](imapitable-querycolumns.md) 用于检索列集。</span><span class="sxs-lookup"><span data-stu-id="44b60-129">[IMAPITable::QueryColumns](imapitable-querycolumns.md) to retrieve the column set.</span></span> 
    
- <span data-ttu-id="44b60-130">[IMAPITable：：QueryRows，](imapitable-queryrows.md) 用于检索行。</span><span class="sxs-lookup"><span data-stu-id="44b60-130">[IMAPITable::QueryRows](imapitable-queryrows.md) to retrieve rows.</span></span> 
    
- <span data-ttu-id="44b60-131">[IMAPITable：：QuerySortOrder，](imapitable-querysortorder.md) 用于检索排序顺序。</span><span class="sxs-lookup"><span data-stu-id="44b60-131">[IMAPITable::QuerySortOrder](imapitable-querysortorder.md) to retrieve the sort order.</span></span> 
    
<span data-ttu-id="44b60-132">设置 Unicode 标志请求从这些调用返回的任何字符串列的信息采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="44b60-132">Setting the Unicode flag requests that the information for any string columns returned from these calls be in Unicode format.</span></span> <span data-ttu-id="44b60-133">但是，由于并非所有邮件存储提供程序都支持 Unicode，因此设置此标志只是一个请求。</span><span class="sxs-lookup"><span data-stu-id="44b60-133">However, because not all message store providers support Unicode, setting this flag is only a request.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="44b60-134">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="44b60-134">Notes to callers</span></span>

<span data-ttu-id="44b60-135">当收件人表打开时，可以通过调用 [IMessage：：ModifyRecipients](imessage-modifyrecipients.md) 方法更改该表。</span><span class="sxs-lookup"><span data-stu-id="44b60-135">You can change a recipient table while it is open by calling the [IMessage::ModifyRecipients](imessage-modifyrecipients.md) method.</span></span> <span data-ttu-id="44b60-136">**ModifyRecipients** 添加收件人、删除收件人或修改收件人属性。</span><span class="sxs-lookup"><span data-stu-id="44b60-136">**ModifyRecipients** adds recipients, deletes recipients, or modifies recipient properties.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="44b60-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="44b60-137">See also</span></span>



[<span data-ttu-id="44b60-138">IMAPIProp::SaveChanges</span><span class="sxs-lookup"><span data-stu-id="44b60-138">IMAPIProp::SaveChanges</span></span>](imapiprop-savechanges.md)
  
[<span data-ttu-id="44b60-139">IMAPITable::QueryRows</span><span class="sxs-lookup"><span data-stu-id="44b60-139">IMAPITable::QueryRows</span></span>](imapitable-queryrows.md)
  
[<span data-ttu-id="44b60-140">IMessage::ModifyRecipients</span><span class="sxs-lookup"><span data-stu-id="44b60-140">IMessage::ModifyRecipients</span></span>](imessage-modifyrecipients.md)
  
[<span data-ttu-id="44b60-141">IMessage : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="44b60-141">IMessage : IMAPIProp</span></span>](imessageimapiprop.md)

