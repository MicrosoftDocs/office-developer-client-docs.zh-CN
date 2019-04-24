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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348774"
---
# <a name="imsgstoregetreceivefolder"></a><span data-ttu-id="dd0c3-103">IMsgStore::GetReceiveFolder</span><span class="sxs-lookup"><span data-stu-id="dd0c3-103">IMsgStore::GetReceiveFolder</span></span>

  
  
<span data-ttu-id="dd0c3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="dd0c3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="dd0c3-105">获取作为指定邮件类别的传入邮件的目标或作为邮件存储的默认接收文件夹而建立的文件夹。</span><span class="sxs-lookup"><span data-stu-id="dd0c3-105">Obtains the folder that was established as the destination for incoming messages of a specified message class or as the default receive folder for the message store.</span></span>
  
```cpp
HRESULT GetReceiveFolder(
  LPSTR lpszMessageClass,
  ULONG ulFlags,
  ULONG FAR * lpcbEntryID,
  LPENTRYID FAR * lppEntryID,
  LPSTR FAR * lppszExplicitClass
);
```

## <a name="parameters"></a><span data-ttu-id="dd0c3-106">参数</span><span class="sxs-lookup"><span data-stu-id="dd0c3-106">Parameters</span></span>

 <span data-ttu-id="dd0c3-107">_lpszMessageClass_</span><span class="sxs-lookup"><span data-stu-id="dd0c3-107">_lpszMessageClass_</span></span>
  
> <span data-ttu-id="dd0c3-108">实时指向与接收文件夹相关联的邮件类的指针。</span><span class="sxs-lookup"><span data-stu-id="dd0c3-108">[in] A pointer to a message class that is associated with a receive folder.</span></span> <span data-ttu-id="dd0c3-109">如果将_lpszMessageClass_参数设置为 NULL 或空字符串, 则**GetReceiveFolder**将返回邮件存储区的默认接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="dd0c3-109">If the  _lpszMessageClass_ parameter is set to NULL or an empty string, **GetReceiveFolder** returns the default receive folder for the message store.</span></span> 
    
 <span data-ttu-id="dd0c3-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="dd0c3-110">_ulFlags_</span></span>
  
> <span data-ttu-id="dd0c3-111">实时标志的位掩码, 用于控制传入和返回的字符串的类型。</span><span class="sxs-lookup"><span data-stu-id="dd0c3-111">[in] A bitmask of flags that controls the type of the passed-in and returned strings.</span></span> <span data-ttu-id="dd0c3-112">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="dd0c3-112">The following flag can be set:</span></span>
    
<span data-ttu-id="dd0c3-113">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="dd0c3-113">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="dd0c3-114">邮件类字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="dd0c3-114">The message class string is in Unicode format.</span></span> <span data-ttu-id="dd0c3-115">如果未设置 MAPI_UNICODE 标志, 则邮件类字符串将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="dd0c3-115">If the MAPI_UNICODE flag is not set, the message class string is in ANSI format.</span></span>
    
 <span data-ttu-id="dd0c3-116">_lpcbEntryID_</span><span class="sxs-lookup"><span data-stu-id="dd0c3-116">_lpcbEntryID_</span></span>
  
> <span data-ttu-id="dd0c3-117">排除指向条目标识符中由_lppEntryID_参数指向的字节计数的指针。</span><span class="sxs-lookup"><span data-stu-id="dd0c3-117">[out] A pointer to the byte count in the entry identifier pointed to by the  _lppEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="dd0c3-118">_lppEntryID_</span><span class="sxs-lookup"><span data-stu-id="dd0c3-118">_lppEntryID_</span></span>
  
> <span data-ttu-id="dd0c3-119">排除指向所请求的接收文件夹的条目标识符的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="dd0c3-119">[out] A pointer to a pointer to the entry identifier for the requested receive folder.</span></span>
    
 <span data-ttu-id="dd0c3-120">_lppszExplicitClass_</span><span class="sxs-lookup"><span data-stu-id="dd0c3-120">_lppszExplicitClass_</span></span>
  
