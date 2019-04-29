---
title: IAddrBookNewEntry
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IAddrBook.NewEntry
api_type:
- COM
ms.assetid: 8d2d786b-e621-456d-b087-3373df6f8ac5
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 285da82d143524d2b2cf73ed3e5f1e3aeef6f9b3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405098"
---
# <a name="iaddrbooknewentry"></a><span data-ttu-id="ec7ec-103">IAddrBook::NewEntry</span><span class="sxs-lookup"><span data-stu-id="ec7ec-103">IAddrBook::NewEntry</span></span>

  
  
<span data-ttu-id="ec7ec-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ec7ec-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ec7ec-105">将新的收件人添加到通讯簿容器或传出邮件的收件人列表中。</span><span class="sxs-lookup"><span data-stu-id="ec7ec-105">Adds a new recipient to an address book container or to the recipient list of an outgoing message.</span></span>
  
```cpp
HRESULT NewEntry(
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  ULONG cbEIDContainer,
  LPENTRYID lpEIDContainer,
  ULONG cbEIDNewEntryTpl,
  LPENTRYID lpEIDNewEntryTpl,
  ULONG FAR * lpcbEIDNewEntry,
  LPENTRYID FAR * lppEIDNewEntry
);
```

## <a name="parameters"></a><span data-ttu-id="ec7ec-106">参数</span><span class="sxs-lookup"><span data-stu-id="ec7ec-106">Parameters</span></span>

 <span data-ttu-id="ec7ec-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="ec7ec-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="ec7ec-108">实时对话框的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="ec7ec-108">[in] A handle to the parent window for the dialog box.</span></span>
    
 <span data-ttu-id="ec7ec-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="ec7ec-109">_ulFlags_</span></span>
  
> <span data-ttu-id="ec7ec-110">实时标志的位掩码, 用于控制所使用文本的类型。</span><span class="sxs-lookup"><span data-stu-id="ec7ec-110">[in] A bitmask of flags that controls the type of the text that is used.</span></span> <span data-ttu-id="ec7ec-111">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="ec7ec-111">The following flag can be set:</span></span>
    
<span data-ttu-id="ec7ec-112">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="ec7ec-112">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="ec7ec-113">传入的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="ec7ec-113">The passed-in strings are in Unicode format.</span></span> <span data-ttu-id="ec7ec-114">如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="ec7ec-114">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="ec7ec-115">_cbEIDContainer_</span><span class="sxs-lookup"><span data-stu-id="ec7ec-115">_cbEIDContainer_</span></span>
  
> <span data-ttu-id="ec7ec-116">实时条目标识符中由_lpEIDContainer_参数指向的字节数。</span><span class="sxs-lookup"><span data-stu-id="ec7ec-116">[in] The byte count in the entry identifier pointed to by the  _lpEIDContainer_ parameter.</span></span> 
    
 <span data-ttu-id="ec7ec-117">_lpEIDContainer_</span><span class="sxs-lookup"><span data-stu-id="ec7ec-117">_lpEIDContainer_</span></span>
  
> <span data-ttu-id="ec7ec-118">实时一个指针, 指向要在其中添加新收件人的容器的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="ec7ec-118">[in] A pointer to the entry identifier of the container where the new recipient is to be added.</span></span> <span data-ttu-id="ec7ec-119">如果_cbEIDContainer_参数为零, **NewEntry**方法将返回收件人条目标识符和模板列表, 就像调用了[IAddrBook:: CreateOneOff](iaddrbook-createoneoff.md)方法一样。</span><span class="sxs-lookup"><span data-stu-id="ec7ec-119">If the  _cbEIDContainer_ parameter is zero, the **NewEntry** method returns a recipient entry identifier and a list of templates as if the [IAddrBook::CreateOneOff](iaddrbook-createoneoff.md) method was called.</span></span> 
    
 <span data-ttu-id="ec7ec-120">_cbEIDNewEntryTpl_</span><span class="sxs-lookup"><span data-stu-id="ec7ec-120">_cbEIDNewEntryTpl_</span></span>
  
> <span data-ttu-id="ec7ec-121">实时条目标识符中由_lpEIDNewEntryTpl_参数指向的字节数。</span><span class="sxs-lookup"><span data-stu-id="ec7ec-121">[in] The byte count in the entry identifier pointed to by the  _lpEIDNewEntryTpl_ parameter.</span></span> 
    
 <span data-ttu-id="ec7ec-122">_lpEIDNewEntryTpl_</span><span class="sxs-lookup"><span data-stu-id="ec7ec-122">_lpEIDNewEntryTpl_</span></span>
  
