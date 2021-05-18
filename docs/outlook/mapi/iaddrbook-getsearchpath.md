---
title: IAddrBookGetSearchPath
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IAddrBook.GetSearchPath
api_type:
- COM
ms.assetid: 43b51a66-71fa-4e10-93e4-d533b48af4de
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: f8c129e772870804ef464765b2035a3582317a09
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412980"
---
# <a name="iaddrbookgetsearchpath"></a><span data-ttu-id="190ae-103">IAddrBook::GetSearchPath</span><span class="sxs-lookup"><span data-stu-id="190ae-103">IAddrBook::GetSearchPath</span></span>

  
  
<span data-ttu-id="190ae-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="190ae-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="190ae-105">返回 [IAddrBook：：ResolveName](iaddrbook-resolvename.md) 方法启动的名称解析过程中要包含的容器的条目标识符的有序列表。</span><span class="sxs-lookup"><span data-stu-id="190ae-105">Returns an ordered list of entry identifiers of the containers to be included in the name resolution process initiated by the [IAddrBook::ResolveName](iaddrbook-resolvename.md) method.</span></span> 
  
```cpp
HRESULT GetSearchPath(
  ULONG ulFlags,
  LPSRowSet FAR * lppSearchPath
);
```

## <a name="parameters"></a><span data-ttu-id="190ae-106">参数</span><span class="sxs-lookup"><span data-stu-id="190ae-106">Parameters</span></span>

 <span data-ttu-id="190ae-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="190ae-107">_ulFlags_</span></span>
  
> <span data-ttu-id="190ae-108">[in]控制搜索路径中返回的字符串类型的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="190ae-108">[in] A bitmask of flags that controls the type of the strings returned in the search path.</span></span> <span data-ttu-id="190ae-109">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="190ae-109">The following flag can be set:</span></span>
    
<span data-ttu-id="190ae-110">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="190ae-110">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="190ae-111">返回的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="190ae-111">The returned strings are in Unicode format.</span></span> <span data-ttu-id="190ae-112">如果未MAPI_UNICODE，则字符串采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="190ae-112">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="190ae-113">_lppSearchPath_</span><span class="sxs-lookup"><span data-stu-id="190ae-113">_lppSearchPath_</span></span>
  
> <span data-ttu-id="190ae-114">[out]指向指向容器条目标识符的有序列表的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="190ae-114">[out] A pointer to a pointer to an ordered list of container entry identifiers.</span></span> <span data-ttu-id="190ae-115">**GetSearchPath** 将排序列表存储在 [SRowSet](srowset.md) 结构中。</span><span class="sxs-lookup"><span data-stu-id="190ae-115">**GetSearchPath** stores the ordered list in an [SRowSet](srowset.md) structure.</span></span> <span data-ttu-id="190ae-116">如果通讯簿层次结构中没有任何容器，则 **SRowSet** 结构中返回零。</span><span class="sxs-lookup"><span data-stu-id="190ae-116">If there are no containers in the address book hierarchy, zero is returned in the **SRowSet** structure.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="190ae-117">返回值</span><span class="sxs-lookup"><span data-stu-id="190ae-117">Return value</span></span>

<span data-ttu-id="190ae-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="190ae-118">S_OK</span></span> 
  
> <span data-ttu-id="190ae-119">已成功检索搜索路径。</span><span class="sxs-lookup"><span data-stu-id="190ae-119">The search path was successfully retrieved.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="190ae-120">备注</span><span class="sxs-lookup"><span data-stu-id="190ae-120">Remarks</span></span>

<span data-ttu-id="190ae-121">客户端和服务提供商调用 **GetSearchPath** 方法来获取用于用 **ResolveName** 方法解析名称的搜索路径。</span><span class="sxs-lookup"><span data-stu-id="190ae-121">Clients and service providers call the **GetSearchPath** method to get the search path that is used to resolve names with the **ResolveName** method.</span></span> <span data-ttu-id="190ae-122">通常，客户端调用 [IAddrBook：：SetSearchPath](iaddrbook-setsearchpath.md) 方法在配置文件中建立容器搜索路径，然后再调用 **GetSearchPath** 进行检索。</span><span class="sxs-lookup"><span data-stu-id="190ae-122">Typically, clients call the [IAddrBook::SetSearchPath](iaddrbook-setsearchpath.md) method to establish a container search path in the profile before they call **GetSearchPath** to retrieve it.</span></span> <span data-ttu-id="190ae-123">但是，调用 **SetSearchPath** 是可选的。</span><span class="sxs-lookup"><span data-stu-id="190ae-123">However, calling **SetSearchPath** is optional.</span></span> 
  