> <span data-ttu-id="dd0c3-121">排除指向邮件类的指针的指针, 该邮件类显式设置为其接收文件夹由_lppEntryID_指向的文件夹。</span><span class="sxs-lookup"><span data-stu-id="dd0c3-121">[out] A pointer to a pointer to the message class that explicitly sets as its receive folder the folder pointed to by  _lppEntryID_.</span></span> <span data-ttu-id="dd0c3-122">此邮件类应与_lpszMessageClass_参数中的类相同, 或与该类的基类相同。</span><span class="sxs-lookup"><span data-stu-id="dd0c3-122">This message class should either be the same as the class in the  _lpszMessageClass_ parameter, or a base class of that class.</span></span> <span data-ttu-id="dd0c3-123">传递 NULL 表示_lppEntryID_指向的文件夹是邮件存储的默认接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="dd0c3-123">Passing NULL indicates that the folder pointed to by  _lppEntryID_ is the default receive folder for the message store.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="dd0c3-124">返回值</span><span class="sxs-lookup"><span data-stu-id="dd0c3-124">Return value</span></span>

<span data-ttu-id="dd0c3-125">S_OK</span><span class="sxs-lookup"><span data-stu-id="dd0c3-125">S_OK</span></span> 
  
> <span data-ttu-id="dd0c3-126">已成功返回接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="dd0c3-126">The receive folder was successfully returned.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="dd0c3-127">注解</span><span class="sxs-lookup"><span data-stu-id="dd0c3-127">Remarks</span></span>

<span data-ttu-id="dd0c3-128">**IMsgStore:: GetReceiveFolder**方法获取接收文件夹的条目标识符, 该文件夹是指定用于接收特定邮件类别的传入邮件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="dd0c3-128">The **IMsgStore::GetReceiveFolder** method obtains the entry identifier of a receive folder, a folder designated to receive incoming messages of a particular message class.</span></span> <span data-ttu-id="dd0c3-129">调用方可以在_lpszMessageClass_参数中指定邮件类或 NULL。</span><span class="sxs-lookup"><span data-stu-id="dd0c3-129">Callers can specify a message class or NULL in the  _lpszMessageClass_ parameter.</span></span> <span data-ttu-id="dd0c3-130">如果_lpszMessageClass_为 NULL, 则**GetReceiveFolder**将返回以下值:</span><span class="sxs-lookup"><span data-stu-id="dd0c3-130">If  _lpszMessageClass_ is NULL, **GetReceiveFolder** returns the following values:</span></span> 
  
- <span data-ttu-id="dd0c3-131">在_lppszExplicitClass_中, 由_lpszMessageClass_指向的邮件类的第一个基类的名称, 该基类显式设置接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="dd0c3-131">In  _lppszExplicitClass_, the name of the first base class of the message class pointed to by  _lpszMessageClass_ that does explicitly set a receive folder.</span></span> 
    
- <span data-ttu-id="dd0c3-132">在_lppEntryID_中, 由_lppszExplicitClass_参数指向的基类的接收文件夹的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="dd0c3-132">In  _lppEntryID_, the entry identifier of the receive folder for the base class pointed to by the  _lppszExplicitClass_ parameter.</span></span> 
    
<span data-ttu-id="dd0c3-133">例如, 假设邮件类为 IPM 的接收文件夹 **。注意**已设置为收件箱的条目标识符, 并且将使用设置为 IPM 的_lpszMessageClass_的内容调用**GetReceiveFolder** **。注意**: "电话"。</span><span class="sxs-lookup"><span data-stu-id="dd0c3-133">For example, suppose the receive folder of the message class **IPM.Note** has been set to the entry identifier of the Inbox and **GetReceiveFolder** is called with the contents of  _lpszMessageClass_ set to **IPM.Note.Phone**.</span></span> <span data-ttu-id="dd0c3-134">如果**IPM。注意: 电话**未设置显式接收文件夹, **GetReceiveFolder**返回_lppEntryID_和 IPM 中的收件箱的条目标识符 **。注意**在_lppszExplicitClass_中。</span><span class="sxs-lookup"><span data-stu-id="dd0c3-134">If **IPM.Note.Phone** does not have an explicit receive folder set, **GetReceiveFolder** returns the entry identifier of the Inbox in  _lppEntryID_ and **IPM.Note** in  _lppszExplicitClass_.</span></span>
  