> <span data-ttu-id="ec7ec-123">实时指向将用于创建新收件人的一次性模板的指针。</span><span class="sxs-lookup"><span data-stu-id="ec7ec-123">[in] A pointer to a one-off template that will be used to create the new recipient.</span></span> <span data-ttu-id="ec7ec-124">如果_cbEIDNewEntryTpl_为零且_lpEIDNewEntryTpl_为 NULL, 则**NewEntry**将显示一个对话框, 用户可以从该对话框中选择用于添加新条目的模板列表。</span><span class="sxs-lookup"><span data-stu-id="ec7ec-124">If  _cbEIDNewEntryTpl_ is zero and  _lpEIDNewEntryTpl_ is NULL, **NewEntry** displays a dialog box with which the user can select from a list of templates for adding new entries.</span></span> 
    
 <span data-ttu-id="ec7ec-125">_lpcbEIDNewEntry_</span><span class="sxs-lookup"><span data-stu-id="ec7ec-125">_lpcbEIDNewEntry_</span></span>
  
> <span data-ttu-id="ec7ec-126">排除指向条目标识符中由_lppEIDNewEntry_参数指向的字节计数的指针。</span><span class="sxs-lookup"><span data-stu-id="ec7ec-126">[out] A pointer to the byte count in the entry identifier pointed to by the  _lppEIDNewEntry_ parameter.</span></span> 
    
 <span data-ttu-id="ec7ec-127">_lppEIDNewEntry_</span><span class="sxs-lookup"><span data-stu-id="ec7ec-127">_lppEIDNewEntry_</span></span>
  
> <span data-ttu-id="ec7ec-128">排除指向新收件人的条目标识符的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="ec7ec-128">[out] A pointer to a pointer to the new recipient's entry identifier.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="ec7ec-129">返回值</span><span class="sxs-lookup"><span data-stu-id="ec7ec-129">Return value</span></span>

<span data-ttu-id="ec7ec-130">S_OK</span><span class="sxs-lookup"><span data-stu-id="ec7ec-130">S_OK</span></span> 
  
> <span data-ttu-id="ec7ec-131">已成功创建新的通讯簿条目。</span><span class="sxs-lookup"><span data-stu-id="ec7ec-131">The new address book entry was successfully created.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="ec7ec-132">说明</span><span class="sxs-lookup"><span data-stu-id="ec7ec-132">Remarks</span></span>

<span data-ttu-id="ec7ec-133">**NewEntry**方法创建一个新的通讯簿条目, 以将其直接添加到容器中或用于处理传出邮件。</span><span class="sxs-lookup"><span data-stu-id="ec7ec-133">The **NewEntry** method creates a new address book entry, to be added directly into a container or to be used to address an outgoing message.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="ec7ec-134">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="ec7ec-134">Notes to callers</span></span>

<span data-ttu-id="ec7ec-135">如果要将新项添加到特定容器, 请将_lpEIDContainer_的条目标识符和_cbEIDContainer_设置为条目标识符中的字节数。</span><span class="sxs-lookup"><span data-stu-id="ec7ec-135">If you want the new entry to be added to a specific container, set  _lpEIDContainer_ to the container's entry identifier and  _cbEIDContainer_ to the byte count in the entry identifier.</span></span> 
  
<span data-ttu-id="ec7ec-136">如果要将新条目添加到传出邮件的收件人列表中, 请将_lpEIDContainer_设置为 NULL, 并将_cbEIDContainer_设置为零。</span><span class="sxs-lookup"><span data-stu-id="ec7ec-136">If you want the new entry to be added to the recipient list of an outgoing message, set  _lpEIDContainer_ to NULL and  _cbEIDContainer_ to zero.</span></span> 
  
<span data-ttu-id="ec7ec-137">如果要允许客户端应用程序的用户选择要创建的条目的类型, 请在_lpEIDNewEntryTpl_中传递_cbEIDNewEntryTpl_和 NULL 中的零。</span><span class="sxs-lookup"><span data-stu-id="ec7ec-137">If you want to allow the user of a client application to select the type of entry to be created, pass zero in  _cbEIDNewEntryTpl_ and NULL in  _lpEIDNewEntryTpl_.</span></span> <span data-ttu-id="ec7ec-138">**NewEntry**方法显示 mapi 的一次性表、mapi 支持的模板列表以及会话中的每个通讯簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="ec7ec-138">The **NewEntry** method displays the MAPI one-off table, a list of templates supported by MAPI and by each address book provider in the session.</span></span> <span data-ttu-id="ec7ec-139">每个模板都可以为一个或多个地址类型创建收件人条目。</span><span class="sxs-lookup"><span data-stu-id="ec7ec-139">Each template can create a recipient entry for one or more address types.</span></span> 
  
