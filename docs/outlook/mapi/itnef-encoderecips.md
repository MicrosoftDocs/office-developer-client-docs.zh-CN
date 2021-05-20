---
title: ITnefEncodeRecips
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ITnef.EncodeRecips
api_type:
- COM
ms.assetid: b3ce4b0e-4f48-4a7e-a30c-c4754bccb12c
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: d8caa503e557d35e259db743505d39ea4809dbfd
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437649"
---
# <a name="itnefencoderecips"></a><span data-ttu-id="0c10d-103">ITnef::EncodeRecips</span><span class="sxs-lookup"><span data-stu-id="0c10d-103">ITnef::EncodeRecips</span></span>

  
  
<span data-ttu-id="0c10d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0c10d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0c10d-105">将邮件收件人表的视图编码为Transport-Neutral封装格式 (TNEF) 流。</span><span class="sxs-lookup"><span data-stu-id="0c10d-105">Encodes a view for a message's recipient table in the Transport-Neutral Encapsulation Format (TNEF) data stream for the message.</span></span>
  
```cpp
HRESULT EncodeRecips(
  ULONG ulFlags,
  LPMAPITABLE lpRecipientTable
);
```

## <a name="parameters"></a><span data-ttu-id="0c10d-106">参数</span><span class="sxs-lookup"><span data-stu-id="0c10d-106">Parameters</span></span>

 <span data-ttu-id="0c10d-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="0c10d-107">_ulFlags_</span></span>
  
> <span data-ttu-id="0c10d-108">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="0c10d-108">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="0c10d-109">_lpRecipientTable_</span><span class="sxs-lookup"><span data-stu-id="0c10d-109">_lpRecipientTable_</span></span>
  
> <span data-ttu-id="0c10d-110">[in]指向视图已编码的收件人表的指针。</span><span class="sxs-lookup"><span data-stu-id="0c10d-110">[in] A pointer to the recipient table for which the view is encoded.</span></span> <span data-ttu-id="0c10d-111">_lpRecipientTable_ 参数可以是 NULL。</span><span class="sxs-lookup"><span data-stu-id="0c10d-111">The  _lpRecipientTable_ parameter can be NULL.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="0c10d-112">返回值</span><span class="sxs-lookup"><span data-stu-id="0c10d-112">Return value</span></span>

<span data-ttu-id="0c10d-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="0c10d-113">S_OK</span></span> 
  
> <span data-ttu-id="0c10d-114">调用成功并返回预期值。</span><span class="sxs-lookup"><span data-stu-id="0c10d-114">The call succeeded and returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="0c10d-115">备注</span><span class="sxs-lookup"><span data-stu-id="0c10d-115">Remarks</span></span>

<span data-ttu-id="0c10d-116">传输提供程序、邮件存储提供程序和网关调用 **ITnef：：EncodeRecips** 方法来对特定的收件人表视图执行 TNEF 编码。</span><span class="sxs-lookup"><span data-stu-id="0c10d-116">Transport providers, message store providers, and gateways call the **ITnef::EncodeRecips** method to perform TNEF encoding for a particular recipient table view.</span></span> <span data-ttu-id="0c10d-117">TNEF 编码很有用，例如，如果提供程序或网关需要收件人表的特定列集、排序顺序或限制。</span><span class="sxs-lookup"><span data-stu-id="0c10d-117">TNEF encoding is useful, for example, if a provider or gateway requires a particular column set, sort order, or restriction for the recipient table.</span></span> 
  
<span data-ttu-id="0c10d-118">提供程序或网关传递表视图以在  _lpRecipientTable_ 参数中编码。</span><span class="sxs-lookup"><span data-stu-id="0c10d-118">A provider or gateway passes the table view to be encoded in the  _lpRecipientTable_ parameter.</span></span> <span data-ttu-id="0c10d-119">TNEF 实现使用给定列集、排序顺序、限制和位置对给定视图的收件人表进行编码。</span><span class="sxs-lookup"><span data-stu-id="0c10d-119">The TNEF implementation encodes the recipient table with the given view, using the given column set, sort order, restriction, and position.</span></span> <span data-ttu-id="0c10d-120">如果提供程序或网关在  _lpRecipientTable_ 中传递 NULL，则 TNEF 从使用 [IMessage：：GetRecipientTable](imessage-getrecipienttable.md) 方法编码的邮件获取收件人表，然后使用表的当前设置将表的每一行处理到 TNEF 流中。</span><span class="sxs-lookup"><span data-stu-id="0c10d-120">If a provider or gateway passes NULL in  _lpRecipientTable_, TNEF gets the recipient table from the message being encoded by using the [IMessage::GetRecipientTable](imessage-getrecipienttable.md) method, and processes every row of the table into the TNEF stream by using the table's current settings.</span></span> 
  
<span data-ttu-id="0c10d-121">因此，在 _lpRecipientTable_ 中调用 NULL 的 **EncodeRecips** 会编码所有邮件收件人，并且等效于在其 _ulFlags_ 参数中调用具有 TNEF_PROP_INCLUDE 标志的 [ITnef：：AddProps](itnef-addprops.md)方法，以及其 _lpPropList_ 参数中的 **PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="0c10d-121">Calling **EncodeRecips** with NULL in  _lpRecipientTable_ thus encodes all message recipients and is equivalent to calling the [ITnef::AddProps](itnef-addprops.md) method with the TNEF_PROP_INCLUDE flag in its  _ulFlags_ parameter and the **PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) property in its  _lpPropList_ parameter.</span></span> 
  
<span data-ttu-id="0c10d-122">请注意，除非要求对特定的收件人表视图进行编码，否则很少需要调用 **EncodeRecips。**</span><span class="sxs-lookup"><span data-stu-id="0c10d-122">Note that it is rarely necessary to call **EncodeRecips** unless there is a requirement to encode a particular recipient table view.</span></span> <span data-ttu-id="0c10d-123">外消息系统几乎始终具有处理收件人列表所需的工具，这些收件人列表功能足够强大，足以满足对收件人列表进行编码的常见需求;因此，这些系统几乎永远不会需要 TNEF 来达到此目的。</span><span class="sxs-lookup"><span data-stu-id="0c10d-123">Foreign messaging systems almost always have facilities for handling recipient lists that are powerful enough to handle the common needs of encoding recipient lists; therefore, these systems almost never require TNEF for this purpose.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="0c10d-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0c10d-124">See also</span></span>



[<span data-ttu-id="0c10d-125">IMessage::GetRecipientTable</span><span class="sxs-lookup"><span data-stu-id="0c10d-125">IMessage::GetRecipientTable</span></span>](imessage-getrecipienttable.md)
  
[<span data-ttu-id="0c10d-126">ITnef::AddProps</span><span class="sxs-lookup"><span data-stu-id="0c10d-126">ITnef::AddProps</span></span>](itnef-addprops.md)
  
[<span data-ttu-id="0c10d-127">PidTagMessageRecipients 规范属性</span><span class="sxs-lookup"><span data-stu-id="0c10d-127">PidTagMessageRecipients Canonical Property</span></span>](pidtagmessagerecipients-canonical-property.md)
  
[<span data-ttu-id="0c10d-128">ITnef : IUnknown</span><span class="sxs-lookup"><span data-stu-id="0c10d-128">ITnef : IUnknown</span></span>](itnefiunknown.md)

