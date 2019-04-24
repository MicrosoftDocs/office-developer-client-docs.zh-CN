---
title: IAddrBookGetDefaultDir
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IAddrBook.GetDefaultDir
api_type:
- COM
ms.assetid: 7a9fdf3f-fd76-40fb-8217-967c6efba5f6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d9ad74d8ae02a49ee3c222394caedfd571f84b1c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32336692"
---
# <a name="iaddrbookgetdefaultdir"></a><span data-ttu-id="70b6d-103">IAddrBook::GetDefaultDir</span><span class="sxs-lookup"><span data-stu-id="70b6d-103">IAddrBook::GetDefaultDir</span></span>

  
  
<span data-ttu-id="70b6d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="70b6d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="70b6d-105">返回初始通讯簿容器的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="70b6d-105">Returns the entry identifier for the initial address book container.</span></span>
  
```cpp
HRESULT GetDefaultDir(
  ULONG FAR * lpcbEntryID,
  LPENTRYID FAR * lppEntryID
);
```

## <a name="parameters"></a><span data-ttu-id="70b6d-106">参数</span><span class="sxs-lookup"><span data-stu-id="70b6d-106">Parameters</span></span>

 <span data-ttu-id="70b6d-107">_lpcbEntryID_</span><span class="sxs-lookup"><span data-stu-id="70b6d-107">_lpcbEntryID_</span></span>
  
> <span data-ttu-id="70b6d-108">排除指向条目标识符中由_lppEntryID_参数指向的字节计数的指针。</span><span class="sxs-lookup"><span data-stu-id="70b6d-108">[out] A pointer to the byte count in the entry identifier pointed to by the  _lppEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="70b6d-109">_lppEntryID_</span><span class="sxs-lookup"><span data-stu-id="70b6d-109">_lppEntryID_</span></span>
  
> <span data-ttu-id="70b6d-110">排除指向指向默认容器的条目标识符的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="70b6d-110">[out] A pointer to a pointer to the entry identifier of the default container.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="70b6d-111">返回值</span><span class="sxs-lookup"><span data-stu-id="70b6d-111">Return value</span></span>

<span data-ttu-id="70b6d-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="70b6d-112">S_OK</span></span> 
  
> <span data-ttu-id="70b6d-113">已成功返回默认容器的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="70b6d-113">The entry identifier of the default container was successfully returned.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="70b6d-114">注解</span><span class="sxs-lookup"><span data-stu-id="70b6d-114">Remarks</span></span>

<span data-ttu-id="70b6d-115">客户端应用程序和服务提供程序调用**GetDefaultDir**方法以检索默认通讯簿容器的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="70b6d-115">Client applications and service providers call the **GetDefaultDir** method to retrieve the entry identifier of the default address book container.</span></span> <span data-ttu-id="70b6d-116">默认容器是首次打开通讯簿时用户在通讯簿中看到的显示内容。</span><span class="sxs-lookup"><span data-stu-id="70b6d-116">The default container is what the user sees displayed in the address book when the address book is first opened.</span></span> <span data-ttu-id="70b6d-117">如果未通过调用[IAddrBook:: SetDefaultDir](iaddrbook-setdefaultdir.md)方法设置默认容器, 则 MAPI 将分配为默认容器, 其名称不是个人通讯簿 (PAB) 的第一个容器。</span><span class="sxs-lookup"><span data-stu-id="70b6d-117">If a default container has not been set by a call to the [IAddrBook::SetDefaultDir](iaddrbook-setdefaultdir.md) method, MAPI assigns as the default container the first container with names that is not the personal address book (PAB).</span></span> <span data-ttu-id="70b6d-118">如果找不到这样的容器, 则 PAB 将成为默认容器。</span><span class="sxs-lookup"><span data-stu-id="70b6d-118">If such a container cannot be found, the PAB becomes the default container.</span></span> 
  
<span data-ttu-id="70b6d-119">若要设置默认目录, 客户端或提供程序将调用**SetDefaultDir**方法。</span><span class="sxs-lookup"><span data-stu-id="70b6d-119">To set the default directory, a client or provider calls the **SetDefaultDir** method.</span></span> <span data-ttu-id="70b6d-120">客户端和提供程序无需调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法;由于对通讯簿所做的更改不会进行事务处理, 因此更改将立即永久生效。</span><span class="sxs-lookup"><span data-stu-id="70b6d-120">Clients and providers do not have to call the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method; because changes to the address book are not transacted, changes are immediately made permanent.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="70b6d-121">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="70b6d-121">MFCMAPI reference</span></span>

<span data-ttu-id="70b6d-122">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="70b6d-122">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="70b6d-123">**文件**</span><span class="sxs-lookup"><span data-stu-id="70b6d-123">**File**</span></span>|<span data-ttu-id="70b6d-124">**函数**</span><span class="sxs-lookup"><span data-stu-id="70b6d-124">**Function**</span></span>|<span data-ttu-id="70b6d-125">**备注**</span><span class="sxs-lookup"><span data-stu-id="70b6d-125">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="70b6d-126">MainDlg</span><span class="sxs-lookup"><span data-stu-id="70b6d-126">MainDlg.cpp</span></span>  <br/> |<span data-ttu-id="70b6d-127">CMainDlg:: OnOpenDefaultDir</span><span class="sxs-lookup"><span data-stu-id="70b6d-127">CMainDlg::OnOpenDefaultDir</span></span>  <br/> |<span data-ttu-id="70b6d-128">MFCMAPI 使用**GetDefaultDir**方法获取默认通讯簿容器的 ID。</span><span class="sxs-lookup"><span data-stu-id="70b6d-128">MFCMAPI uses the **GetDefaultDir** method to get the ID for the default address book container.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="70b6d-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="70b6d-129">See also</span></span>



[<span data-ttu-id="70b6d-130">IAddrBook::SetDefaultDir</span><span class="sxs-lookup"><span data-stu-id="70b6d-130">IAddrBook::SetDefaultDir</span></span>](iaddrbook-setdefaultdir.md)
  
[<span data-ttu-id="70b6d-131">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="70b6d-131">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)
  
[<span data-ttu-id="70b6d-132">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="70b6d-132">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="70b6d-133">PidTagContainerFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="70b6d-133">PidTagContainerFlags Canonical Property</span></span>](pidtagcontainerflags-canonical-property.md)
  
[<span data-ttu-id="70b6d-134">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="70b6d-134">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)


[<span data-ttu-id="70b6d-135">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="70b6d-135">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

