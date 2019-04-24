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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348655"
---
# <a name="itnefencoderecips"></a><span data-ttu-id="b81b8-103">ITnef::EncodeRecips</span><span class="sxs-lookup"><span data-stu-id="b81b8-103">ITnef::EncodeRecips</span></span>

  
  
<span data-ttu-id="b81b8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b81b8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b81b8-105">在邮件的传输中性封装格式 (TNEF) 数据流中对邮件的收件人表的视图进行编码。</span><span class="sxs-lookup"><span data-stu-id="b81b8-105">Encodes a view for a message's recipient table in the Transport-Neutral Encapsulation Format (TNEF) data stream for the message.</span></span>
  
```cpp
HRESULT EncodeRecips(
  ULONG ulFlags,
  LPMAPITABLE lpRecipientTable
);
```

## <a name="parameters"></a><span data-ttu-id="b81b8-106">参数</span><span class="sxs-lookup"><span data-stu-id="b81b8-106">Parameters</span></span>

 <span data-ttu-id="b81b8-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="b81b8-107">_ulFlags_</span></span>
  
> <span data-ttu-id="b81b8-108">实时保留必须为零。</span><span class="sxs-lookup"><span data-stu-id="b81b8-108">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="b81b8-109">_lpRecipientTable_</span><span class="sxs-lookup"><span data-stu-id="b81b8-109">_lpRecipientTable_</span></span>
  
> <span data-ttu-id="b81b8-110">实时指向对其对视图进行编码的收件人表的指针。</span><span class="sxs-lookup"><span data-stu-id="b81b8-110">[in] A pointer to the recipient table for which the view is encoded.</span></span> <span data-ttu-id="b81b8-111">_lpRecipientTable_参数可以为 NULL。</span><span class="sxs-lookup"><span data-stu-id="b81b8-111">The  _lpRecipientTable_ parameter can be NULL.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="b81b8-112">返回值</span><span class="sxs-lookup"><span data-stu-id="b81b8-112">Return value</span></span>

<span data-ttu-id="b81b8-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="b81b8-113">S_OK</span></span> 
  
> <span data-ttu-id="b81b8-114">调用成功, 并返回了所需的一个或一些值。</span><span class="sxs-lookup"><span data-stu-id="b81b8-114">The call succeeded and returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="b81b8-115">注解</span><span class="sxs-lookup"><span data-stu-id="b81b8-115">Remarks</span></span>

<span data-ttu-id="b81b8-116">传输提供程序、邮件存储提供程序和网关调用**ITnef:: EncodeRecips**方法来执行特定收件人表视图的 TNEF 编码。</span><span class="sxs-lookup"><span data-stu-id="b81b8-116">Transport providers, message store providers, and gateways call the **ITnef::EncodeRecips** method to perform TNEF encoding for a particular recipient table view.</span></span> <span data-ttu-id="b81b8-117">例如, 如果提供程序或网关需要特定的列集、排序顺序或对收件人表的限制, 则 TNEF 编码非常有用。</span><span class="sxs-lookup"><span data-stu-id="b81b8-117">TNEF encoding is useful, for example, if a provider or gateway requires a particular column set, sort order, or restriction for the recipient table.</span></span> 
  
<span data-ttu-id="b81b8-118">提供程序或网关传递要在_lpRecipientTable_参数中进行编码的表视图。</span><span class="sxs-lookup"><span data-stu-id="b81b8-118">A provider or gateway passes the table view to be encoded in the  _lpRecipientTable_ parameter.</span></span> <span data-ttu-id="b81b8-119">TNEF 实现使用给定的列集、排序顺序、限制和位置对收件人表使用给定的视图进行编码。</span><span class="sxs-lookup"><span data-stu-id="b81b8-119">The TNEF implementation encodes the recipient table with the given view, using the given column set, sort order, restriction, and position.</span></span> <span data-ttu-id="b81b8-120">如果提供程序或网关在_lpRecipientTable_中传递了 NULL, TNEF 将从使用[IMessage:: GetRecipientTable](imessage-getrecipienttable.md)方法进行编码的邮件中获取收件人表, 并使用将表中的每一行处理到 TNEF 流中。表的当前设置。</span><span class="sxs-lookup"><span data-stu-id="b81b8-120">If a provider or gateway passes NULL in  _lpRecipientTable_, TNEF gets the recipient table from the message being encoded by using the [IMessage::GetRecipientTable](imessage-getrecipienttable.md) method, and processes every row of the table into the TNEF stream by using the table's current settings.</span></span> 
  
<span data-ttu-id="b81b8-121">因此, 使用_lpRecipientTable_中的 NULL 调用**EncodeRecips**将对所有邮件收件人进行编码, 并且相当于在其_TNEF_PROP_INCLUDE_参数和 ulFlags 中调用[ITnef:: AddProps](itnef-addprops.md)方法和 PR_ 标记。 **MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 属性在其_lpPropList_参数中。</span><span class="sxs-lookup"><span data-stu-id="b81b8-121">Calling **EncodeRecips** with NULL in  _lpRecipientTable_ thus encodes all message recipients and is equivalent to calling the [ITnef::AddProps](itnef-addprops.md) method with the TNEF_PROP_INCLUDE flag in its  _ulFlags_ parameter and the **PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) property in its  _lpPropList_ parameter.</span></span> 
  
<span data-ttu-id="b81b8-122">请注意, 如果需要对特定收件人表视图进行编码, 则几乎不需要调用**EncodeRecips** 。</span><span class="sxs-lookup"><span data-stu-id="b81b8-122">Note that it is rarely necessary to call **EncodeRecips** unless there is a requirement to encode a particular recipient table view.</span></span> <span data-ttu-id="b81b8-123">外部邮件系统几乎总是有处理可满足编码收件人列表的常见需求的收件人列表的功能;因此, 这些系统几乎不需要 TNEF 即可实现此目的。</span><span class="sxs-lookup"><span data-stu-id="b81b8-123">Foreign messaging systems almost always have facilities for handling recipient lists that are powerful enough to handle the common needs of encoding recipient lists; therefore, these systems almost never require TNEF for this purpose.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="b81b8-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b81b8-124">See also</span></span>



[<span data-ttu-id="b81b8-125">IMessage::GetRecipientTable</span><span class="sxs-lookup"><span data-stu-id="b81b8-125">IMessage::GetRecipientTable</span></span>](imessage-getrecipienttable.md)
  
[<span data-ttu-id="b81b8-126">ITnef::AddProps</span><span class="sxs-lookup"><span data-stu-id="b81b8-126">ITnef::AddProps</span></span>](itnef-addprops.md)
  
[<span data-ttu-id="b81b8-127">PidTagMessageRecipients 规范属性</span><span class="sxs-lookup"><span data-stu-id="b81b8-127">PidTagMessageRecipients Canonical Property</span></span>](pidtagmessagerecipients-canonical-property.md)
  
[<span data-ttu-id="b81b8-128">ITnef : IUnknown</span><span class="sxs-lookup"><span data-stu-id="b81b8-128">ITnef : IUnknown</span></span>](itnefiunknown.md)

