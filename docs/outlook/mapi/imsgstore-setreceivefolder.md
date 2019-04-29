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
ms.openlocfilehash: efa5d60098fd5f16328669249a8445a124d9878b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434086"
---
# <a name="imsgstoresetreceivefolder"></a><span data-ttu-id="a0e1e-103">IMsgStore::SetReceiveFolder</span><span class="sxs-lookup"><span data-stu-id="a0e1e-103">IMsgStore::SetReceiveFolder</span></span>

  
  
<span data-ttu-id="a0e1e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a0e1e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a0e1e-105">建立一个文件夹作为特定邮件类别的传入邮件的目标。</span><span class="sxs-lookup"><span data-stu-id="a0e1e-105">Establishes a folder as the destination for incoming messages of a particular message class.</span></span>
  
```cpp
HRESULT SetReceiveFolder(
  LPSTR lpszMessageClass,
  ULONG ulFlags,
  ULONG cbEntryID,
  LPENTRYID lpEntryID
);
```

## <a name="parameters"></a><span data-ttu-id="a0e1e-106">参数</span><span class="sxs-lookup"><span data-stu-id="a0e1e-106">Parameters</span></span>

 <span data-ttu-id="a0e1e-107">_lpszMessageClass_</span><span class="sxs-lookup"><span data-stu-id="a0e1e-107">_lpszMessageClass_</span></span>
  
> <span data-ttu-id="a0e1e-108">实时指向要与新的接收文件夹相关联的邮件类的指针。</span><span class="sxs-lookup"><span data-stu-id="a0e1e-108">[in] A pointer to the message class that is to be associated with the new receive folder.</span></span> <span data-ttu-id="a0e1e-109">如果将_lpszMessageClass_参数设置为 NULL 或空字符串, 则**SetReceiveFolder**将为邮件存储区设置默认接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="a0e1e-109">If the  _lpszMessageClass_ parameter is set to NULL or an empty string, **SetReceiveFolder** sets the default receive folder for the message store.</span></span> 
    
 <span data-ttu-id="a0e1e-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="a0e1e-110">_ulFlags_</span></span>
  
> <span data-ttu-id="a0e1e-111">实时用于控制传入字符串中的文本类型的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="a0e1e-111">[in] A bitmask of flags that controls the type of the text in the passed-in strings.</span></span> <span data-ttu-id="a0e1e-112">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="a0e1e-112">The following flag can be set:</span></span>
    
<span data-ttu-id="a0e1e-113">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="a0e1e-113">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="a0e1e-114">邮件类字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="a0e1e-114">The message class string is in Unicode format.</span></span> <span data-ttu-id="a0e1e-115">如果未设置 MAPI_UNICODE 标志, 则邮件类字符串将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="a0e1e-115">If the MAPI_UNICODE flag is not set, the message class string is in ANSI format.</span></span>
    
 <span data-ttu-id="a0e1e-116">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="a0e1e-116">_cbEntryID_</span></span>
  
> <span data-ttu-id="a0e1e-117">实时条目标识符中由_lpEntryID_参数指向的字节数。</span><span class="sxs-lookup"><span data-stu-id="a0e1e-117">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="a0e1e-118">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="a0e1e-118">_lpEntryID_</span></span>
  
> <span data-ttu-id="a0e1e-119">实时指向要作为接收文件夹建立的文件夹的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="a0e1e-119">[in] A pointer to the entry identifier of the folder to establish as the receive folder.</span></span> <span data-ttu-id="a0e1e-120">如果将_lpEntryID_参数设置为 NULL, **SetReceiveFolder**将使用邮件存储区的默认值替换当前的接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="a0e1e-120">If the  _lpEntryID_ parameter is set to NULL, **SetReceiveFolder** replaces the current receive folder with the message store's default.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="a0e1e-121">返回值</span><span class="sxs-lookup"><span data-stu-id="a0e1e-121">Return value</span></span>

<span data-ttu-id="a0e1e-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="a0e1e-122">S_OK</span></span> 
  
