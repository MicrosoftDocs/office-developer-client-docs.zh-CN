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
ms.openlocfilehash: 3f13a4d278b85ffae33e8f44f3a15eb499fb11b3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775269"
---
# <a name="iaddrbooksetpab"></a><span data-ttu-id="03f95-103">IAddrBook::SetPAB</span><span class="sxs-lookup"><span data-stu-id="03f95-103">IAddrBook::SetPAB</span></span>

  
  
<span data-ttu-id="03f95-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="03f95-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="03f95-105">指定为个人通讯簿 (PAB) 特定的容器。</span><span class="sxs-lookup"><span data-stu-id="03f95-105">Designates a particular container as the personal address book (PAB).</span></span>
  
```cpp
HRESULT SetPAB(
  ULONG cbEntryID,
  LPENTRYID lpEntryID
);
```

## <a name="parameters"></a><span data-ttu-id="03f95-106">参数</span><span class="sxs-lookup"><span data-stu-id="03f95-106">Parameters</span></span>

 <span data-ttu-id="03f95-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="03f95-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="03f95-108">[in]在_lpEntryID_参数指向的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="03f95-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="03f95-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="03f95-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="03f95-110">[in]指向要指定为 PAB 的容器的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="03f95-110">[in] A pointer to the entry identifier of the container to be designated as the PAB.</span></span> <span data-ttu-id="03f95-111">_LpEntryID_参数不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="03f95-111">The  _lpEntryID_ parameter cannot be NULL.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="03f95-112">返回值</span><span class="sxs-lookup"><span data-stu-id="03f95-112">Return value</span></span>

<span data-ttu-id="03f95-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="03f95-113">S_OK</span></span> 
  
> <span data-ttu-id="03f95-114">作为 PAB 建立了指定的容器。</span><span class="sxs-lookup"><span data-stu-id="03f95-114">The specified container has been established as the PAB.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="03f95-115">说明</span><span class="sxs-lookup"><span data-stu-id="03f95-115">Remarks</span></span>

<span data-ttu-id="03f95-116">客户端和服务提供商调用**SetPAB**方法将指定为 PAB 某个特定的容器。</span><span class="sxs-lookup"><span data-stu-id="03f95-116">Clients and service providers call the **SetPAB** method to designate a particular container as the PAB.</span></span> <span data-ttu-id="03f95-117">PAB 是从其他容器以及新条目复制的项组成的容器。</span><span class="sxs-lookup"><span data-stu-id="03f95-117">The PAB is a container that consists of entries copied from other containers as well as new entries.</span></span> 
  
<span data-ttu-id="03f95-118">调用**SetPAB**建立容器作为 PAB，直到该容器进行不可用或新容器成为通过后续调用**SetPAB**PAB。</span><span class="sxs-lookup"><span data-stu-id="03f95-118">A call to **SetPAB** establishes a container as the PAB until that container is made unavailable or a new container becomes the PAB through a subsequent call to **SetPAB**.</span></span> 
  
<span data-ttu-id="03f95-119">客户端和提供程序不需要调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法进行永久 PAB 更改。</span><span class="sxs-lookup"><span data-stu-id="03f95-119">Clients and providers do not have to call the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method to make the PAB change permanent.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="03f95-120">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="03f95-120">MFCMAPI reference</span></span>

<span data-ttu-id="03f95-121">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="03f95-121">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="03f95-122">**文件**</span><span class="sxs-lookup"><span data-stu-id="03f95-122">**File**</span></span>|<span data-ttu-id="03f95-123">**函数**</span><span class="sxs-lookup"><span data-stu-id="03f95-123">**Function**</span></span>|<span data-ttu-id="03f95-124">**Comment**</span><span class="sxs-lookup"><span data-stu-id="03f95-124">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="03f95-125">AbContDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="03f95-125">AbContDlg.cpp</span></span>  <br/> |<span data-ttu-id="03f95-126">CAbContDlg::OnSetPAB</span><span class="sxs-lookup"><span data-stu-id="03f95-126">CAbContDlg::OnSetPAB</span></span>  <br/> |<span data-ttu-id="03f95-127">MFCMAPI 使用**SetPAB**方法使指定的容器 PAB。</span><span class="sxs-lookup"><span data-stu-id="03f95-127">MFCMAPI uses the **SetPAB** method to make the specified container the PAB.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="03f95-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="03f95-128">See also</span></span>



[<span data-ttu-id="03f95-129">IAddrBook::GetPAB</span><span class="sxs-lookup"><span data-stu-id="03f95-129">IAddrBook::GetPAB</span></span>](iaddrbook-getpab.md)
  
[<span data-ttu-id="03f95-130">IAddrBook::GetSearchPath</span><span class="sxs-lookup"><span data-stu-id="03f95-130">IAddrBook::GetSearchPath</span></span>](iaddrbook-getsearchpath.md)
  
[<span data-ttu-id="03f95-131">PidTagContainerFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="03f95-131">PidTagContainerFlags Canonical Property</span></span>](pidtagcontainerflags-canonical-property.md)
  
[<span data-ttu-id="03f95-132">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="03f95-132">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)


[<span data-ttu-id="03f95-133">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="03f95-133">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

