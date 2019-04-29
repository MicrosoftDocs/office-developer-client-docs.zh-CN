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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6c565c088fd4ef7d5df141bf770c560f79535998
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419896"
---
# <a name="iaddrbookgetpab"></a><span data-ttu-id="2dacd-103">IAddrBook::GetPAB</span><span class="sxs-lookup"><span data-stu-id="2dacd-103">IAddrBook::GetPAB</span></span>

  
  
<span data-ttu-id="2dacd-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2dacd-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2dacd-105">返回指定为 "个人通讯簿" (PAB) 的容器的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="2dacd-105">Returns the entry identifier of the container that is designated as the personal address book (PAB).</span></span>
  
```cpp
HRESULT GetPAB(
  ULONG FAR * lpcbEntryID,
  LPENTRYID FAR * lppEntryID
);
```

## <a name="parameters"></a><span data-ttu-id="2dacd-106">参数</span><span class="sxs-lookup"><span data-stu-id="2dacd-106">Parameters</span></span>

 <span data-ttu-id="2dacd-107">_lpcbEntryID_</span><span class="sxs-lookup"><span data-stu-id="2dacd-107">_lpcbEntryID_</span></span>
  
> <span data-ttu-id="2dacd-108">排除指向条目标识符中由_lppEntryID_参数指向的字节计数的指针。</span><span class="sxs-lookup"><span data-stu-id="2dacd-108">[out] A pointer to the byte count in the entry identifier pointed to by the  _lppEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="2dacd-109">_lppEntryID_</span><span class="sxs-lookup"><span data-stu-id="2dacd-109">_lppEntryID_</span></span>
  
> <span data-ttu-id="2dacd-110">排除指向 PAB 条目标识符的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="2dacd-110">[out] A pointer to a pointer to the entry identifier of the PAB.</span></span> <span data-ttu-id="2dacd-111">如果没有指定为 PAB 的容器, 则_lppEntryID_参数包含零。</span><span class="sxs-lookup"><span data-stu-id="2dacd-111">The  _lppEntryID_ parameter contains zero if no container has been designated as the PAB.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="2dacd-112">返回值</span><span class="sxs-lookup"><span data-stu-id="2dacd-112">Return value</span></span>

<span data-ttu-id="2dacd-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="2dacd-113">S_OK</span></span> 
  
> <span data-ttu-id="2dacd-114">已成功返回 PAB 的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="2dacd-114">The entry identifier of the PAB was successfully returned.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="2dacd-115">说明</span><span class="sxs-lookup"><span data-stu-id="2dacd-115">Remarks</span></span>

<span data-ttu-id="2dacd-116">客户端调用**GetPAB**方法以检索被指定为 PAB 的容器的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="2dacd-116">Clients call the **GetPAB** method to retrieve the entry identifier of the container designated as the PAB.</span></span> <span data-ttu-id="2dacd-117">如果未在配置文件中建立 pab, MAPI 将选择 pab 通讯簿层次结构中允许修改的第一个容器。</span><span class="sxs-lookup"><span data-stu-id="2dacd-117">If a PAB has not been established in the profile, MAPI selects as the PAB the first container in the address book hierarchy that allows modifications.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="2dacd-118">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="2dacd-118">MFCMAPI reference</span></span>

<span data-ttu-id="2dacd-119">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="2dacd-119">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="2dacd-120">**文件**</span><span class="sxs-lookup"><span data-stu-id="2dacd-120">**File**</span></span>|<span data-ttu-id="2dacd-121">**函数**</span><span class="sxs-lookup"><span data-stu-id="2dacd-121">**Function**</span></span>|<span data-ttu-id="2dacd-122">**备注**</span><span class="sxs-lookup"><span data-stu-id="2dacd-122">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2dacd-123">MainDlg</span><span class="sxs-lookup"><span data-stu-id="2dacd-123">MainDlg.cpp</span></span>  <br/> |<span data-ttu-id="2dacd-124">CMainDlg:: OnOpenPAB</span><span class="sxs-lookup"><span data-stu-id="2dacd-124">CMainDlg::OnOpenPAB</span></span>  <br/> |<span data-ttu-id="2dacd-125">MFCMAPI 使用**GetPAB**方法获取用户的个人通讯簿的 ID。</span><span class="sxs-lookup"><span data-stu-id="2dacd-125">MFCMAPI uses the **GetPAB** method to get the ID for the user's personal address book.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="2dacd-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2dacd-126">See also</span></span>



[<span data-ttu-id="2dacd-127">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="2dacd-127">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)
  
[<span data-ttu-id="2dacd-128">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="2dacd-128">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="2dacd-129">PidTagContainerFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="2dacd-129">PidTagContainerFlags Canonical Property</span></span>](pidtagcontainerflags-canonical-property.md)
  
[<span data-ttu-id="2dacd-130">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="2dacd-130">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)


[<span data-ttu-id="2dacd-131">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="2dacd-131">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

