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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 9cc4e3ba77395e09a6b95e8381fa402fc3cdff61
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405154"
---
# <a name="imapisupportcopymessages"></a><span data-ttu-id="ee804-103">IMAPISupport::CopyMessages</span><span class="sxs-lookup"><span data-stu-id="ee804-103">IMAPISupport::CopyMessages</span></span>

  
  
<span data-ttu-id="ee804-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ee804-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ee804-105">将邮件从一个文件夹复制或移动到另一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="ee804-105">Copies or moves messages from one folder to another folder.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="ee804-106">参数</span><span class="sxs-lookup"><span data-stu-id="ee804-106">Parameters</span></span>

 <span data-ttu-id="ee804-107">_lpSrcInterface_</span><span class="sxs-lookup"><span data-stu-id="ee804-107">_lpSrcInterface_</span></span>
  
> <span data-ttu-id="ee804-108">实时指向接口标识符 (IID) 的指针, 该接口标识符表示用于访问包含要复制或移动的邮件的文件夹的接口。</span><span class="sxs-lookup"><span data-stu-id="ee804-108">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the folder that contains the messages to be copied or moved.</span></span>
    
 <span data-ttu-id="ee804-109">_lpSrcFolder_</span><span class="sxs-lookup"><span data-stu-id="ee804-109">_lpSrcFolder_</span></span>
  
> <span data-ttu-id="ee804-110">实时指向包含要复制或移动的邮件的文件夹的指针。</span><span class="sxs-lookup"><span data-stu-id="ee804-110">[in] A pointer to the folder that contains the messages to be copied or moved.</span></span>
    
 <span data-ttu-id="ee804-111">_lpMsgList_</span><span class="sxs-lookup"><span data-stu-id="ee804-111">_lpMsgList_</span></span>
  
> <span data-ttu-id="ee804-112">实时指向条目标识符数组的指针, 这些标识符标识要复制或移动的邮件。</span><span class="sxs-lookup"><span data-stu-id="ee804-112">[in] A pointer to an array of entry identifiers that identify the messages to be copied or moved.</span></span> 
    
 <span data-ttu-id="ee804-113">_lpDestInterface_</span><span class="sxs-lookup"><span data-stu-id="ee804-113">_lpDestInterface_</span></span>
  
> <span data-ttu-id="ee804-114">实时指向接口标识符 (IID) 的指针, 该接口标识符代表要用于访问已复制或移动的邮件的目标文件夹的接口。</span><span class="sxs-lookup"><span data-stu-id="ee804-114">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the destination folder for the copied or moved messages.</span></span>
    
 <span data-ttu-id="ee804-115">_lpDestFolder_</span><span class="sxs-lookup"><span data-stu-id="ee804-115">_lpDestFolder_</span></span>
  
> <span data-ttu-id="ee804-116">实时指向已复制或移动邮件的目标文件夹的指针。</span><span class="sxs-lookup"><span data-stu-id="ee804-116">[in] A pointer to the destination folder for the copied or moved messages.</span></span> <span data-ttu-id="ee804-117">此文件夹必须处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="ee804-117">This folder must be open.</span></span>
    
 <span data-ttu-id="ee804-118">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="ee804-118">_ulUIParam_</span></span>
  
> <span data-ttu-id="ee804-119">实时指向显示进度指示器的进度对象的指针。</span><span class="sxs-lookup"><span data-stu-id="ee804-119">[in] A pointer to a progress object that displays a progress indicator.</span></span> <span data-ttu-id="ee804-120">如果在_lpProgress_中传递 NULL, 则邮件存储提供程序将使用 MAPI 进度对象实现来显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="ee804-120">If NULL is passed in  _lpProgress_, the message store provider displays a progress indicator by using the MAPI progress object implementation.</span></span> <span data-ttu-id="ee804-121">除非在_ulFlags_中设置了 MESSAGE_DIALOG 标志, 否则_lpProgress_参数将被忽略。</span><span class="sxs-lookup"><span data-stu-id="ee804-121">The  _lpProgress_ parameter is ignored unless the MESSAGE_DIALOG flag is set in  _ulFlags_.</span></span>
    
 <span data-ttu-id="ee804-122">_lpProgress_</span><span class="sxs-lookup"><span data-stu-id="ee804-122">_lpProgress_</span></span>
  