<span data-ttu-id="dd0c3-135">如果客户端为邮件类调用**GetReceiveFolder** , 但尚未为该邮件类别设置接收文件夹, 则_lppszExplicitClass_可以是零长度字符串、Unicode 格式的字符串, 也可以是 ANSI 格式的字符串, 具体取决于是否client 在_ulFlags_参数中设置 MAPI_UNICODE 标志。</span><span class="sxs-lookup"><span data-stu-id="dd0c3-135">If the client calls **GetReceiveFolder** for a message class and has not set a receive folder for that message class,  _lppszExplicitClass_ is either a zero-length string, a string in Unicode format, or a string in ANSI format depending on whether the client set the MAPI_UNICODE flag in the  _ulFlags_ parameter.</span></span> 
  
<span data-ttu-id="dd0c3-136">通过在_lpszMessageClass_参数中传递 NULL 获取的默认接收文件夹, 对于每个邮件存储始终存在。</span><span class="sxs-lookup"><span data-stu-id="dd0c3-136">A default receive folder, obtained by passing NULL in the  _lpszMessageClass_ parameter, always exists for every message store.</span></span> 
  
<span data-ttu-id="dd0c3-137">在使用_lppEntryID_中返回的条目标识符完成时, 客户端应调用[MAPIFreeBuffer](mapifreebuffer.md)函数, 以释放保留该条目标识符的内存。</span><span class="sxs-lookup"><span data-stu-id="dd0c3-137">A client should call the [MAPIFreeBuffer](mapifreebuffer.md) function when it is done with the entry identifier returned in  _lppEntryID_ to free the memory that holds that entry identifier.</span></span> <span data-ttu-id="dd0c3-138">在使用_lppszExplicitClass_中返回的邮件类字符串完成时, 它还应调用**MAPIFreeBuffer** , 以释放保留该字符串的内存。</span><span class="sxs-lookup"><span data-stu-id="dd0c3-138">It should also call **MAPIFreeBuffer** when it is done with the message class string returned in  _lppszExplicitClass_ to free the memory that holds that string.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="dd0c3-139">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="dd0c3-139">MFCMAPI reference</span></span>

<span data-ttu-id="dd0c3-140">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="dd0c3-140">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="dd0c3-141">**文件**</span><span class="sxs-lookup"><span data-stu-id="dd0c3-141">**File**</span></span>|<span data-ttu-id="dd0c3-142">**函数**</span><span class="sxs-lookup"><span data-stu-id="dd0c3-142">**Function**</span></span>|<span data-ttu-id="dd0c3-143">**备注**</span><span class="sxs-lookup"><span data-stu-id="dd0c3-143">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="dd0c3-144">MAPIFunctions</span><span class="sxs-lookup"><span data-stu-id="dd0c3-144">MAPIFunctions.cpp</span></span>  <br/> |<span data-ttu-id="dd0c3-145">GetInbox</span><span class="sxs-lookup"><span data-stu-id="dd0c3-145">GetInbox</span></span>  <br/> |<span data-ttu-id="dd0c3-146">MFCMAPI 使用**IMsgStore:: GetReceiveFolder**方法查找 "收件箱" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="dd0c3-146">MFCMAPI uses the **IMsgStore::GetReceiveFolder** method to locate the Inbox folder.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="dd0c3-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dd0c3-147">See also</span></span>



[<span data-ttu-id="dd0c3-148">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="dd0c3-148">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="dd0c3-149">IMsgStore : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="dd0c3-149">IMsgStore : IMAPIProp</span></span>](imsgstoreimapiprop.md)


[<span data-ttu-id="dd0c3-150">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="dd0c3-150">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

