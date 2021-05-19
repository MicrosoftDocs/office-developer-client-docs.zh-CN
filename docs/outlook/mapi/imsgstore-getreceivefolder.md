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
ms.openlocfilehash: ab21dcfb9011b675e3db4e4df29cb6ecafa6e7c6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435346"
---
# <a name="imsgstoregetreceivefolder"></a><span data-ttu-id="66758-103">IMsgStore::GetReceiveFolder</span><span class="sxs-lookup"><span data-stu-id="66758-103">IMsgStore::GetReceiveFolder</span></span>

  
  
<span data-ttu-id="66758-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="66758-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="66758-105">获取已建立为指定邮件类的传入邮件的目标或作为邮件存储的默认接收文件夹的文件夹。</span><span class="sxs-lookup"><span data-stu-id="66758-105">Obtains the folder that was established as the destination for incoming messages of a specified message class or as the default receive folder for the message store.</span></span>
  
```cpp
HRESULT GetReceiveFolder(
  LPSTR lpszMessageClass,
  ULONG ulFlags,
  ULONG FAR * lpcbEntryID,
  LPENTRYID FAR * lppEntryID,
  LPSTR FAR * lppszExplicitClass
);
```

## <a name="parameters"></a><span data-ttu-id="66758-106">参数</span><span class="sxs-lookup"><span data-stu-id="66758-106">Parameters</span></span>

 <span data-ttu-id="66758-107">_lpszMessageClass_</span><span class="sxs-lookup"><span data-stu-id="66758-107">_lpszMessageClass_</span></span>
  
> <span data-ttu-id="66758-108">[in]指向与接收文件夹关联的邮件类的指针。</span><span class="sxs-lookup"><span data-stu-id="66758-108">[in] A pointer to a message class that is associated with a receive folder.</span></span> <span data-ttu-id="66758-109">如果  _lpszMessageClass_ 参数设置为 NULL 或空字符串 **，GetReceiveFolder** 将返回邮件存储的默认接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="66758-109">If the  _lpszMessageClass_ parameter is set to NULL or an empty string, **GetReceiveFolder** returns the default receive folder for the message store.</span></span> 
    
 <span data-ttu-id="66758-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="66758-110">_ulFlags_</span></span>
  
> <span data-ttu-id="66758-111">[in]控制传入和返回的字符串类型的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="66758-111">[in] A bitmask of flags that controls the type of the passed-in and returned strings.</span></span> <span data-ttu-id="66758-112">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="66758-112">The following flag can be set:</span></span>
    
<span data-ttu-id="66758-113">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="66758-113">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="66758-114">邮件类字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="66758-114">The message class string is in Unicode format.</span></span> <span data-ttu-id="66758-115">如果未MAPI_UNICODE，则邮件类字符串采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="66758-115">If the MAPI_UNICODE flag is not set, the message class string is in ANSI format.</span></span>
    
 <span data-ttu-id="66758-116">_lpcbEntryID_</span><span class="sxs-lookup"><span data-stu-id="66758-116">_lpcbEntryID_</span></span>
  
> <span data-ttu-id="66758-117">[out]指向  _lppEntryID_ 参数指向的条目标识符中的字节计数的指针。</span><span class="sxs-lookup"><span data-stu-id="66758-117">[out] A pointer to the byte count in the entry identifier pointed to by the  _lppEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="66758-118">_lppEntryID_</span><span class="sxs-lookup"><span data-stu-id="66758-118">_lppEntryID_</span></span>
  
> <span data-ttu-id="66758-119">[out]指向指向所请求接收文件夹的条目标识符的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="66758-119">[out] A pointer to a pointer to the entry identifier for the requested receive folder.</span></span>
    
 <span data-ttu-id="66758-120">_lppszExplicitClass_</span><span class="sxs-lookup"><span data-stu-id="66758-120">_lppszExplicitClass_</span></span>
  
> <span data-ttu-id="66758-121">[out]指向显式将  _lppEntryID_ 指向的文件夹作为接收文件夹的邮件类的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="66758-121">[out] A pointer to a pointer to the message class that explicitly sets as its receive folder the folder pointed to by  _lppEntryID_.</span></span> <span data-ttu-id="66758-122">此消息类应该与  _lpszMessageClass_ 参数中的类相同，或者是该类的基类。</span><span class="sxs-lookup"><span data-stu-id="66758-122">This message class should either be the same as the class in the  _lpszMessageClass_ parameter, or a base class of that class.</span></span> <span data-ttu-id="66758-123">传递 NULL 表示  _lppEntryID_ 指向的文件夹是邮件存储的默认接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="66758-123">Passing NULL indicates that the folder pointed to by  _lppEntryID_ is the default receive folder for the message store.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="66758-124">返回值</span><span class="sxs-lookup"><span data-stu-id="66758-124">Return value</span></span>

<span data-ttu-id="66758-125">S_OK</span><span class="sxs-lookup"><span data-stu-id="66758-125">S_OK</span></span> 
  
> <span data-ttu-id="66758-126">已成功返回接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="66758-126">The receive folder was successfully returned.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="66758-127">备注</span><span class="sxs-lookup"><span data-stu-id="66758-127">Remarks</span></span>

<span data-ttu-id="66758-128">**IMsgStore：：GetReceiveFolder** 方法获取接收文件夹的条目标识符，该文件夹被指定为接收特定邮件类的传入邮件。</span><span class="sxs-lookup"><span data-stu-id="66758-128">The **IMsgStore::GetReceiveFolder** method obtains the entry identifier of a receive folder, a folder designated to receive incoming messages of a particular message class.</span></span> <span data-ttu-id="66758-129">呼叫者可以在  _lpszMessageClass_ 参数中指定邮件类或 NULL。</span><span class="sxs-lookup"><span data-stu-id="66758-129">Callers can specify a message class or NULL in the  _lpszMessageClass_ parameter.</span></span> <span data-ttu-id="66758-130">如果  _lpszMessageClass_ 为 **NULL，GetReceiveFolder** 将返回以下值：</span><span class="sxs-lookup"><span data-stu-id="66758-130">If  _lpszMessageClass_ is NULL, **GetReceiveFolder** returns the following values:</span></span> 
  