> <span data-ttu-id="a0e1e-123">已成功建立接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="a0e1e-123">A receive folder was successfully established.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="a0e1e-124">说明</span><span class="sxs-lookup"><span data-stu-id="a0e1e-124">Remarks</span></span>

<span data-ttu-id="a0e1e-125">**IMsgStore:: SetReceiveFolder**方法设置或更改特定邮件类别的接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="a0e1e-125">The **IMsgStore::SetReceiveFolder** method sets or changes the receive folder for a particular message class.</span></span> <span data-ttu-id="a0e1e-126">使用**SetReceiveFolder**, 客户端可以通过使用连续调用为每个定义的邮件类别指定不同的接收文件夹, 或指定所有邮件类别的传入邮件都将转到同一文件夹。</span><span class="sxs-lookup"><span data-stu-id="a0e1e-126">With **SetReceiveFolder**, a client can, by using successive calls, specify a different receive folder for each defined message class or specify that incoming messages for multiple message classes all go to the same folder.</span></span> <span data-ttu-id="a0e1e-127">例如, 客户端可以让其自己的邮件类到达自己的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="a0e1e-127">For example, a client can have its own class of messages arrive in its own folder.</span></span> <span data-ttu-id="a0e1e-128">传真应用程序可以指定一个文件夹, 其中存储提供程序将传入传真和另一个文件夹放置在其中, 提供程序将传出传真放在其中。</span><span class="sxs-lookup"><span data-stu-id="a0e1e-128">A fax application can designate one folder in which the store provider puts incoming faxes and another folder in which the provider puts outgoing faxes.</span></span>
  
<span data-ttu-id="a0e1e-129">如果在调用**SetReceiveFolder**期间发生错误, 则接收文件夹设置将保持不变。</span><span class="sxs-lookup"><span data-stu-id="a0e1e-129">If an error occurs during the call to **SetReceiveFolder**, the receive folder setting remains unchanged.</span></span> 
  
<span data-ttu-id="a0e1e-130">如果**SetReceiveFolder**将接收文件夹设置更改为 "lpEntryID", 并将 " __ " 设置为 NULL, 则表示应设置默认接收文件夹, 即使没有指定的现有设置, **SetReceiveFolder**也会返回 S_OK。邮件类别。</span><span class="sxs-lookup"><span data-stu-id="a0e1e-130">If **SetReceiveFolder** changes the receive folder setting with  _lpEntryID_ set to NULL, indicating that the default receive folder should be set, **SetReceiveFolder** returns S_OK even if there was no existing setting for the indicated message class.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="a0e1e-131">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="a0e1e-131">MFCMAPI reference</span></span>

<span data-ttu-id="a0e1e-132">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="a0e1e-132">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="a0e1e-133">**文件**</span><span class="sxs-lookup"><span data-stu-id="a0e1e-133">**File**</span></span>|<span data-ttu-id="a0e1e-134">**函数**</span><span class="sxs-lookup"><span data-stu-id="a0e1e-134">**Function**</span></span>|<span data-ttu-id="a0e1e-135">**备注**</span><span class="sxs-lookup"><span data-stu-id="a0e1e-135">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a0e1e-136">MsgStoreDlg</span><span class="sxs-lookup"><span data-stu-id="a0e1e-136">MsgStoreDlg.cpp</span></span>  <br/> |<span data-ttu-id="a0e1e-137">CMsgStoreDlg:: OnSetReceiveFolder</span><span class="sxs-lookup"><span data-stu-id="a0e1e-137">CMsgStoreDlg::OnSetReceiveFolder</span></span>  <br/> |<span data-ttu-id="a0e1e-138">MFCMAPI 使用**IMsgStore:: SetReceiveFolder**方法将文件夹设置为特定邮件类别的接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="a0e1e-138">MFCMAPI uses the **IMsgStore::SetReceiveFolder** method to set a folder as the receive folder for a particular message class.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="a0e1e-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a0e1e-139">See also</span></span>



[<span data-ttu-id="a0e1e-140">IMsgStore : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="a0e1e-140">IMsgStore : IMAPIProp</span></span>](imsgstoreimapiprop.md)


[<span data-ttu-id="a0e1e-141">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="a0e1e-141">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

