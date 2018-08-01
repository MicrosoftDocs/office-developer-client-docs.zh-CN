---
title: IMAPISupportCopyMessages
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.CopyMessages
api_type:
- COM
ms.assetid: 70f67614-af0d-43f6-99f6-391a2f5673cb
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 64b2c147acb02b6c29cf080076b6fe2e3eefb717
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775592"
---
# <a name="imapisupportcopymessages"></a><span data-ttu-id="876d7-103">IMAPISupport::CopyMessages</span><span class="sxs-lookup"><span data-stu-id="876d7-103">IMAPISupport::CopyMessages</span></span>

  
  
<span data-ttu-id="876d7-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="876d7-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="876d7-105">复制或移动邮件从一个文件夹到另一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="876d7-105">Copies or moves messages from one folder to another folder.</span></span>
  
```cpp
HRESULT CopyMessages(
  LPCIID lpSrcInterface,
  LPVOID lpSrcFolder,
  LPENTRYLIST lpMsgList,
  LPCIID lpDestInterface,
  LPVOID lpDestFolder,
  ULONG_PTR ulUIParam,
  LPMAPIPROGRESS lpProgress,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="876d7-106">参数</span><span class="sxs-lookup"><span data-stu-id="876d7-106">Parameters</span></span>

 <span data-ttu-id="876d7-107">_lpSrcInterface_</span><span class="sxs-lookup"><span data-stu-id="876d7-107">_lpSrcInterface_</span></span>
  
> <span data-ttu-id="876d7-108">[in]指向接口标识 (IID) 值，该值代表要用于访问该文件夹包含的邮件复制或移动的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="876d7-108">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the folder that contains the messages to be copied or moved.</span></span>
    
 <span data-ttu-id="876d7-109">_lpSrcFolder_</span><span class="sxs-lookup"><span data-stu-id="876d7-109">_lpSrcFolder_</span></span>
  
> <span data-ttu-id="876d7-110">[in]一个指向包含邮件复制或移动的文件夹。</span><span class="sxs-lookup"><span data-stu-id="876d7-110">[in] A pointer to the folder that contains the messages to be copied or moved.</span></span>
    
 <span data-ttu-id="876d7-111">_lpMsgList_</span><span class="sxs-lookup"><span data-stu-id="876d7-111">_lpMsgList_</span></span>
  
> <span data-ttu-id="876d7-112">[in]一个指向的标识的邮件复制或移动的项标识符数组。</span><span class="sxs-lookup"><span data-stu-id="876d7-112">[in] A pointer to an array of entry identifiers that identify the messages to be copied or moved.</span></span> 
    
 <span data-ttu-id="876d7-113">_lpDestInterface_</span><span class="sxs-lookup"><span data-stu-id="876d7-113">_lpDestInterface_</span></span>
  
> <span data-ttu-id="876d7-114">[in]指向接口标识 (IID) 值，该值代表要用于访问的复制或移动邮件的目标文件夹的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="876d7-114">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the destination folder for the copied or moved messages.</span></span>
    
 <span data-ttu-id="876d7-115">_lpDestFolder_</span><span class="sxs-lookup"><span data-stu-id="876d7-115">_lpDestFolder_</span></span>
  
> <span data-ttu-id="876d7-116">[in]一个指向的复制或移动邮件的目标文件夹。</span><span class="sxs-lookup"><span data-stu-id="876d7-116">[in] A pointer to the destination folder for the copied or moved messages.</span></span> <span data-ttu-id="876d7-117">此文件夹必须打开。</span><span class="sxs-lookup"><span data-stu-id="876d7-117">This folder must be open.</span></span>
    
 <span data-ttu-id="876d7-118">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="876d7-118">_ulUIParam_</span></span>
  
> <span data-ttu-id="876d7-119">[in]指向显示进度指示器进度对象的指针。</span><span class="sxs-lookup"><span data-stu-id="876d7-119">[in] A pointer to a progress object that displays a progress indicator.</span></span> <span data-ttu-id="876d7-120">如果在_lpProgress_传递 NULL，则消息存储提供程序将使用 MAPI 进度对象实现显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="876d7-120">If NULL is passed in  _lpProgress_, the message store provider displays a progress indicator by using the MAPI progress object implementation.</span></span> <span data-ttu-id="876d7-121">除非_ulFlags_中设置了 MESSAGE_DIALOG 标志，则将忽略该_lpProgress_参数。</span><span class="sxs-lookup"><span data-stu-id="876d7-121">The  _lpProgress_ parameter is ignored unless the MESSAGE_DIALOG flag is set in  _ulFlags_.</span></span>
    
 <span data-ttu-id="876d7-122">_lpProgress_</span><span class="sxs-lookup"><span data-stu-id="876d7-122">_lpProgress_</span></span>
  
> <span data-ttu-id="876d7-123">[in]指向显示进度指示器进度对象的指针。</span><span class="sxs-lookup"><span data-stu-id="876d7-123">[in] A pointer to a progress object that displays a progress indicator.</span></span> <span data-ttu-id="876d7-124">如果在_lpProgress_传递 NULL，则消息存储提供程序将使用 MAPI 进度对象实现显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="876d7-124">If NULL is passed in  _lpProgress_, the message store provider displays a progress indicator by using the MAPI progress object implementation.</span></span> <span data-ttu-id="876d7-125">除非_ulFlags_中设置了 MESSAGE_DIALOG 标志，则将忽略该_lpProgress_参数。</span><span class="sxs-lookup"><span data-stu-id="876d7-125">The  _lpProgress_ parameter is ignored unless the MESSAGE_DIALOG flag is set in  _ulFlags_.</span></span>
    
 <span data-ttu-id="876d7-126">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="876d7-126">_ulFlags_</span></span>
  
> <span data-ttu-id="876d7-127">[in]位掩码的标志，控制如何完成复制或移动操作。</span><span class="sxs-lookup"><span data-stu-id="876d7-127">[in] A bitmask of flags that controls how the copy or move operation is accomplished.</span></span> <span data-ttu-id="876d7-128">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="876d7-128">The following flags can be set:</span></span>
    
<span data-ttu-id="876d7-129">MESSAGE_DIALOG</span><span class="sxs-lookup"><span data-stu-id="876d7-129">MESSAGE_DIALOG</span></span> 
  
> <span data-ttu-id="876d7-130">请求进度指示器的显示。</span><span class="sxs-lookup"><span data-stu-id="876d7-130">Requests the display of a progress indicator.</span></span>
    
<span data-ttu-id="876d7-131">MESSAGE_MOVE</span><span class="sxs-lookup"><span data-stu-id="876d7-131">MESSAGE_MOVE</span></span> 
  
> <span data-ttu-id="876d7-132">应移动邮件，而不是复制。</span><span class="sxs-lookup"><span data-stu-id="876d7-132">The messages should be moved, instead of copied.</span></span> <span data-ttu-id="876d7-133">如果未设置 MESSAGE_MOVE，邮件所复制。</span><span class="sxs-lookup"><span data-stu-id="876d7-133">If MESSAGE_MOVE is not set, the messages are copied.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="876d7-134">返回值</span><span class="sxs-lookup"><span data-stu-id="876d7-134">Return value</span></span>

<span data-ttu-id="876d7-135">S_OK</span><span class="sxs-lookup"><span data-stu-id="876d7-135">S_OK</span></span> 
  
> <span data-ttu-id="876d7-136">复制或移动操作已成功。</span><span class="sxs-lookup"><span data-stu-id="876d7-136">The copy or move operation was successful.</span></span>
    
<span data-ttu-id="876d7-137">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="876d7-137">MAPI_E_USER_CANCEL</span></span> 
  
> <span data-ttu-id="876d7-138">用户取消操作，通常通过单击对话框中的**取消**按钮。</span><span class="sxs-lookup"><span data-stu-id="876d7-138">The user canceled the operation, typically by clicking the **Cancel** button in a dialog box.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="876d7-139">说明</span><span class="sxs-lookup"><span data-stu-id="876d7-139">Remarks</span></span>

<span data-ttu-id="876d7-140">消息存储提供程序支持对象的实现**IMAPISupport::CopyMessages**方法。</span><span class="sxs-lookup"><span data-stu-id="876d7-140">The **IMAPISupport::CopyMessages** method is implemented for message store provider support objects.</span></span> <span data-ttu-id="876d7-141">消息存储提供程序可以[IMAPIFolder::CopyMessages](imapifolder-copymessages.md)复制或移动到另一个文件夹中一个或多个邮件其实现中调用**IMAPISupport::CopyMessages** 。</span><span class="sxs-lookup"><span data-stu-id="876d7-141">Message store providers can call **IMAPISupport::CopyMessages** in their implementation of [IMAPIFolder::CopyMessages](imapifolder-copymessages.md) to copy or move one or more messages from one folder to another.</span></span> <span data-ttu-id="876d7-142">作为**IMAPISupport::CopyMessages**呼叫的一部分，消息存储提供程序可以指定 MAPI 应显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="876d7-142">As part of the **IMAPISupport::CopyMessages** call, the message store provider can specify that MAPI should display a progress indicator.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="876d7-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="876d7-143">See also</span></span>



[<span data-ttu-id="876d7-144">IMAPIFolder::CopyMessages</span><span class="sxs-lookup"><span data-stu-id="876d7-144">IMAPIFolder::CopyMessages</span></span>](imapifolder-copymessages.md)
  
[<span data-ttu-id="876d7-145">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="876d7-145">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

