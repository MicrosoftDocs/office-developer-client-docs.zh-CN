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
# <a name="iablogongetoneofftable"></a><span data-ttu-id="a61e2-103">IABLogon::GetOneOffTable</span><span class="sxs-lookup"><span data-stu-id="a61e2-103">IABLogon::GetOneOffTable</span></span>

  
  
<span data-ttu-id="a61e2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a61e2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a61e2-105">返回用于创建要添加到传出邮件的收件人列表的收件人的一次模板表。</span><span class="sxs-lookup"><span data-stu-id="a61e2-105">Returns a table of one-off templates for creating recipients to be added to the recipient list of an outgoing message.</span></span>
  
```cpp
HRESULT GetOneOffTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a><span data-ttu-id="a61e2-106">参数</span><span class="sxs-lookup"><span data-stu-id="a61e2-106">Parameters</span></span>

 <span data-ttu-id="a61e2-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="a61e2-107">_ulFlags_</span></span>
  
> <span data-ttu-id="a61e2-108">[in]控制表中包含的字符串列类型的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="a61e2-108">[in] A bitmask of flags that controls the type of string columns included in the table.</span></span> <span data-ttu-id="a61e2-109">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="a61e2-109">The following flag can be set:</span></span>
    
<span data-ttu-id="a61e2-110">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="a61e2-110">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="a61e2-111">字符串列采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="a61e2-111">The string columns are in Unicode format.</span></span> <span data-ttu-id="a61e2-112">如果未MAPI_UNICODE，则字符串列采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="a61e2-112">If the MAPI_UNICODE flag is not set, the string columns are in ANSI format.</span></span>
    
 <span data-ttu-id="a61e2-113">_lppTable_</span><span class="sxs-lookup"><span data-stu-id="a61e2-113">_lppTable_</span></span>
  
> <span data-ttu-id="a61e2-114">[out]指向指向一次表的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="a61e2-114">[out] A pointer to a pointer to the one-off table.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="a61e2-115">返回值</span><span class="sxs-lookup"><span data-stu-id="a61e2-115">Return value</span></span>

<span data-ttu-id="a61e2-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="a61e2-116">S_OK</span></span> 
  
> <span data-ttu-id="a61e2-117">已成功检索一次表。</span><span class="sxs-lookup"><span data-stu-id="a61e2-117">The one-off table was successfully retrieved.</span></span>
    
<span data-ttu-id="a61e2-118">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="a61e2-118">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="a61e2-119">设置 MAPI_UNICODE 标志，通讯簿提供程序不支持 Unicode，或者MAPI_UNICODE设置该地址簿提供程序仅支持 Unicode。</span><span class="sxs-lookup"><span data-stu-id="a61e2-119">Either the MAPI_UNICODE flag was set and the address book provider does not support Unicode, or MAPI_UNICODE was not set and the address book provider supports only Unicode.</span></span>
    
<span data-ttu-id="a61e2-120">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="a61e2-120">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="a61e2-121">通讯簿提供程序不提供任何一次使用模板。</span><span class="sxs-lookup"><span data-stu-id="a61e2-121">The address book provider does not supply any one-off templates.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="a61e2-122">备注</span><span class="sxs-lookup"><span data-stu-id="a61e2-122">Remarks</span></span>

<span data-ttu-id="a61e2-123">MAPI 调用 **GetOneOffTable** 方法，使一次可用模板可用于创建收件人。</span><span class="sxs-lookup"><span data-stu-id="a61e2-123">MAPI calls the **GetOneOffTable** method to make available one-off templates to create recipients.</span></span> <span data-ttu-id="a61e2-124">新收件人将添加到传出邮件的收件人列表中。</span><span class="sxs-lookup"><span data-stu-id="a61e2-124">The new recipients are added to the recipient list of an outgoing message.</span></span> <span data-ttu-id="a61e2-125">通讯簿提供程序应支持在一对一表上发送通知，以通知 MAPI 模板修改。</span><span class="sxs-lookup"><span data-stu-id="a61e2-125">Address book providers should support notification on their one-off table to inform MAPI of template modifications.</span></span> <span data-ttu-id="a61e2-126">MAPI 使一次表保持打开状态，以启用动态更新。</span><span class="sxs-lookup"><span data-stu-id="a61e2-126">MAPI keeps the one-off table open to enable dynamic updating.</span></span> 
  
<span data-ttu-id="a61e2-127">通讯簿提供程序还可以支持每个容器的一对一表。</span><span class="sxs-lookup"><span data-stu-id="a61e2-127">Address book providers can also support a one-off table for each of their containers.</span></span> <span data-ttu-id="a61e2-128">调用方通过调用容器的[IMAPIProp：：OpenProperty](imapiprop-openproperty.md)方法并请求 PR_CREATE_TEMPLATES ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 检索此一) 表。 </span><span class="sxs-lookup"><span data-stu-id="a61e2-128">Callers retrieve this one-off table by calling the container's [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method and requesting the **PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) property.</span></span> <span data-ttu-id="a61e2-129">通过此表提供的模板用于将收件人添加到容器。</span><span class="sxs-lookup"><span data-stu-id="a61e2-129">The templates available through this table are used to add recipients to the container.</span></span> <span data-ttu-id="a61e2-130">有关这两种类型的一键式表之间的差异的讨论，请参阅 [Implementing One-Off Tables](implementing-one-off-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="a61e2-130">For a discussion of the differences between the two types of one-off tables, see [Implementing One-Off Tables](implementing-one-off-tables.md).</span></span>
  
<span data-ttu-id="a61e2-131">有关通讯簿提供程序的一键式表中的所需列的列表，请参阅 [一键式表](one-off-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="a61e2-131">For a list of the required columns in an address book provider's one-off table, see [One-Off Tables](one-off-tables.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a61e2-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a61e2-132">See also</span></span>



[<span data-ttu-id="a61e2-133">IABContainer::CreateEntry</span><span class="sxs-lookup"><span data-stu-id="a61e2-133">IABContainer::CreateEntry</span></span>](iabcontainer-createentry.md)
  
[<span data-ttu-id="a61e2-134">IAddrBook::NewEntry</span><span class="sxs-lookup"><span data-stu-id="a61e2-134">IAddrBook::NewEntry</span></span>](iaddrbook-newentry.md)
  
[<span data-ttu-id="a61e2-135">IMAPISupport::GetOneOffTable</span><span class="sxs-lookup"><span data-stu-id="a61e2-135">IMAPISupport::GetOneOffTable</span></span>](imapisupport-getoneofftable.md)
  
[<span data-ttu-id="a61e2-136">IABLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="a61e2-136">IABLogon : IUnknown</span></span>](iablogoniunknown.md)

