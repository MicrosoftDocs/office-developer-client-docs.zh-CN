---
title: IMsgStoreSetReceiveFolder
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgStore.SetReceiveFolder
api_type:
- COM
ms.assetid: 469f0412-1343-47ce-b6e8-e0d5e56c29bb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4e2d4f76fe436fd18b439bbbb558b1169094b438
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589460"
---
# <a name="imsgstoresetreceivefolder"></a><span data-ttu-id="38772-103">IMsgStore::SetReceiveFolder</span><span class="sxs-lookup"><span data-stu-id="38772-103">IMsgStore::SetReceiveFolder</span></span>

  
  
<span data-ttu-id="38772-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="38772-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="38772-105">为特定邮件类别的传入消息的目标建立一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="38772-105">Establishes a folder as the destination for incoming messages of a particular message class.</span></span>
  
```cpp
HRESULT SetReceiveFolder(
  LPSTR lpszMessageClass,
  ULONG ulFlags,
  ULONG cbEntryID,
  LPENTRYID lpEntryID
);
```

## <a name="parameters"></a><span data-ttu-id="38772-106">参数</span><span class="sxs-lookup"><span data-stu-id="38772-106">Parameters</span></span>

 <span data-ttu-id="38772-107">_lpszMessageClass_</span><span class="sxs-lookup"><span data-stu-id="38772-107">_lpszMessageClass_</span></span>
  
> <span data-ttu-id="38772-108">[in]指向要与新关联的邮件类的接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="38772-108">[in] A pointer to the message class that is to be associated with the new receive folder.</span></span> <span data-ttu-id="38772-109">如果_lpszMessageClass_参数设置为 NULL 或空字符串， **SetReceiveFolder**设置默认接收消息存储库的文件夹。</span><span class="sxs-lookup"><span data-stu-id="38772-109">If the  _lpszMessageClass_ parameter is set to NULL or an empty string, **SetReceiveFolder** sets the default receive folder for the message store.</span></span> 
    
 <span data-ttu-id="38772-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="38772-110">_ulFlags_</span></span>
  
> <span data-ttu-id="38772-111">[in]位掩码的标志的控制传入的字符串中的文本的类型。</span><span class="sxs-lookup"><span data-stu-id="38772-111">[in] A bitmask of flags that controls the type of the text in the passed-in strings.</span></span> <span data-ttu-id="38772-112">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="38772-112">The following flag can be set:</span></span>
    
<span data-ttu-id="38772-113">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="38772-113">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="38772-114">邮件类字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="38772-114">The message class string is in Unicode format.</span></span> <span data-ttu-id="38772-115">如果未设置 MAPI_UNICODE 标志，消息类字符串是 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="38772-115">If the MAPI_UNICODE flag is not set, the message class string is in ANSI format.</span></span>
    
 <span data-ttu-id="38772-116">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="38772-116">_cbEntryID_</span></span>
  
> <span data-ttu-id="38772-117">[in]在_lpEntryID_参数指向的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="38772-117">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="38772-118">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="38772-118">_lpEntryID_</span></span>
  
> <span data-ttu-id="38772-119">[in]指向要建立作为接收文件夹的文件夹的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="38772-119">[in] A pointer to the entry identifier of the folder to establish as the receive folder.</span></span> <span data-ttu-id="38772-120">如果_lpEntryID_参数设置为 NULL， **SetReceiveFolder**替换当前收到消息存储库的默认文件夹。</span><span class="sxs-lookup"><span data-stu-id="38772-120">If the  _lpEntryID_ parameter is set to NULL, **SetReceiveFolder** replaces the current receive folder with the message store's default.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="38772-121">返回值</span><span class="sxs-lookup"><span data-stu-id="38772-121">Return value</span></span>

<span data-ttu-id="38772-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="38772-122">S_OK</span></span> 
  
> <span data-ttu-id="38772-123">已成功建立的接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="38772-123">A receive folder was successfully established.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="38772-124">注解</span><span class="sxs-lookup"><span data-stu-id="38772-124">Remarks</span></span>

<span data-ttu-id="38772-125">**IMsgStore::SetReceiveFolder**方法设置或更改为特定邮件类的接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="38772-125">The **IMsgStore::SetReceiveFolder** method sets or changes the receive folder for a particular message class.</span></span> <span data-ttu-id="38772-126">与**SetReceiveFolder**，客户端可以使用连续呼叫指定不同接收每个定义的邮件类的文件夹或指定为所有的多个邮件类的传入消息转到同一文件夹中。</span><span class="sxs-lookup"><span data-stu-id="38772-126">With **SetReceiveFolder**, a client can, by using successive calls, specify a different receive folder for each defined message class or specify that incoming messages for multiple message classes all go to the same folder.</span></span> <span data-ttu-id="38772-127">例如，客户端可以有其自己的消息的类到达其自己的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="38772-127">For example, a client can have its own class of messages arrive in its own folder.</span></span> <span data-ttu-id="38772-128">传真应用程序可以指定一个文件夹存储提供程序将在其中放传入传真和提供程序将在其中放传出传真的另一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="38772-128">A fax application can designate one folder in which the store provider puts incoming faxes and another folder in which the provider puts outgoing faxes.</span></span>
  
<span data-ttu-id="38772-129">如果**SetReceiveFolder**到在呼叫期间发生错误，接收文件夹设置保持不变。</span><span class="sxs-lookup"><span data-stu-id="38772-129">If an error occurs during the call to **SetReceiveFolder**, the receive folder setting remains unchanged.</span></span> 
  
<span data-ttu-id="38772-130">如果**SetReceiveFolder**更改与_lpEntryID_的接收文件夹设置设置为 NULL，表明应设置默认的接收文件夹、 **SetReceiveFolder**即使出现指示没有现有设置，则返回 S_OK邮件类。</span><span class="sxs-lookup"><span data-stu-id="38772-130">If **SetReceiveFolder** changes the receive folder setting with  _lpEntryID_ set to NULL, indicating that the default receive folder should be set, **SetReceiveFolder** returns S_OK even if there was no existing setting for the indicated message class.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="38772-131">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="38772-131">MFCMAPI reference</span></span>

<span data-ttu-id="38772-132">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="38772-132">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="38772-133">**文件**</span><span class="sxs-lookup"><span data-stu-id="38772-133">**File**</span></span>|<span data-ttu-id="38772-134">**函数**</span><span class="sxs-lookup"><span data-stu-id="38772-134">**Function**</span></span>|<span data-ttu-id="38772-135">**Comment**</span><span class="sxs-lookup"><span data-stu-id="38772-135">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="38772-136">MsgStoreDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="38772-136">MsgStoreDlg.cpp</span></span>  <br/> |<span data-ttu-id="38772-137">CMsgStoreDlg::OnSetReceiveFolder</span><span class="sxs-lookup"><span data-stu-id="38772-137">CMsgStoreDlg::OnSetReceiveFolder</span></span>  <br/> |<span data-ttu-id="38772-138">MFCMAPI 使用**IMsgStore::SetReceiveFolder**方法将文件夹设置为一个特定的邮件类的接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="38772-138">MFCMAPI uses the **IMsgStore::SetReceiveFolder** method to set a folder as the receive folder for a particular message class.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="38772-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="38772-139">See also</span></span>



[<span data-ttu-id="38772-140">IMsgStore : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="38772-140">IMsgStore : IMAPIProp</span></span>](imsgstoreimapiprop.md)


[<span data-ttu-id="38772-141">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="38772-141">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

