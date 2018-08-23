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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 6324dcc567aee48f190f8568c6c94b5ee87c731f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584562"
---
# <a name="itnefencoderecips"></a><span data-ttu-id="ff7ba-103">ITnef::EncodeRecips</span><span class="sxs-lookup"><span data-stu-id="ff7ba-103">ITnef::EncodeRecips</span></span>

  
  
<span data-ttu-id="ff7ba-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ff7ba-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ff7ba-105">将编码消息的收件人的表中的邮件传输中性封装格式 (TNEF) 数据流的视图。</span><span class="sxs-lookup"><span data-stu-id="ff7ba-105">Encodes a view for a message's recipient table in the Transport-Neutral Encapsulation Format (TNEF) data stream for the message.</span></span>
  
```cpp
HRESULT EncodeRecips(
  ULONG ulFlags,
  LPMAPITABLE lpRecipientTable
);
```

## <a name="parameters"></a><span data-ttu-id="ff7ba-106">参数</span><span class="sxs-lookup"><span data-stu-id="ff7ba-106">Parameters</span></span>

 <span data-ttu-id="ff7ba-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="ff7ba-107">_ulFlags_</span></span>
  
> <span data-ttu-id="ff7ba-108">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="ff7ba-108">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="ff7ba-109">_lpRecipientTable_</span><span class="sxs-lookup"><span data-stu-id="ff7ba-109">_lpRecipientTable_</span></span>
  
> <span data-ttu-id="ff7ba-110">[in]指向收件人为其编码视图的表的指针。</span><span class="sxs-lookup"><span data-stu-id="ff7ba-110">[in] A pointer to the recipient table for which the view is encoded.</span></span> <span data-ttu-id="ff7ba-111">_LpRecipientTable_参数可以是 NULL。</span><span class="sxs-lookup"><span data-stu-id="ff7ba-111">The  _lpRecipientTable_ parameter can be NULL.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="ff7ba-112">返回值</span><span class="sxs-lookup"><span data-stu-id="ff7ba-112">Return value</span></span>

<span data-ttu-id="ff7ba-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="ff7ba-113">S_OK</span></span> 
  
> <span data-ttu-id="ff7ba-114">呼叫成功，并返回预期的值。</span><span class="sxs-lookup"><span data-stu-id="ff7ba-114">The call succeeded and returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="ff7ba-115">注解</span><span class="sxs-lookup"><span data-stu-id="ff7ba-115">Remarks</span></span>

<span data-ttu-id="ff7ba-116">传输提供程序、 消息存储提供程序，和网关呼叫**ITnef::EncodeRecips**方法执行 TNEF 编码特定收件人表视图。</span><span class="sxs-lookup"><span data-stu-id="ff7ba-116">Transport providers, message store providers, and gateways call the **ITnef::EncodeRecips** method to perform TNEF encoding for a particular recipient table view.</span></span> <span data-ttu-id="ff7ba-117">TNEF 编码很有用，例如，如果提供程序或网关所需的特定列集、 排序顺序或限制的收件人的表。</span><span class="sxs-lookup"><span data-stu-id="ff7ba-117">TNEF encoding is useful, for example, if a provider or gateway requires a particular column set, sort order, or restriction for the recipient table.</span></span> 
  
<span data-ttu-id="ff7ba-118">提供程序或网关传递编码_lpRecipientTable_参数中的表视图。</span><span class="sxs-lookup"><span data-stu-id="ff7ba-118">A provider or gateway passes the table view to be encoded in the  _lpRecipientTable_ parameter.</span></span> <span data-ttu-id="ff7ba-119">TNEF 实现进行编码收件人表与给定视图中，使用给定的列集、 排序顺序、 限制和位置。</span><span class="sxs-lookup"><span data-stu-id="ff7ba-119">The TNEF implementation encodes the recipient table with the given view, using the given column set, sort order, restriction, and position.</span></span> <span data-ttu-id="ff7ba-120">如果提供程序或网关传入_lpRecipientTable_NULL，TNEF 从邮件正在编码使用[IMessage::GetRecipientTable](imessage-getrecipienttable.md)方法，获取收件人的表和通过使用到 TNEF 流处理每个表的行表的当前设置。</span><span class="sxs-lookup"><span data-stu-id="ff7ba-120">If a provider or gateway passes NULL in  _lpRecipientTable_, TNEF gets the recipient table from the message being encoded by using the [IMessage::GetRecipientTable](imessage-getrecipienttable.md) method, and processes every row of the table into the TNEF stream by using the table's current settings.</span></span> 
  
<span data-ttu-id="ff7ba-121">_LpRecipientTable_中调用**EncodeRecips**具有 NULL 因此将编码所有邮件的收件人，并等效于调用其_ulFlags_参数和**PR_ TNEF_PROP_INCLUDE 标志[ITnef::AddProps](itnef-addprops.md)方法MESSAGE_RECIPIENTS**中其_lpPropList_参数 ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="ff7ba-121">Calling **EncodeRecips** with NULL in  _lpRecipientTable_ thus encodes all message recipients and is equivalent to calling the [ITnef::AddProps](itnef-addprops.md) method with the TNEF_PROP_INCLUDE flag in its  _ulFlags_ parameter and the **PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) property in its  _lpPropList_ parameter.</span></span> 
  
<span data-ttu-id="ff7ba-122">请注意，很少需要调用**EncodeRecips** ，除非要求进行编码特定收件人表视图。</span><span class="sxs-lookup"><span data-stu-id="ff7ba-122">Note that it is rarely necessary to call **EncodeRecips** unless there is a requirement to encode a particular recipient table view.</span></span> <span data-ttu-id="ff7ba-123">外部邮件系统始终具有用于处理了足以处理的编码收件人列表; 常见需求的收件人列表功能因此，这些系统几乎从不需要 TNEF 实现此目的。</span><span class="sxs-lookup"><span data-stu-id="ff7ba-123">Foreign messaging systems almost always have facilities for handling recipient lists that are powerful enough to handle the common needs of encoding recipient lists; therefore, these systems almost never require TNEF for this purpose.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ff7ba-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ff7ba-124">See also</span></span>



[<span data-ttu-id="ff7ba-125">IMessage::GetRecipientTable</span><span class="sxs-lookup"><span data-stu-id="ff7ba-125">IMessage::GetRecipientTable</span></span>](imessage-getrecipienttable.md)
  
[<span data-ttu-id="ff7ba-126">ITnef::AddProps</span><span class="sxs-lookup"><span data-stu-id="ff7ba-126">ITnef::AddProps</span></span>](itnef-addprops.md)
  
[<span data-ttu-id="ff7ba-127">PidTagMessageRecipients 规范属性</span><span class="sxs-lookup"><span data-stu-id="ff7ba-127">PidTagMessageRecipients Canonical Property</span></span>](pidtagmessagerecipients-canonical-property.md)
  
[<span data-ttu-id="ff7ba-128">ITnef : IUnknown</span><span class="sxs-lookup"><span data-stu-id="ff7ba-128">ITnef : IUnknown</span></span>](itnefiunknown.md)

