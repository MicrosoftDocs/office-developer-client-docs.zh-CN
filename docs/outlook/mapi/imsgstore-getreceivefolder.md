---
title: IMsgStoreGetReceiveFolder
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgStore.GetReceiveFolder
api_type:
- COM
ms.assetid: ccd9d623-a3cb-4e66-9649-78c3887cb726
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f58bd8499b63bcd526906f78143b76092f194cb4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775865"
---
# <a name="imsgstoregetreceivefolder"></a><span data-ttu-id="fda53-103">IMsgStore::GetReceiveFolder</span><span class="sxs-lookup"><span data-stu-id="fda53-103">IMsgStore::GetReceiveFolder</span></span>

  
  
<span data-ttu-id="fda53-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="fda53-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="fda53-105">获取时，传入邮件指定的邮件类的或为默认的目标接收的消息存储库文件夹建立的文件夹。</span><span class="sxs-lookup"><span data-stu-id="fda53-105">Obtains the folder that was established as the destination for incoming messages of a specified message class or as the default receive folder for the message store.</span></span>
  
```cpp
HRESULT GetReceiveFolder(
  LPSTR lpszMessageClass,
  ULONG ulFlags,
  ULONG FAR * lpcbEntryID,
  LPENTRYID FAR * lppEntryID,
  LPSTR FAR * lppszExplicitClass
);
```

## <a name="parameters"></a><span data-ttu-id="fda53-106">参数</span><span class="sxs-lookup"><span data-stu-id="fda53-106">Parameters</span></span>

 <span data-ttu-id="fda53-107">_lpszMessageClass_</span><span class="sxs-lookup"><span data-stu-id="fda53-107">_lpszMessageClass_</span></span>
  
> <span data-ttu-id="fda53-108">[in]指向相关联的接收文件夹的邮件类的指针。</span><span class="sxs-lookup"><span data-stu-id="fda53-108">[in] A pointer to a message class that is associated with a receive folder.</span></span> <span data-ttu-id="fda53-109">如果_lpszMessageClass_参数设置为 NULL 或空字符串， **GetReceiveFolder**返回默认接收消息存储库的文件夹。</span><span class="sxs-lookup"><span data-stu-id="fda53-109">If the  _lpszMessageClass_ parameter is set to NULL or an empty string, **GetReceiveFolder** returns the default receive folder for the message store.</span></span> 
    
 <span data-ttu-id="fda53-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="fda53-110">_ulFlags_</span></span>
  
> <span data-ttu-id="fda53-111">[in]位掩码的标志的控制的传入的和返回字符串的类型。</span><span class="sxs-lookup"><span data-stu-id="fda53-111">[in] A bitmask of flags that controls the type of the passed-in and returned strings.</span></span> <span data-ttu-id="fda53-112">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="fda53-112">The following flag can be set:</span></span>
    
<span data-ttu-id="fda53-113">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="fda53-113">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="fda53-114">邮件类字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="fda53-114">The message class string is in Unicode format.</span></span> <span data-ttu-id="fda53-115">如果未设置 MAPI_UNICODE 标志，消息类字符串是 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="fda53-115">If the MAPI_UNICODE flag is not set, the message class string is in ANSI format.</span></span>
    
 <span data-ttu-id="fda53-116">_lpcbEntryID_</span><span class="sxs-lookup"><span data-stu-id="fda53-116">_lpcbEntryID_</span></span>
  
> <span data-ttu-id="fda53-117">[输出]一个指向_lppEntryID_参数指向该条目标识符中的字节数。</span><span class="sxs-lookup"><span data-stu-id="fda53-117">[out] A pointer to the byte count in the entry identifier pointed to by the  _lppEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="fda53-118">_lppEntryID_</span><span class="sxs-lookup"><span data-stu-id="fda53-118">_lppEntryID_</span></span>
  