<span data-ttu-id="ec7ec-140">如果要保留新条目的条目标识符, 请在_lpcbEIDNewEntry_和_lppEIDNewEntry_参数中传递有效的指针。</span><span class="sxs-lookup"><span data-stu-id="ec7ec-140">If you want to retain the entry identifier of the new entry, pass valid pointers in the  _lpcbEIDNewEntry_ and  _lppEIDNewEntry_ parameters.</span></span> <span data-ttu-id="ec7ec-141">通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数, 您负责在完成此条目标识符后释放此条目标识符。</span><span class="sxs-lookup"><span data-stu-id="ec7ec-141">You are responsible for freeing this entry identifier when you are finished with it by calling the [MAPIFreeBuffer](mapifreebuffer.md) function.</span></span> 
  
<span data-ttu-id="ec7ec-142">若要使用特定模板将新条目添加到可修改容器中, 请使用以下过程:</span><span class="sxs-lookup"><span data-stu-id="ec7ec-142">To use a particular template to add a new entry to a modifiable container, use the following procedure:</span></span>
  
1. <span data-ttu-id="ec7ec-143">调用[IMAPISession:: OpenEntry](imapisession-openentry.md)方法打开目标容器, 并将_lpEntryID_参数设置为容器的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="ec7ec-143">Call the [IMAPISession::OpenEntry](imapisession-openentry.md) method to open the destination container, and set the  _lpEntryID_ parameter to the entry identifier of the container.</span></span> 
    
2. <span data-ttu-id="ec7ec-144">调用目标容器的[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法, 并将_ulPropTag_参数设置为**PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)), 并将_lpiid_参数设置为 IID_IMAPITable。</span><span class="sxs-lookup"><span data-stu-id="ec7ec-144">Call the destination container's [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method, and set the  _ulPropTag_ parameter to **PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) and the  _lpiid_ parameter to IID_IMAPITable.</span></span> <span data-ttu-id="ec7ec-145">容器将返回一个一次性表格, 其中列出了创建新条目所支持的所有模板。</span><span class="sxs-lookup"><span data-stu-id="ec7ec-145">The container will return a one-off table that lists all the templates that it supports for creating new entries.</span></span> 
    
3. <span data-ttu-id="ec7ec-146">检索表示要创建的特定类型的条目的模板的行。</span><span class="sxs-lookup"><span data-stu-id="ec7ec-146">Retrieve the row that represents the template for the particular type of entry you want to create.</span></span> <span data-ttu-id="ec7ec-147">" **PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))" 列指示模板支持的地址类型。</span><span class="sxs-lookup"><span data-stu-id="ec7ec-147">The **PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) column indicates the address type that is supported by the template.</span></span>
    
4. <span data-ttu-id="ec7ec-148">调用**NewEntry**方法, 并将_lpEIDNewEntryTpl_设置为选定模板的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="ec7ec-148">Call the **NewEntry** method, and set  _lpEIDNewEntryTpl_ to the entry identifier of the selected template.</span></span> <span data-ttu-id="ec7ec-149">条目标识符将是来自一次性表中的模板行的**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 列。</span><span class="sxs-lookup"><span data-stu-id="ec7ec-149">The entry identifier will be the **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) column from the template's row in the one-off table.</span></span> <span data-ttu-id="ec7ec-150">在_lpEIDContainer_中传递_cbEIDContainer_和 NULL 中的零。</span><span class="sxs-lookup"><span data-stu-id="ec7ec-150">Pass zero in  _cbEIDContainer_ and NULL in  _lpEIDContainer_.</span></span> <span data-ttu-id="ec7ec-151">如果要保留新条目的条目标识符, 请在_lppEIDNewEntry_参数中传递有效的指针。</span><span class="sxs-lookup"><span data-stu-id="ec7ec-151">Pass a valid pointer in the  _lppEIDNewEntry_ parameter if you want to retain the new entry's entry identifier.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="ec7ec-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ec7ec-152">See also</span></span>



[<span data-ttu-id="ec7ec-153">IAddrBook::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="ec7ec-153">IAddrBook::OpenEntry</span></span>](iaddrbook-openentry.md)
  
[<span data-ttu-id="ec7ec-154">IMAPIProp::OpenProperty</span><span class="sxs-lookup"><span data-stu-id="ec7ec-154">IMAPIProp::OpenProperty</span></span>](imapiprop-openproperty.md)
  
[<span data-ttu-id="ec7ec-155">PidTagCreateTemplates 规范属性</span><span class="sxs-lookup"><span data-stu-id="ec7ec-155">PidTagCreateTemplates Canonical Property</span></span>](pidtagcreatetemplates-canonical-property.md)
  
[<span data-ttu-id="ec7ec-156">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="ec7ec-156">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)