> <span data-ttu-id="ee804-123">实时指向显示进度指示器的进度对象的指针。</span><span class="sxs-lookup"><span data-stu-id="ee804-123">[in] A pointer to a progress object that displays a progress indicator.</span></span> <span data-ttu-id="ee804-124">如果在_lpProgress_中传递 NULL, 则邮件存储提供程序将使用 MAPI 进度对象实现来显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="ee804-124">If NULL is passed in  _lpProgress_, the message store provider displays a progress indicator by using the MAPI progress object implementation.</span></span> <span data-ttu-id="ee804-125">除非在_ulFlags_中设置了 MESSAGE_DIALOG 标志, 否则_lpProgress_参数将被忽略。</span><span class="sxs-lookup"><span data-stu-id="ee804-125">The  _lpProgress_ parameter is ignored unless the MESSAGE_DIALOG flag is set in  _ulFlags_.</span></span>
    
 <span data-ttu-id="ee804-126">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="ee804-126">_ulFlags_</span></span>
  
> <span data-ttu-id="ee804-127">实时用于控制如何完成复制或移动操作的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="ee804-127">[in] A bitmask of flags that controls how the copy or move operation is accomplished.</span></span> <span data-ttu-id="ee804-128">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="ee804-128">The following flags can be set:</span></span>
    
<span data-ttu-id="ee804-129">MESSAGE_DIALOG</span><span class="sxs-lookup"><span data-stu-id="ee804-129">MESSAGE_DIALOG</span></span> 
  
> <span data-ttu-id="ee804-130">请求显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="ee804-130">Requests the display of a progress indicator.</span></span>
    
<span data-ttu-id="ee804-131">MESSAGE_MOVE</span><span class="sxs-lookup"><span data-stu-id="ee804-131">MESSAGE_MOVE</span></span> 
  
> <span data-ttu-id="ee804-132">应移动邮件, 而不是复制。</span><span class="sxs-lookup"><span data-stu-id="ee804-132">The messages should be moved, instead of copied.</span></span> <span data-ttu-id="ee804-133">如果未设置 MESSAGE_MOVE, 则会复制邮件。</span><span class="sxs-lookup"><span data-stu-id="ee804-133">If MESSAGE_MOVE is not set, the messages are copied.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="ee804-134">返回值</span><span class="sxs-lookup"><span data-stu-id="ee804-134">Return value</span></span>

<span data-ttu-id="ee804-135">S_OK</span><span class="sxs-lookup"><span data-stu-id="ee804-135">S_OK</span></span> 
  
> <span data-ttu-id="ee804-136">复制或移动操作成功完成。</span><span class="sxs-lookup"><span data-stu-id="ee804-136">The copy or move operation was successful.</span></span>
    
<span data-ttu-id="ee804-137">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="ee804-137">MAPI_E_USER_CANCEL</span></span> 
  
> <span data-ttu-id="ee804-138">用户取消了操作, 通常是单击对话框中的 "**取消**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="ee804-138">The user canceled the operation, typically by clicking the **Cancel** button in a dialog box.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="ee804-139">说明</span><span class="sxs-lookup"><span data-stu-id="ee804-139">Remarks</span></span>

<span data-ttu-id="ee804-140">为邮件存储提供程序支持对象实现了**IMAPISupport:: CopyMessages**方法。</span><span class="sxs-lookup"><span data-stu-id="ee804-140">The **IMAPISupport::CopyMessages** method is implemented for message store provider support objects.</span></span> <span data-ttu-id="ee804-141">邮件存储提供程序可以在其[IMAPIFolder:: CopyMessages](imapifolder-copymessages.md)的实现中调用**IMAPISupport:: CopyMessages** , 将一个或多个邮件从一个文件夹复制或移动到另一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="ee804-141">Message store providers can call **IMAPISupport::CopyMessages** in their implementation of [IMAPIFolder::CopyMessages](imapifolder-copymessages.md) to copy or move one or more messages from one folder to another.</span></span> <span data-ttu-id="ee804-142">作为**IMAPISupport:: CopyMessages**调用的一部分, 邮件存储提供程序可以指定 MAPI 应显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="ee804-142">As part of the **IMAPISupport::CopyMessages** call, the message store provider can specify that MAPI should display a progress indicator.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ee804-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ee804-143">See also</span></span>



[<span data-ttu-id="ee804-144">IMAPIFolder::CopyMessages</span><span class="sxs-lookup"><span data-stu-id="ee804-144">IMAPIFolder::CopyMessages</span></span>](imapifolder-copymessages.md)
  
[<span data-ttu-id="ee804-145">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="ee804-145">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