> <span data-ttu-id="fda53-119">[输出]为请求的项标识符指针的指针接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="fda53-119">[out] A pointer to a pointer to the entry identifier for the requested receive folder.</span></span>
    
 <span data-ttu-id="fda53-120">_lppszExplicitClass_</span><span class="sxs-lookup"><span data-stu-id="fda53-120">_lppszExplicitClass_</span></span>
  
> <span data-ttu-id="fda53-121">[输出]指向作为显式设置的邮件类的指针的指针其接收由_lppEntryID_文件夹指向的文件夹。</span><span class="sxs-lookup"><span data-stu-id="fda53-121">[out] A pointer to a pointer to the message class that explicitly sets as its receive folder the folder pointed to by  _lppEntryID_.</span></span> <span data-ttu-id="fda53-122">此邮件类也应在_lpszMessageClass_参数中的类或该类的基类相同。</span><span class="sxs-lookup"><span data-stu-id="fda53-122">This message class should either be the same as the class in the  _lpszMessageClass_ parameter, or a base class of that class.</span></span> <span data-ttu-id="fda53-123">传递 NULL 指示由_lppEntryID_指向的文件夹是默认接收的消息存储库文件夹。</span><span class="sxs-lookup"><span data-stu-id="fda53-123">Passing NULL indicates that the folder pointed to by  _lppEntryID_ is the default receive folder for the message store.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="fda53-124">返回值</span><span class="sxs-lookup"><span data-stu-id="fda53-124">Return value</span></span>

<span data-ttu-id="fda53-125">S_OK</span><span class="sxs-lookup"><span data-stu-id="fda53-125">S_OK</span></span> 
  
> <span data-ttu-id="fda53-126">已成功返回的接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="fda53-126">The receive folder was successfully returned.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="fda53-127">说明</span><span class="sxs-lookup"><span data-stu-id="fda53-127">Remarks</span></span>

<span data-ttu-id="fda53-128">**IMsgStore::GetReceiveFolder**方法获取接收文件夹中，指定要接收传入邮件的特定邮件类别的文件夹的项标识符。</span><span class="sxs-lookup"><span data-stu-id="fda53-128">The **IMsgStore::GetReceiveFolder** method obtains the entry identifier of a receive folder, a folder designated to receive incoming messages of a particular message class.</span></span> <span data-ttu-id="fda53-129">呼叫者可以_lpszMessageClass_参数中指定的邮件类或 NULL。</span><span class="sxs-lookup"><span data-stu-id="fda53-129">Callers can specify a message class or NULL in the  _lpszMessageClass_ parameter.</span></span> <span data-ttu-id="fda53-130">如果_lpszMessageClass_为 NULL，则**GetReceiveFolder**将返回以下值：</span><span class="sxs-lookup"><span data-stu-id="fda53-130">If  _lpszMessageClass_ is NULL, **GetReceiveFolder** returns the following values:</span></span> 
  
- <span data-ttu-id="fda53-131">_LppszExplicitClass_中的第一个基类的邮件类的名称指向_lpszMessageClass_显式设置的接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="fda53-131">In  _lppszExplicitClass_, the name of the first base class of the message class pointed to by  _lpszMessageClass_ that does explicitly set a receive folder.</span></span> 
    
- <span data-ttu-id="fda53-132">_LppEntryID_中的项标识符的接收文件夹的基类指向_lppszExplicitClass_参数。</span><span class="sxs-lookup"><span data-stu-id="fda53-132">In  _lppEntryID_, the entry identifier of the receive folder for the base class pointed to by the  _lppszExplicitClass_ parameter.</span></span> 
    
