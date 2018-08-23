---
title: IABLogonGetOneOffTable
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IABLogon.GetOneOffTable
api_type:
- COM
ms.assetid: 7ac2a8d4-6890-4346-a6b6-34deca9dab50
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 3732d8cbfaf9a6a10c62eae9e7a12b04de8a80ee
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22583678"
---
# <a name="iablogongetoneofftable"></a><span data-ttu-id="f9268-103">IABLogon::GetOneOffTable</span><span class="sxs-lookup"><span data-stu-id="f9268-103">IABLogon::GetOneOffTable</span></span>

  
  
<span data-ttu-id="f9268-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f9268-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f9268-105">返回一个一次性模板，用于创建要添加到的传出邮件的收件人列表的收件人的表。</span><span class="sxs-lookup"><span data-stu-id="f9268-105">Returns a table of one-off templates for creating recipients to be added to the recipient list of an outgoing message.</span></span>
  
```cpp
HRESULT GetOneOffTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a><span data-ttu-id="f9268-106">参数</span><span class="sxs-lookup"><span data-stu-id="f9268-106">Parameters</span></span>

 <span data-ttu-id="f9268-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="f9268-107">_ulFlags_</span></span>
  
> <span data-ttu-id="f9268-108">[in]位掩码的标志，用于控制字符串表中包含的列的类型。</span><span class="sxs-lookup"><span data-stu-id="f9268-108">[in] A bitmask of flags that controls the type of string columns included in the table.</span></span> <span data-ttu-id="f9268-109">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="f9268-109">The following flag can be set:</span></span>
    
<span data-ttu-id="f9268-110">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="f9268-110">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="f9268-111">字符串列的 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="f9268-111">The string columns are in Unicode format.</span></span> <span data-ttu-id="f9268-112">如果未设置 MAPI_UNICODE 标志，字符串列的 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="f9268-112">If the MAPI_UNICODE flag is not set, the string columns are in ANSI format.</span></span>
    
 <span data-ttu-id="f9268-113">_lppTable_</span><span class="sxs-lookup"><span data-stu-id="f9268-113">_lppTable_</span></span>
  
> <span data-ttu-id="f9268-114">[输出]指向一次性表格的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="f9268-114">[out] A pointer to a pointer to the one-off table.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="f9268-115">返回值</span><span class="sxs-lookup"><span data-stu-id="f9268-115">Return value</span></span>

<span data-ttu-id="f9268-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="f9268-116">S_OK</span></span> 
  
> <span data-ttu-id="f9268-117">已成功检索一次性表。</span><span class="sxs-lookup"><span data-stu-id="f9268-117">The one-off table was successfully retrieved.</span></span>
    
<span data-ttu-id="f9268-118">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="f9268-118">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="f9268-119">既设置了 MAPI_UNICODE 标志通讯簿提供程序不支持 Unicode，或未设置 MAPI_UNICODE 和通讯簿提供程序支持仅 Unicode。</span><span class="sxs-lookup"><span data-stu-id="f9268-119">Either the MAPI_UNICODE flag was set and the address book provider does not support Unicode, or MAPI_UNICODE was not set and the address book provider supports only Unicode.</span></span>
    
<span data-ttu-id="f9268-120">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="f9268-120">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="f9268-121">通讯簿提供程序不提供任何一次性模板。</span><span class="sxs-lookup"><span data-stu-id="f9268-121">The address book provider does not supply any one-off templates.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="f9268-122">注解</span><span class="sxs-lookup"><span data-stu-id="f9268-122">Remarks</span></span>

<span data-ttu-id="f9268-123">MAPI 调用**GetOneOffTable**方法使可用一次性模板创建收件人。</span><span class="sxs-lookup"><span data-stu-id="f9268-123">MAPI calls the **GetOneOffTable** method to make available one-off templates to create recipients.</span></span> <span data-ttu-id="f9268-124">新的收件人添加到的传出邮件的收件人列表。</span><span class="sxs-lookup"><span data-stu-id="f9268-124">The new recipients are added to the recipient list of an outgoing message.</span></span> <span data-ttu-id="f9268-125">通讯簿提供程序应支持通知模板修改的 MAPI 其一次性表上的通知。</span><span class="sxs-lookup"><span data-stu-id="f9268-125">Address book providers should support notification on their one-off table to inform MAPI of template modifications.</span></span> <span data-ttu-id="f9268-126">MAPI 保持打开，以允许动态更新一次性表。</span><span class="sxs-lookup"><span data-stu-id="f9268-126">MAPI keeps the one-off table open to enable dynamic updating.</span></span> 
  
<span data-ttu-id="f9268-127">通讯簿提供程序还可以为每个其容器支持一次性表。</span><span class="sxs-lookup"><span data-stu-id="f9268-127">Address book providers can also support a one-off table for each of their containers.</span></span> <span data-ttu-id="f9268-128">呼叫者通过调用容器的[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法并请求**PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 属性来检索此一次性表。</span><span class="sxs-lookup"><span data-stu-id="f9268-128">Callers retrieve this one-off table by calling the container's [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method and requesting the **PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) property.</span></span> <span data-ttu-id="f9268-129">可通过此表的模板用于将收件人添加到容器。</span><span class="sxs-lookup"><span data-stu-id="f9268-129">The templates available through this table are used to add recipients to the container.</span></span> <span data-ttu-id="f9268-130">有关两种类型的一次性表之间的差异的讨论，请参阅[实现一次性表](implementing-one-off-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="f9268-130">For a discussion of the differences between the two types of one-off tables, see [Implementing One-Off Tables](implementing-one-off-tables.md).</span></span>
  
<span data-ttu-id="f9268-131">通讯簿提供程序的一次性表中所需的列的列表，请参阅[一次性表](one-off-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="f9268-131">For a list of the required columns in an address book provider's one-off table, see [One-Off Tables](one-off-tables.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f9268-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f9268-132">See also</span></span>



[<span data-ttu-id="f9268-133">IABContainer::CreateEntry</span><span class="sxs-lookup"><span data-stu-id="f9268-133">IABContainer::CreateEntry</span></span>](iabcontainer-createentry.md)
  
[<span data-ttu-id="f9268-134">IAddrBook::NewEntry</span><span class="sxs-lookup"><span data-stu-id="f9268-134">IAddrBook::NewEntry</span></span>](iaddrbook-newentry.md)
  
[<span data-ttu-id="f9268-135">IMAPISupport::GetOneOffTable</span><span class="sxs-lookup"><span data-stu-id="f9268-135">IMAPISupport::GetOneOffTable</span></span>](imapisupport-getoneofftable.md)
  
[<span data-ttu-id="f9268-136">IABLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f9268-136">IABLogon : IUnknown</span></span>](iablogoniunknown.md)

