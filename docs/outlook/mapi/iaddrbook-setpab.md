---
title: IAddrBookSetPAB
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IAddrBook.SetPAB
api_type:
- COM
ms.assetid: 75daf9d4-6975-435f-91e5-1b41e0047ab7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 29677ce74f405e8ca03f1639f3d98288532e9653
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424614"
---
# <a name="iaddrbooksetpab"></a><span data-ttu-id="307b4-103">IAddrBook::SetPAB</span><span class="sxs-lookup"><span data-stu-id="307b4-103">IAddrBook::SetPAB</span></span>

  
  
<span data-ttu-id="307b4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="307b4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="307b4-105">将特定容器指定为 PAB (个人通讯簿) 。</span><span class="sxs-lookup"><span data-stu-id="307b4-105">Designates a particular container as the personal address book (PAB).</span></span>
  
```cpp
HRESULT SetPAB(
  ULONG cbEntryID,
  LPENTRYID lpEntryID
);
```

## <a name="parameters"></a><span data-ttu-id="307b4-106">参数</span><span class="sxs-lookup"><span data-stu-id="307b4-106">Parameters</span></span>

 <span data-ttu-id="307b4-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="307b4-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="307b4-108">[in]  _lpEntryID_ 参数指向的条目标识符中的字节计数。</span><span class="sxs-lookup"><span data-stu-id="307b4-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="307b4-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="307b4-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="307b4-110">[in]指向要指定为 PAB 的容器的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="307b4-110">[in] A pointer to the entry identifier of the container to be designated as the PAB.</span></span> <span data-ttu-id="307b4-111">_lpEntryID_ 参数不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="307b4-111">The  _lpEntryID_ parameter cannot be NULL.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="307b4-112">返回值</span><span class="sxs-lookup"><span data-stu-id="307b4-112">Return value</span></span>

<span data-ttu-id="307b4-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="307b4-113">S_OK</span></span> 
  
> <span data-ttu-id="307b4-114">指定的容器已建立为 PAB。</span><span class="sxs-lookup"><span data-stu-id="307b4-114">The specified container has been established as the PAB.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="307b4-115">备注</span><span class="sxs-lookup"><span data-stu-id="307b4-115">Remarks</span></span>

<span data-ttu-id="307b4-116">客户端和服务提供商调用 **SetPAB** 方法以将特定容器指定为 PAB。</span><span class="sxs-lookup"><span data-stu-id="307b4-116">Clients and service providers call the **SetPAB** method to designate a particular container as the PAB.</span></span> <span data-ttu-id="307b4-117">PAB 是包含从其他容器复制的条目和新条目的容器。</span><span class="sxs-lookup"><span data-stu-id="307b4-117">The PAB is a container that consists of entries copied from other containers as well as new entries.</span></span> 
  
<span data-ttu-id="307b4-118">调用 **SetPAB 会** 建立一个容器作为 PAB，直到该容器不可用，或者通过后续调用 **SetPAB，** 新容器成为 PAB。</span><span class="sxs-lookup"><span data-stu-id="307b4-118">A call to **SetPAB** establishes a container as the PAB until that container is made unavailable or a new container becomes the PAB through a subsequent call to **SetPAB**.</span></span> 
  
<span data-ttu-id="307b4-119">客户端和提供程序不需要调用 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法来永久更改 PAB。</span><span class="sxs-lookup"><span data-stu-id="307b4-119">Clients and providers do not have to call the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method to make the PAB change permanent.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="307b4-120">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="307b4-120">MFCMAPI reference</span></span>

<span data-ttu-id="307b4-121">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="307b4-121">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="307b4-122">**文件**</span><span class="sxs-lookup"><span data-stu-id="307b4-122">**File**</span></span>|<span data-ttu-id="307b4-123">**函数**</span><span class="sxs-lookup"><span data-stu-id="307b4-123">**Function**</span></span>|<span data-ttu-id="307b4-124">**备注**</span><span class="sxs-lookup"><span data-stu-id="307b4-124">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="307b4-125">AbContDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="307b4-125">AbContDlg.cpp</span></span>  <br/> |<span data-ttu-id="307b4-126">CAbContDlg：：OnSetPAB</span><span class="sxs-lookup"><span data-stu-id="307b4-126">CAbContDlg::OnSetPAB</span></span>  <br/> |<span data-ttu-id="307b4-127">MFCMAPI 使用 **SetPAB** 方法将指定的容器设置为 PAB。</span><span class="sxs-lookup"><span data-stu-id="307b4-127">MFCMAPI uses the **SetPAB** method to make the specified container the PAB.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="307b4-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="307b4-128">See also</span></span>



[<span data-ttu-id="307b4-129">IAddrBook::GetPAB</span><span class="sxs-lookup"><span data-stu-id="307b4-129">IAddrBook::GetPAB</span></span>](iaddrbook-getpab.md)
  
[<span data-ttu-id="307b4-130">IAddrBook::GetSearchPath</span><span class="sxs-lookup"><span data-stu-id="307b4-130">IAddrBook::GetSearchPath</span></span>](iaddrbook-getsearchpath.md)
  
[<span data-ttu-id="307b4-131">PidTagContainerFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="307b4-131">PidTagContainerFlags Canonical Property</span></span>](pidtagcontainerflags-canonical-property.md)
  
[<span data-ttu-id="307b4-132">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="307b4-132">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)


[<span data-ttu-id="307b4-133">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="307b4-133">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