<span data-ttu-id="190ae-124">如果从未调用过 **SetSearchPath，GetSearchPath** 会通过处理通讯簿的层次结构表来构建路径。 </span><span class="sxs-lookup"><span data-stu-id="190ae-124">If **SetSearchPath** has never been called, **GetSearchPath** builds a path by working through the address book's hierarchy tables.</span></span> <span data-ttu-id="190ae-125">**GetSearchPath** 建立的默认搜索路径由以下容器组成，顺序如下：</span><span class="sxs-lookup"><span data-stu-id="190ae-125">The default search path established by **GetSearchPath** consists of the following containers in the following order:</span></span> 
  
1. <span data-ttu-id="190ae-126">具有读/写权限的第一个容器，通常为 PAB (个人) 。</span><span class="sxs-lookup"><span data-stu-id="190ae-126">The first container with read/write permission, usually the personal address book (PAB).</span></span>
    
2. <span data-ttu-id="190ae-127">每个具有[PidTagDisplayType PR_DISPLAY_TYPE (PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) 设置为 DT_GLOBAL。 </span><span class="sxs-lookup"><span data-stu-id="190ae-127">Every container that has its **PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) property set to DT_GLOBAL.</span></span> <span data-ttu-id="190ae-128">此设置指示容器保留收件人。</span><span class="sxs-lookup"><span data-stu-id="190ae-128">This setting indicates that the container holds recipients.</span></span> 
    
3. <span data-ttu-id="190ae-129">如果 PR_DISPLAY_TYPE 属性中没有设置 **DT_GLOBAL** 标志的容器，且默认容器与具有读/写权限的第一个容器不同，则指定为默认值的容器。</span><span class="sxs-lookup"><span data-stu-id="190ae-129">The container designated as the default, if there are no containers that have the DT_GLOBAL flag set in their **PR_DISPLAY_TYPE** property and the default container differs from the first container with read/write permission.</span></span> 
    
<span data-ttu-id="190ae-130">如果 **已调用 SetSearchPath，GetSearchPath** 会使用已存储在配置文件中的通讯簿容器构建路径。 </span><span class="sxs-lookup"><span data-stu-id="190ae-130">If **SetSearchPath** has been called, **GetSearchPath** builds a path by using the address book containers that have been stored in the profile.</span></span> <span data-ttu-id="190ae-131">**GetSearchPath** 先验证此路径，然后再将路径返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="190ae-131">**GetSearchPath** validates this path before it returns it to the caller.</span></span> 
  
<span data-ttu-id="190ae-132">首次调用 **SetSearchPath** 后，对 **SetSearchPath** 的后续调用必须用于修改 **GetSearchPath 返回的搜索路径**。</span><span class="sxs-lookup"><span data-stu-id="190ae-132">After the first call to **SetSearchPath**, subsequent calls to **SetSearchPath** must be used to modify the search path returned by **GetSearchPath**.</span></span> <span data-ttu-id="190ae-133">换句话说，调用客户端或提供商在首次调用 **SetSearchPath** 之后不会收到默认搜索路径。</span><span class="sxs-lookup"><span data-stu-id="190ae-133">In other words, the calling client or provider does not receive the default search path after the first call to **SetSearchPath**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="190ae-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="190ae-134">See also</span></span>



[<span data-ttu-id="190ae-135">IAddrBook::SetSearchPath</span><span class="sxs-lookup"><span data-stu-id="190ae-135">IAddrBook::SetSearchPath</span></span>](iaddrbook-setsearchpath.md)
  
[<span data-ttu-id="190ae-136">SRowSet</span><span class="sxs-lookup"><span data-stu-id="190ae-136">SRowSet</span></span>](srowset.md)
  
[<span data-ttu-id="190ae-137">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="190ae-137">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)