<span data-ttu-id="fda53-133">例如，假设邮件类**IPM 的接收文件夹。注意**已设置的项标识符的收件箱和**GetReceiveFolder**称为_lpszMessageClass_设置为**IPM 的内容。Note.Phone**。</span><span class="sxs-lookup"><span data-stu-id="fda53-133">For example, suppose the receive folder of the message class **IPM.Note** has been set to the entry identifier of the Inbox and **GetReceiveFolder** is called with the contents of  _lpszMessageClass_ set to **IPM.Note.Phone**.</span></span> <span data-ttu-id="fda53-134">如果**IPM。Note.Phone**不具有显式接收文件夹集， **GetReceiveFolder** _lppEntryID_和**IPM 中返回的项标识符的收件箱。注意** _lppszExplicitClass_中。</span><span class="sxs-lookup"><span data-stu-id="fda53-134">If **IPM.Note.Phone** does not have an explicit receive folder set, **GetReceiveFolder** returns the entry identifier of the Inbox in  _lppEntryID_ and **IPM.Note** in  _lppszExplicitClass_.</span></span>
  
<span data-ttu-id="fda53-135">如果客户端调用**GetReceiveFolder**为邮件类，并且未设置用于该邮件类的接收文件夹， _lppszExplicitClass_是零长度字符串、 Unicode 格式的字符串或具体取决于 ANSI 格式的字符串客户端_ulFlags_参数中设置 MAPI_UNICODE 标志。</span><span class="sxs-lookup"><span data-stu-id="fda53-135">If the client calls **GetReceiveFolder** for a message class and has not set a receive folder for that message class,  _lppszExplicitClass_ is either a zero-length string, a string in Unicode format, or a string in ANSI format depending on whether the client set the MAPI_UNICODE flag in the  _ulFlags_ parameter.</span></span> 
  
<span data-ttu-id="fda53-136">默认的接收文件夹，获取_lpszMessageClass_参数中传递 NULL，每个邮件存储始终存在。</span><span class="sxs-lookup"><span data-stu-id="fda53-136">A default receive folder, obtained by passing NULL in the  _lpszMessageClass_ parameter, always exists for every message store.</span></span> 
  
<span data-ttu-id="fda53-137">客户端应调用[MAPIFreeBuffer](mapifreebuffer.md)函数完成_lppEntryID_以释放内存，保存该条目标识符中返回的项标识符。</span><span class="sxs-lookup"><span data-stu-id="fda53-137">A client should call the [MAPIFreeBuffer](mapifreebuffer.md) function when it is done with the entry identifier returned in  _lppEntryID_ to free the memory that holds that entry identifier.</span></span> <span data-ttu-id="fda53-138">完成使用_lppszExplicitClass_以释放内存包含该字符串中返回的消息类字符串，它还应调用**MAPIFreeBuffer** 。</span><span class="sxs-lookup"><span data-stu-id="fda53-138">It should also call **MAPIFreeBuffer** when it is done with the message class string returned in  _lppszExplicitClass_ to free the memory that holds that string.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="fda53-139">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="fda53-139">MFCMAPI reference</span></span>

<span data-ttu-id="fda53-140">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="fda53-140">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="fda53-141">**文件**</span><span class="sxs-lookup"><span data-stu-id="fda53-141">**File**</span></span>|<span data-ttu-id="fda53-142">**函数**</span><span class="sxs-lookup"><span data-stu-id="fda53-142">**Function**</span></span>|<span data-ttu-id="fda53-143">**Comment**</span><span class="sxs-lookup"><span data-stu-id="fda53-143">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fda53-144">MAPIFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="fda53-144">MAPIFunctions.cpp</span></span>  <br/> |<span data-ttu-id="fda53-145">GetInbox</span><span class="sxs-lookup"><span data-stu-id="fda53-145">GetInbox</span></span>  <br/> |<span data-ttu-id="fda53-146">MFCMAPI 使用**IMsgStore::GetReceiveFolder**方法找到收件箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="fda53-146">MFCMAPI uses the **IMsgStore::GetReceiveFolder** method to locate the Inbox folder.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="fda53-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fda53-147">See also</span></span>



[<span data-ttu-id="fda53-148">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="fda53-148">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="fda53-149">IMsgStore : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="fda53-149">IMsgStore : IMAPIProp</span></span>](imsgstoreimapiprop.md)


[<span data-ttu-id="fda53-150">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="fda53-150">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

