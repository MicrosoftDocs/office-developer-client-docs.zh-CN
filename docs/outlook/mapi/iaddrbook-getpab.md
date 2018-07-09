---
title: IAddrBookGetPAB
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IAddrBook.GetPAB
api_type:
- COM
ms.assetid: 9830e09c-700f-469b-a54d-4e4e0583aa84
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 3d67d71effde87711e3be9aca1b979627acda37d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775258"
---
# <a name="iaddrbookgetpab"></a><span data-ttu-id="ad7f9-103">IAddrBook::GetPAB</span><span class="sxs-lookup"><span data-stu-id="ad7f9-103">IAddrBook::GetPAB</span></span>

  
  
<span data-ttu-id="ad7f9-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ad7f9-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ad7f9-105">返回的项标识符指定为个人通讯簿 (PAB) 的容器。</span><span class="sxs-lookup"><span data-stu-id="ad7f9-105">Returns the entry identifier of the container that is designated as the personal address book (PAB).</span></span>
  
```cpp
HRESULT GetPAB(
  ULONG FAR * lpcbEntryID,
  LPENTRYID FAR * lppEntryID
);
```

## <a name="parameters"></a><span data-ttu-id="ad7f9-106">参数</span><span class="sxs-lookup"><span data-stu-id="ad7f9-106">Parameters</span></span>

 <span data-ttu-id="ad7f9-107">_lpcbEntryID_</span><span class="sxs-lookup"><span data-stu-id="ad7f9-107">_lpcbEntryID_</span></span>
  
> <span data-ttu-id="ad7f9-108">[输出]一个指向_lppEntryID_参数指向该条目标识符中的字节数。</span><span class="sxs-lookup"><span data-stu-id="ad7f9-108">[out] A pointer to the byte count in the entry identifier pointed to by the  _lppEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="ad7f9-109">_lppEntryID_</span><span class="sxs-lookup"><span data-stu-id="ad7f9-109">_lppEntryID_</span></span>
  
> <span data-ttu-id="ad7f9-110">[输出]指向 PAB 的项标识符的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="ad7f9-110">[out] A pointer to a pointer to the entry identifier of the PAB.</span></span> <span data-ttu-id="ad7f9-111">如果没有容器被指定为 PAB， _lppEntryID_参数包含零。</span><span class="sxs-lookup"><span data-stu-id="ad7f9-111">The  _lppEntryID_ parameter contains zero if no container has been designated as the PAB.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="ad7f9-112">返回值</span><span class="sxs-lookup"><span data-stu-id="ad7f9-112">Return value</span></span>

<span data-ttu-id="ad7f9-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="ad7f9-113">S_OK</span></span> 
  
> <span data-ttu-id="ad7f9-114">已成功返回 PAB 的项标识符。</span><span class="sxs-lookup"><span data-stu-id="ad7f9-114">The entry identifier of the PAB was successfully returned.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="ad7f9-115">备注</span><span class="sxs-lookup"><span data-stu-id="ad7f9-115">Remarks</span></span>

<span data-ttu-id="ad7f9-116">客户端调用**GetPAB**方法检索的项标识符指定为 PAB 的容器。</span><span class="sxs-lookup"><span data-stu-id="ad7f9-116">Clients call the **GetPAB** method to retrieve the entry identifier of the container designated as the PAB.</span></span> <span data-ttu-id="ad7f9-117">如果尚未配置文件中建立 PAB，MAPI 选择作为 PAB 第一个容器允许进行修改的通讯簿层次结构中。</span><span class="sxs-lookup"><span data-stu-id="ad7f9-117">If a PAB has not been established in the profile, MAPI selects as the PAB the first container in the address book hierarchy that allows modifications.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="ad7f9-118">MFCMAPI 参考</span><span class="sxs-lookup"><span data-stu-id="ad7f9-118">MFCMAPI reference</span></span>

<span data-ttu-id="ad7f9-119">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="ad7f9-119">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="ad7f9-120">**文件**</span><span class="sxs-lookup"><span data-stu-id="ad7f9-120">**File**</span></span>|<span data-ttu-id="ad7f9-121">**函数**</span><span class="sxs-lookup"><span data-stu-id="ad7f9-121">**Function**</span></span>|<span data-ttu-id="ad7f9-122">**Comment**</span><span class="sxs-lookup"><span data-stu-id="ad7f9-122">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ad7f9-123">MainDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="ad7f9-123">MainDlg.cpp</span></span>  <br/> |<span data-ttu-id="ad7f9-124">CMainDlg::OnOpenPAB</span><span class="sxs-lookup"><span data-stu-id="ad7f9-124">CMainDlg::OnOpenPAB</span></span>  <br/> |<span data-ttu-id="ad7f9-125">MFCMAPI 使用**GetPAB**方法来获取用户的个人通讯簿的 ID。</span><span class="sxs-lookup"><span data-stu-id="ad7f9-125">MFCMAPI uses the **GetPAB** method to get the ID for the user's personal address book.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="ad7f9-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ad7f9-126">See also</span></span>



[<span data-ttu-id="ad7f9-127">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="ad7f9-127">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)
  
[<span data-ttu-id="ad7f9-128">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="ad7f9-128">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="ad7f9-129">PidTagContainerFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="ad7f9-129">PidTagContainerFlags Canonical Property</span></span>](pidtagcontainerflags-canonical-property.md)
  
[<span data-ttu-id="ad7f9-130">IAddrBook: IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="ad7f9-130">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)


[<span data-ttu-id="ad7f9-131">MFCMAPI 作为的代码示例</span><span class="sxs-lookup"><span data-stu-id="ad7f9-131">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

