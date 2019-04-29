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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 326a78ed512ec82a9f16b1540aad60954ab2d864
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411874"
---
# <a name="iablogongetoneofftable"></a><span data-ttu-id="4cb17-103">IABLogon::GetOneOffTable</span><span class="sxs-lookup"><span data-stu-id="4cb17-103">IABLogon::GetOneOffTable</span></span>

  
  
<span data-ttu-id="4cb17-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4cb17-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4cb17-105">返回一个一次性模板表, 用于创建要添加到传出邮件的收件人列表中的收件人。</span><span class="sxs-lookup"><span data-stu-id="4cb17-105">Returns a table of one-off templates for creating recipients to be added to the recipient list of an outgoing message.</span></span>
  
```cpp
HRESULT GetOneOffTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a><span data-ttu-id="4cb17-106">参数</span><span class="sxs-lookup"><span data-stu-id="4cb17-106">Parameters</span></span>

 <span data-ttu-id="4cb17-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="4cb17-107">_ulFlags_</span></span>
  
> <span data-ttu-id="4cb17-108">实时标志的位掩码, 用于控制包含在表中的字符串列的类型。</span><span class="sxs-lookup"><span data-stu-id="4cb17-108">[in] A bitmask of flags that controls the type of string columns included in the table.</span></span> <span data-ttu-id="4cb17-109">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="4cb17-109">The following flag can be set:</span></span>
    
<span data-ttu-id="4cb17-110">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="4cb17-110">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="4cb17-111">字符串列采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="4cb17-111">The string columns are in Unicode format.</span></span> <span data-ttu-id="4cb17-112">如果未设置 MAPI_UNICODE 标志, 则字符串列的格式为 ANSI。</span><span class="sxs-lookup"><span data-stu-id="4cb17-112">If the MAPI_UNICODE flag is not set, the string columns are in ANSI format.</span></span>
    
 <span data-ttu-id="4cb17-113">_lppTable_</span><span class="sxs-lookup"><span data-stu-id="4cb17-113">_lppTable_</span></span>
  
> <span data-ttu-id="4cb17-114">排除指向一次性表的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="4cb17-114">[out] A pointer to a pointer to the one-off table.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="4cb17-115">返回值</span><span class="sxs-lookup"><span data-stu-id="4cb17-115">Return value</span></span>

<span data-ttu-id="4cb17-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="4cb17-116">S_OK</span></span> 
  
> <span data-ttu-id="4cb17-117">已成功检索一次性表。</span><span class="sxs-lookup"><span data-stu-id="4cb17-117">The one-off table was successfully retrieved.</span></span>
    
<span data-ttu-id="4cb17-118">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="4cb17-118">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="4cb17-119">设置了 MAPI_UNICODE 标志, 且通讯簿提供程序不支持 unicode, 或者未设置 MAPI_UNICODE, 并且通讯簿提供程序仅支持 unicode。</span><span class="sxs-lookup"><span data-stu-id="4cb17-119">Either the MAPI_UNICODE flag was set and the address book provider does not support Unicode, or MAPI_UNICODE was not set and the address book provider supports only Unicode.</span></span>
    
<span data-ttu-id="4cb17-120">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="4cb17-120">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="4cb17-121">通讯簿提供程序不提供任何一次性模板。</span><span class="sxs-lookup"><span data-stu-id="4cb17-121">The address book provider does not supply any one-off templates.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="4cb17-122">说明</span><span class="sxs-lookup"><span data-stu-id="4cb17-122">Remarks</span></span>

<span data-ttu-id="4cb17-123">MAPI 调用**GetOneOffTable**方法来创建可用的一次性模板, 以创建收件人。</span><span class="sxs-lookup"><span data-stu-id="4cb17-123">MAPI calls the **GetOneOffTable** method to make available one-off templates to create recipients.</span></span> <span data-ttu-id="4cb17-124">新收件人将添加到传出邮件的收件人列表中。</span><span class="sxs-lookup"><span data-stu-id="4cb17-124">The new recipients are added to the recipient list of an outgoing message.</span></span> <span data-ttu-id="4cb17-125">通讯簿提供程序应支持对其一次性表发出通知, 以通知 MAPI 的模板修改。</span><span class="sxs-lookup"><span data-stu-id="4cb17-125">Address book providers should support notification on their one-off table to inform MAPI of template modifications.</span></span> <span data-ttu-id="4cb17-126">MAPI 保持打开一个 "一次性" 表以启用动态更新。</span><span class="sxs-lookup"><span data-stu-id="4cb17-126">MAPI keeps the one-off table open to enable dynamic updating.</span></span> 
  
<span data-ttu-id="4cb17-127">通讯簿提供程序还可以支持其每个容器的一次性表。</span><span class="sxs-lookup"><span data-stu-id="4cb17-127">Address book providers can also support a one-off table for each of their containers.</span></span> <span data-ttu-id="4cb17-128">调用方通过调用容器的[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法并请求**PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 属性来检索此一次性表。</span><span class="sxs-lookup"><span data-stu-id="4cb17-128">Callers retrieve this one-off table by calling the container's [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method and requesting the **PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) property.</span></span> <span data-ttu-id="4cb17-129">可通过此表使用的模板将收件人添加到容器中。</span><span class="sxs-lookup"><span data-stu-id="4cb17-129">The templates available through this table are used to add recipients to the container.</span></span> <span data-ttu-id="4cb17-130">有关这两种类型的一次性表之间的区别的讨论, 请参阅[实现一次性表](implementing-one-off-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="4cb17-130">For a discussion of the differences between the two types of one-off tables, see [Implementing One-Off Tables](implementing-one-off-tables.md).</span></span>
  
<span data-ttu-id="4cb17-131">若要获取通讯簿提供程序的一次性表格中所需列的列表, 请参阅[一次性表格](one-off-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="4cb17-131">For a list of the required columns in an address book provider's one-off table, see [One-Off Tables](one-off-tables.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4cb17-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4cb17-132">See also</span></span>



[<span data-ttu-id="4cb17-133">IABContainer::CreateEntry</span><span class="sxs-lookup"><span data-stu-id="4cb17-133">IABContainer::CreateEntry</span></span>](iabcontainer-createentry.md)
  
[<span data-ttu-id="4cb17-134">IAddrBook::NewEntry</span><span class="sxs-lookup"><span data-stu-id="4cb17-134">IAddrBook::NewEntry</span></span>](iaddrbook-newentry.md)
  
[<span data-ttu-id="4cb17-135">IMAPISupport::GetOneOffTable</span><span class="sxs-lookup"><span data-stu-id="4cb17-135">IMAPISupport::GetOneOffTable</span></span>](imapisupport-getoneofftable.md)
  
[<span data-ttu-id="4cb17-136">IABLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="4cb17-136">IABLogon : IUnknown</span></span>](iablogoniunknown.md)

