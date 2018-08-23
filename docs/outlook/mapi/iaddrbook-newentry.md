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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: eaf472a380acd62cddb2c20c35335ccb1e2ce07f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22585855"
---
# <a name="iaddrbooknewentry"></a><span data-ttu-id="6c522-103">IAddrBook::NewEntry</span><span class="sxs-lookup"><span data-stu-id="6c522-103">IAddrBook::NewEntry</span></span>

  
  
<span data-ttu-id="6c522-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6c522-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6c522-105">将一个新收件人添加到通讯簿容器或传出邮件的收件人列表。</span><span class="sxs-lookup"><span data-stu-id="6c522-105">Adds a new recipient to an address book container or to the recipient list of an outgoing message.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="6c522-106">参数</span><span class="sxs-lookup"><span data-stu-id="6c522-106">Parameters</span></span>

 <span data-ttu-id="6c522-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="6c522-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="6c522-108">[in]对话框中的父窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="6c522-108">[in] A handle to the parent window for the dialog box.</span></span>
    
 <span data-ttu-id="6c522-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="6c522-109">_ulFlags_</span></span>
  
> <span data-ttu-id="6c522-110">[in]位掩码的标志的控制使用的文本的类型。</span><span class="sxs-lookup"><span data-stu-id="6c522-110">[in] A bitmask of flags that controls the type of the text that is used.</span></span> <span data-ttu-id="6c522-111">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="6c522-111">The following flag can be set:</span></span>
    
<span data-ttu-id="6c522-112">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="6c522-112">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="6c522-113">传入的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="6c522-113">The passed-in strings are in Unicode format.</span></span> <span data-ttu-id="6c522-114">如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="6c522-114">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="6c522-115">_cbEIDContainer_</span><span class="sxs-lookup"><span data-stu-id="6c522-115">_cbEIDContainer_</span></span>
  
> <span data-ttu-id="6c522-116">[in]在_lpEIDContainer_参数指向的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="6c522-116">[in] The byte count in the entry identifier pointed to by the  _lpEIDContainer_ parameter.</span></span> 
    
 <span data-ttu-id="6c522-117">_lpEIDContainer_</span><span class="sxs-lookup"><span data-stu-id="6c522-117">_lpEIDContainer_</span></span>
  
> <span data-ttu-id="6c522-118">[in]指向新收件人的要添加的容器的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="6c522-118">[in] A pointer to the entry identifier of the container where the new recipient is to be added.</span></span> <span data-ttu-id="6c522-119">如果_cbEIDContainer_参数为零， **NewEntry**方法就会返回一个收件人的项标识符和模板的列表就好像调用[IAddrBook::CreateOneOff](iaddrbook-createoneoff.md)方法。</span><span class="sxs-lookup"><span data-stu-id="6c522-119">If the  _cbEIDContainer_ parameter is zero, the **NewEntry** method returns a recipient entry identifier and a list of templates as if the [IAddrBook::CreateOneOff](iaddrbook-createoneoff.md) method was called.</span></span> 
    
 <span data-ttu-id="6c522-120">_cbEIDNewEntryTpl_</span><span class="sxs-lookup"><span data-stu-id="6c522-120">_cbEIDNewEntryTpl_</span></span>
  
> <span data-ttu-id="6c522-121">[in]在_lpEIDNewEntryTpl_参数指向的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="6c522-121">[in] The byte count in the entry identifier pointed to by the  _lpEIDNewEntryTpl_ parameter.</span></span> 
    
 <span data-ttu-id="6c522-122">_lpEIDNewEntryTpl_</span><span class="sxs-lookup"><span data-stu-id="6c522-122">_lpEIDNewEntryTpl_</span></span>
  
> <span data-ttu-id="6c522-123">[in]一个指向将用于创建新收件人的一次性模板。</span><span class="sxs-lookup"><span data-stu-id="6c522-123">[in] A pointer to a one-off template that will be used to create the new recipient.</span></span> <span data-ttu-id="6c522-124">如果_cbEIDNewEntryTpl_为零，并且_lpEIDNewEntryTpl_为 NULL， **NewEntry**将显示一个对话框，与用户可以选择从列表中添加新项的模板。</span><span class="sxs-lookup"><span data-stu-id="6c522-124">If  _cbEIDNewEntryTpl_ is zero and  _lpEIDNewEntryTpl_ is NULL, **NewEntry** displays a dialog box with which the user can select from a list of templates for adding new entries.</span></span> 
    
 <span data-ttu-id="6c522-125">_lpcbEIDNewEntry_</span><span class="sxs-lookup"><span data-stu-id="6c522-125">_lpcbEIDNewEntry_</span></span>
  