- <span data-ttu-id="66758-131">在  _lppszExplicitClass_ 中，由明确设置接收文件夹的  _lpszMessageClass_ 指向的邮件类的第一个基类的名称。</span><span class="sxs-lookup"><span data-stu-id="66758-131">In  _lppszExplicitClass_, the name of the first base class of the message class pointed to by  _lpszMessageClass_ that does explicitly set a receive folder.</span></span> 
    
- <span data-ttu-id="66758-132">在  _lppEntryID_ 中  _，lppszExplicitClass_ 参数指向的基类的接收文件夹的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="66758-132">In  _lppEntryID_, the entry identifier of the receive folder for the base class pointed to by the  _lppszExplicitClass_ parameter.</span></span> 
    
<span data-ttu-id="66758-133">例如，假设邮件类 IPM 的接收 **文件夹。Note** has been set to the entry identifier of the Inbox and **GetReceiveFolder** is called with the contents of _lpszMessageClass_ set to **IPM.注意。电话**。</span><span class="sxs-lookup"><span data-stu-id="66758-133">For example, suppose the receive folder of the message class **IPM.Note** has been set to the entry identifier of the Inbox and **GetReceiveFolder** is called with the contents of  _lpszMessageClass_ set to **IPM.Note.Phone**.</span></span> <span data-ttu-id="66758-134">如果 **为 IPM。注意。电话** 没有显式接收文件夹集 **，GetReceiveFolder** 返回 _lppEntryID_ 和 IPM 中收件箱的 **条目标识符。** _lppszExplicitClass_ 中的注释。</span><span class="sxs-lookup"><span data-stu-id="66758-134">If **IPM.Note.Phone** does not have an explicit receive folder set, **GetReceiveFolder** returns the entry identifier of the Inbox in  _lppEntryID_ and **IPM.Note** in  _lppszExplicitClass_.</span></span>
  
<span data-ttu-id="66758-135">如果客户端为邮件类调用 **GetReceiveFolder，** 并且尚未为邮件类设置接收文件夹，  _则 lppszExplicitClass_ 可以是零长度字符串、Unicode 格式的字符串或 ANSI 格式的字符串，具体取决于客户端是否在  _ulFlags_ 参数中设置 MAPI_UNICODE 标志。</span><span class="sxs-lookup"><span data-stu-id="66758-135">If the client calls **GetReceiveFolder** for a message class and has not set a receive folder for that message class,  _lppszExplicitClass_ is either a zero-length string, a string in Unicode format, or a string in ANSI format depending on whether the client set the MAPI_UNICODE flag in the  _ulFlags_ parameter.</span></span> 
  
<span data-ttu-id="66758-136">通过传递  _lpszMessageClass_ 参数中的 NULL 获取的默认接收文件夹始终存在于每个邮件存储中。</span><span class="sxs-lookup"><span data-stu-id="66758-136">A default receive folder, obtained by passing NULL in the  _lpszMessageClass_ parameter, always exists for every message store.</span></span> 
  
<span data-ttu-id="66758-137">使用 _lppEntryID_ 中返回的条目标识符完成时，客户端应调用 [MAPIFreeBuffer](mapifreebuffer.md)函数，以释放保留该条目标识符的内存。</span><span class="sxs-lookup"><span data-stu-id="66758-137">A client should call the [MAPIFreeBuffer](mapifreebuffer.md) function when it is done with the entry identifier returned in  _lppEntryID_ to free the memory that holds that entry identifier.</span></span> <span data-ttu-id="66758-138">当使用 _lppszExplicitClass_ 中返回的邮件类字符串完成时，它还应调用 **MAPIFreeBuffer** 以释放包含该字符串的内存。</span><span class="sxs-lookup"><span data-stu-id="66758-138">It should also call **MAPIFreeBuffer** when it is done with the message class string returned in  _lppszExplicitClass_ to free the memory that holds that string.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="66758-139">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="66758-139">MFCMAPI reference</span></span>

<span data-ttu-id="66758-140">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="66758-140">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="66758-141">**文件**</span><span class="sxs-lookup"><span data-stu-id="66758-141">**File**</span></span>|<span data-ttu-id="66758-142">**函数**</span><span class="sxs-lookup"><span data-stu-id="66758-142">**Function**</span></span>|<span data-ttu-id="66758-143">**备注**</span><span class="sxs-lookup"><span data-stu-id="66758-143">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="66758-144">MAPIFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="66758-144">MAPIFunctions.cpp</span></span>  <br/> |<span data-ttu-id="66758-145">GetInbox</span><span class="sxs-lookup"><span data-stu-id="66758-145">GetInbox</span></span>  <br/> |<span data-ttu-id="66758-146">MFCMAPI 使用 **IMsgStore：：GetReceiveFolder** 方法来查找"收件箱"文件夹。</span><span class="sxs-lookup"><span data-stu-id="66758-146">MFCMAPI uses the **IMsgStore::GetReceiveFolder** method to locate the Inbox folder.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="66758-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="66758-147">See also</span></span>



[<span data-ttu-id="66758-148">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="66758-148">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="66758-149">IMsgStore : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="66758-149">IMsgStore : IMAPIProp</span></span>](imsgstoreimapiprop.md)


[<span data-ttu-id="66758-150">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="66758-150">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

