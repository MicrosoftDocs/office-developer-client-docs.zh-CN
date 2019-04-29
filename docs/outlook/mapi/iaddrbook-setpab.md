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
# <a name="iaddrbooksetpab"></a><span data-ttu-id="8e47b-103">IAddrBook::SetPAB</span><span class="sxs-lookup"><span data-stu-id="8e47b-103">IAddrBook::SetPAB</span></span>

  
  
<span data-ttu-id="8e47b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8e47b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8e47b-105">指定特定的容器作为个人通讯簿 (PAB)。</span><span class="sxs-lookup"><span data-stu-id="8e47b-105">Designates a particular container as the personal address book (PAB).</span></span>
  
```cpp
HRESULT SetPAB(
  ULONG cbEntryID,
  LPENTRYID lpEntryID
);
```

## <a name="parameters"></a><span data-ttu-id="8e47b-106">参数</span><span class="sxs-lookup"><span data-stu-id="8e47b-106">Parameters</span></span>

 <span data-ttu-id="8e47b-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="8e47b-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="8e47b-108">实时条目标识符中由_lpEntryID_参数指向的字节数。</span><span class="sxs-lookup"><span data-stu-id="8e47b-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="8e47b-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="8e47b-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="8e47b-110">实时指向要指定为 PAB 的容器的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="8e47b-110">[in] A pointer to the entry identifier of the container to be designated as the PAB.</span></span> <span data-ttu-id="8e47b-111">_lpEntryID_参数不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="8e47b-111">The  _lpEntryID_ parameter cannot be NULL.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="8e47b-112">返回值</span><span class="sxs-lookup"><span data-stu-id="8e47b-112">Return value</span></span>

<span data-ttu-id="8e47b-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="8e47b-113">S_OK</span></span> 
  
> <span data-ttu-id="8e47b-114">指定的容器已被建立为 PAB。</span><span class="sxs-lookup"><span data-stu-id="8e47b-114">The specified container has been established as the PAB.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="8e47b-115">说明</span><span class="sxs-lookup"><span data-stu-id="8e47b-115">Remarks</span></span>

<span data-ttu-id="8e47b-116">客户端和服务提供程序调用**SetPAB**方法, 以将特定容器指定为 PAB。</span><span class="sxs-lookup"><span data-stu-id="8e47b-116">Clients and service providers call the **SetPAB** method to designate a particular container as the PAB.</span></span> <span data-ttu-id="8e47b-117">PAB 是一个容器, 它由从其他容器复制的条目以及新条目组成。</span><span class="sxs-lookup"><span data-stu-id="8e47b-117">The PAB is a container that consists of entries copied from other containers as well as new entries.</span></span> 
  
<span data-ttu-id="8e47b-118">对**SetPAB**的调用在将容器用作 PAB 之前将其建立, 直到将容器变为不可用, 或者新的容器通过对**SetPAB**的后续调用成为 pab。</span><span class="sxs-lookup"><span data-stu-id="8e47b-118">A call to **SetPAB** establishes a container as the PAB until that container is made unavailable or a new container becomes the PAB through a subsequent call to **SetPAB**.</span></span> 
  
<span data-ttu-id="8e47b-119">客户端和提供程序无需调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法来使 PAB 更改永久。</span><span class="sxs-lookup"><span data-stu-id="8e47b-119">Clients and providers do not have to call the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method to make the PAB change permanent.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="8e47b-120">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="8e47b-120">MFCMAPI reference</span></span>

<span data-ttu-id="8e47b-121">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="8e47b-121">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="8e47b-122">**文件**</span><span class="sxs-lookup"><span data-stu-id="8e47b-122">**File**</span></span>|<span data-ttu-id="8e47b-123">**函数**</span><span class="sxs-lookup"><span data-stu-id="8e47b-123">**Function**</span></span>|<span data-ttu-id="8e47b-124">**备注**</span><span class="sxs-lookup"><span data-stu-id="8e47b-124">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8e47b-125">AbContDlg</span><span class="sxs-lookup"><span data-stu-id="8e47b-125">AbContDlg.cpp</span></span>  <br/> |<span data-ttu-id="8e47b-126">CAbContDlg:: OnSetPAB</span><span class="sxs-lookup"><span data-stu-id="8e47b-126">CAbContDlg::OnSetPAB</span></span>  <br/> |<span data-ttu-id="8e47b-127">MFCMAPI 使用**SetPAB**方法使指定容器成为 PAB。</span><span class="sxs-lookup"><span data-stu-id="8e47b-127">MFCMAPI uses the **SetPAB** method to make the specified container the PAB.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="8e47b-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8e47b-128">See also</span></span>



[<span data-ttu-id="8e47b-129">IAddrBook::GetPAB</span><span class="sxs-lookup"><span data-stu-id="8e47b-129">IAddrBook::GetPAB</span></span>](iaddrbook-getpab.md)
  
[<span data-ttu-id="8e47b-130">IAddrBook::GetSearchPath</span><span class="sxs-lookup"><span data-stu-id="8e47b-130">IAddrBook::GetSearchPath</span></span>](iaddrbook-getsearchpath.md)
  
[<span data-ttu-id="8e47b-131">PidTagContainerFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="8e47b-131">PidTagContainerFlags Canonical Property</span></span>](pidtagcontainerflags-canonical-property.md)
  
[<span data-ttu-id="8e47b-132">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="8e47b-132">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)


[<span data-ttu-id="8e47b-133">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="8e47b-133">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