> <span data-ttu-id="6c522-126">[输出]一个指向_lppEIDNewEntry_参数指向该条目标识符中的字节数。</span><span class="sxs-lookup"><span data-stu-id="6c522-126">[out] A pointer to the byte count in the entry identifier pointed to by the  _lppEIDNewEntry_ parameter.</span></span> 
    
 <span data-ttu-id="6c522-127">_lppEIDNewEntry_</span><span class="sxs-lookup"><span data-stu-id="6c522-127">_lppEIDNewEntry_</span></span>
  
> <span data-ttu-id="6c522-128">[输出]为指向新收件人的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="6c522-128">[out] A pointer to a pointer to the new recipient's entry identifier.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="6c522-129">返回值</span><span class="sxs-lookup"><span data-stu-id="6c522-129">Return value</span></span>

<span data-ttu-id="6c522-130">S_OK</span><span class="sxs-lookup"><span data-stu-id="6c522-130">S_OK</span></span> 
  
> <span data-ttu-id="6c522-131">已成功创建新的通讯簿条目。</span><span class="sxs-lookup"><span data-stu-id="6c522-131">The new address book entry was successfully created.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="6c522-132">注解</span><span class="sxs-lookup"><span data-stu-id="6c522-132">Remarks</span></span>

<span data-ttu-id="6c522-133">**NewEntry**方法创建新通讯簿条目，直接将容器添加或要用于传出邮件地址。</span><span class="sxs-lookup"><span data-stu-id="6c522-133">The **NewEntry** method creates a new address book entry, to be added directly into a container or to be used to address an outgoing message.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="6c522-134">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="6c522-134">Notes to callers</span></span>

<span data-ttu-id="6c522-135">如果您希望新条目添加到特定的容器，设置为容器的项标识符和_cbEIDContainer_中的项标识符的字节数为_lpEIDContainer_ 。</span><span class="sxs-lookup"><span data-stu-id="6c522-135">If you want the new entry to be added to a specific container, set  _lpEIDContainer_ to the container's entry identifier and  _cbEIDContainer_ to the byte count in the entry identifier.</span></span> 
  
<span data-ttu-id="6c522-136">如果您希望添加到的传出邮件的收件人列表的新项，设置为空，并且为零的_cbEIDContainer_ _lpEIDContainer_ 。</span><span class="sxs-lookup"><span data-stu-id="6c522-136">If you want the new entry to be added to the recipient list of an outgoing message, set  _lpEIDContainer_ to NULL and  _cbEIDContainer_ to zero.</span></span> 
  
<span data-ttu-id="6c522-137">如果您想要允许客户端应用程序选择项的类型的用户创建，传递零_cbEIDNewEntryTpl_在和中_lpEIDNewEntryTpl_NULL。</span><span class="sxs-lookup"><span data-stu-id="6c522-137">If you want to allow the user of a client application to select the type of entry to be created, pass zero in  _cbEIDNewEntryTpl_ and NULL in  _lpEIDNewEntryTpl_.</span></span> <span data-ttu-id="6c522-138">**NewEntry**方法显示 MAPI 一次性表，通过 MAPI 和每个通讯簿提供程序支持会话中的模板的列表。</span><span class="sxs-lookup"><span data-stu-id="6c522-138">The **NewEntry** method displays the MAPI one-off table, a list of templates supported by MAPI and by each address book provider in the session.</span></span> <span data-ttu-id="6c522-139">每个模板可以创建一个或多个地址类型的收件人条目。</span><span class="sxs-lookup"><span data-stu-id="6c522-139">Each template can create a recipient entry for one or more address types.</span></span> 
  
<span data-ttu-id="6c522-140">如果您想要保留的新条目的项标识符，在_lpcbEIDNewEntry_和_lppEIDNewEntry_参数中传递有效的指针。</span><span class="sxs-lookup"><span data-stu-id="6c522-140">If you want to retain the entry identifier of the new entry, pass valid pointers in the  _lpcbEIDNewEntry_ and  _lppEIDNewEntry_ parameters.</span></span> <span data-ttu-id="6c522-141">您负责完与其通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数释放此条目标识符。</span><span class="sxs-lookup"><span data-stu-id="6c522-141">You are responsible for freeing this entry identifier when you are finished with it by calling the [MAPIFreeBuffer](mapifreebuffer.md) function.</span></span> 
  
<span data-ttu-id="6c522-142">若要使用特定模板可修改容器中添加一个新项，请使用以下过程：</span><span class="sxs-lookup"><span data-stu-id="6c522-142">To use a particular template to add a new entry to a modifiable container, use the following procedure:</span></span>
  
1. <span data-ttu-id="6c522-143">调用[IMAPISession::OpenEntry](imapisession-openentry.md)方法以打开目标容器中，并将_lpEntryID_参数设置为容器的项标识符。</span><span class="sxs-lookup"><span data-stu-id="6c522-143">Call the [IMAPISession::OpenEntry](imapisession-openentry.md) method to open the destination container, and set the  _lpEntryID_ parameter to the entry identifier of the container.</span></span> 
    
2. <span data-ttu-id="6c522-144">调用目标容器[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法，并将**PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) _ulPropTag_参数和_lpiid_参数设置为 IID_IMAPITable。</span><span class="sxs-lookup"><span data-stu-id="6c522-144">Call the destination container's [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method, and set the  _ulPropTag_ parameter to **PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) and the  _lpiid_ parameter to IID_IMAPITable.</span></span> <span data-ttu-id="6c522-145">容器将返回一个一次性表，列出所有它支持用于创建新条目的模板。</span><span class="sxs-lookup"><span data-stu-id="6c522-145">The container will return a one-off table that lists all the templates that it supports for creating new entries.</span></span> 
    
3. <span data-ttu-id="6c522-146">检索表示您想要创建的项的特定类型的模板的行。</span><span class="sxs-lookup"><span data-stu-id="6c522-146">Retrieve the row that represents the template for the particular type of entry you want to create.</span></span> <span data-ttu-id="6c522-147">**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) 列指示由模板支持的地址类型。</span><span class="sxs-lookup"><span data-stu-id="6c522-147">The **PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) column indicates the address type that is supported by the template.</span></span>
    
4. <span data-ttu-id="6c522-148">调用**NewEntry**方法，并将_lpEIDNewEntryTpl_设置为所选模板的项标识符。</span><span class="sxs-lookup"><span data-stu-id="6c522-148">Call the **NewEntry** method, and set  _lpEIDNewEntryTpl_ to the entry identifier of the selected template.</span></span> <span data-ttu-id="6c522-149">项标识符将是一次性的表中的模板的行中的**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 列。</span><span class="sxs-lookup"><span data-stu-id="6c522-149">The entry identifier will be the **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) column from the template's row in the one-off table.</span></span> <span data-ttu-id="6c522-150">传递零_cbEIDContainer_在和中_lpEIDContainer_NULL。</span><span class="sxs-lookup"><span data-stu-id="6c522-150">Pass zero in  _cbEIDContainer_ and NULL in  _lpEIDContainer_.</span></span> <span data-ttu-id="6c522-151">如果您想要保留的新条目的项标识符，请在_lppEIDNewEntry_参数中传递一个有效的指针。</span><span class="sxs-lookup"><span data-stu-id="6c522-151">Pass a valid pointer in the  _lppEIDNewEntry_ parameter if you want to retain the new entry's entry identifier.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="6c522-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6c522-152">See also</span></span>



[<span data-ttu-id="6c522-153">IAddrBook::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="6c522-153">IAddrBook::OpenEntry</span></span>](iaddrbook-openentry.md)
  
[<span data-ttu-id="6c522-154">IMAPIProp::OpenProperty</span><span class="sxs-lookup"><span data-stu-id="6c522-154">IMAPIProp::OpenProperty</span></span>](imapiprop-openproperty.md)
  
[<span data-ttu-id="6c522-155">PidTagCreateTemplates 规范属性</span><span class="sxs-lookup"><span data-stu-id="6c522-155">PidTagCreateTemplates Canonical Property</span></span>](pidtagcreatetemplates-canonical-property.md)
  
[<span data-ttu-id="6c522-156">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="6c522-156">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)

