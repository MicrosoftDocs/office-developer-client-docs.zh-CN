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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 7bf69e560142ab282d6545389e02766389e4d018
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22580696"
---
# <a name="iaddrbookgetsearchpath"></a><span data-ttu-id="ef94f-103">IAddrBook::GetSearchPath</span><span class="sxs-lookup"><span data-stu-id="ef94f-103">IAddrBook::GetSearchPath</span></span>

  
  
<span data-ttu-id="ef94f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ef94f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ef94f-105">返回一个已排序的列表项标识符启动[IAddrBook::ResolveName](iaddrbook-resolvename.md)方法的名称解析进程中包含的容器。</span><span class="sxs-lookup"><span data-stu-id="ef94f-105">Returns an ordered list of entry identifiers of the containers to be included in the name resolution process initiated by the [IAddrBook::ResolveName](iaddrbook-resolvename.md) method.</span></span> 
  
```cpp
HRESULT GetSearchPath(
  ULONG ulFlags,
  LPSRowSet FAR * lppSearchPath
);
```

## <a name="parameters"></a><span data-ttu-id="ef94f-106">参数</span><span class="sxs-lookup"><span data-stu-id="ef94f-106">Parameters</span></span>

 <span data-ttu-id="ef94f-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="ef94f-107">_ulFlags_</span></span>
  
> <span data-ttu-id="ef94f-108">[in]中的搜索路径返回控制的字符串类型的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="ef94f-108">[in] A bitmask of flags that controls the type of the strings returned in the search path.</span></span> <span data-ttu-id="ef94f-109">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="ef94f-109">The following flag can be set:</span></span>
    
<span data-ttu-id="ef94f-110">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="ef94f-110">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="ef94f-111">返回的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="ef94f-111">The returned strings are in Unicode format.</span></span> <span data-ttu-id="ef94f-112">如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="ef94f-112">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="ef94f-113">_lppSearchPath_</span><span class="sxs-lookup"><span data-stu-id="ef94f-113">_lppSearchPath_</span></span>
  
> <span data-ttu-id="ef94f-114">[输出]指向一个已排序列表容器项标识符的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="ef94f-114">[out] A pointer to a pointer to an ordered list of container entry identifiers.</span></span> <span data-ttu-id="ef94f-115">**GetSearchPath** [SRowSet](srowset.md)结构中存储的有序列的表。</span><span class="sxs-lookup"><span data-stu-id="ef94f-115">**GetSearchPath** stores the ordered list in an [SRowSet](srowset.md) structure.</span></span> <span data-ttu-id="ef94f-116">如果通讯簿层次结构中不有任何容器， **SRowSet**结构中将返回零。</span><span class="sxs-lookup"><span data-stu-id="ef94f-116">If there are no containers in the address book hierarchy, zero is returned in the **SRowSet** structure.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="ef94f-117">返回值</span><span class="sxs-lookup"><span data-stu-id="ef94f-117">Return value</span></span>

<span data-ttu-id="ef94f-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="ef94f-118">S_OK</span></span> 
  
> <span data-ttu-id="ef94f-119">已成功检索的搜索路径。</span><span class="sxs-lookup"><span data-stu-id="ef94f-119">The search path was successfully retrieved.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="ef94f-120">注解</span><span class="sxs-lookup"><span data-stu-id="ef94f-120">Remarks</span></span>

<span data-ttu-id="ef94f-121">客户端和服务提供商调用**GetSearchPath**方法以获取用于将名称解析使用**ResolveName**方法的搜索路径。</span><span class="sxs-lookup"><span data-stu-id="ef94f-121">Clients and service providers call the **GetSearchPath** method to get the search path that is used to resolve names with the **ResolveName** method.</span></span> <span data-ttu-id="ef94f-122">通常情况下，客户端调用[IAddrBook::SetSearchPath](iaddrbook-setsearchpath.md)方法之前呼叫**GetSearchPath**检索该配置文件中建立容器搜索路径。</span><span class="sxs-lookup"><span data-stu-id="ef94f-122">Typically, clients call the [IAddrBook::SetSearchPath](iaddrbook-setsearchpath.md) method to establish a container search path in the profile before they call **GetSearchPath** to retrieve it.</span></span> <span data-ttu-id="ef94f-123">但是，调用**SetSearchPath**是可选的。</span><span class="sxs-lookup"><span data-stu-id="ef94f-123">However, calling **SetSearchPath** is optional.</span></span> 
  
<span data-ttu-id="ef94f-124">如果**SetSearchPath**调用过， **GetSearchPath**生成一个路径由通过地址的工作簿的层次结构表。</span><span class="sxs-lookup"><span data-stu-id="ef94f-124">If **SetSearchPath** has never been called, **GetSearchPath** builds a path by working through the address book's hierarchy tables.</span></span> <span data-ttu-id="ef94f-125">默认的搜索路径建立**GetSearchPath**包括以下容器按以下顺序：</span><span class="sxs-lookup"><span data-stu-id="ef94f-125">The default search path established by **GetSearchPath** consists of the following containers in the following order:</span></span> 
  
1. <span data-ttu-id="ef94f-126">第一个容器具有读/写权限，通常在个人通讯簿 (PAB)。</span><span class="sxs-lookup"><span data-stu-id="ef94f-126">The first container with read/write permission, usually the personal address book (PAB).</span></span>
    
2. <span data-ttu-id="ef94f-127">其**PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) 属性设置为 DT_GLOBAL 每个容器。</span><span class="sxs-lookup"><span data-stu-id="ef94f-127">Every container that has its **PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) property set to DT_GLOBAL.</span></span> <span data-ttu-id="ef94f-128">此设置表示该容器包含收件人。</span><span class="sxs-lookup"><span data-stu-id="ef94f-128">This setting indicates that the container holds recipients.</span></span> 
    
3. <span data-ttu-id="ef94f-129">容器被指定为默认值，如果有其**PR_DISPLAY_TYPE**属性和默认容器中设置 DT_GLOBAL 标志没有容器与第一个容器具有读/写权限。</span><span class="sxs-lookup"><span data-stu-id="ef94f-129">The container designated as the default, if there are no containers that have the DT_GLOBAL flag set in their **PR_DISPLAY_TYPE** property and the default container differs from the first container with read/write permission.</span></span> 
    
<span data-ttu-id="ef94f-130">如果已调用**SetSearchPath** ， **GetSearchPath**使用已存储在配置文件中的地址簿容器生成一个路径。</span><span class="sxs-lookup"><span data-stu-id="ef94f-130">If **SetSearchPath** has been called, **GetSearchPath** builds a path by using the address book containers that have been stored in the profile.</span></span> <span data-ttu-id="ef94f-131">**GetSearchPath**返回给调用方之前验证此路径。</span><span class="sxs-lookup"><span data-stu-id="ef94f-131">**GetSearchPath** validates this path before it returns it to the caller.</span></span> 
  
<span data-ttu-id="ef94f-132">后**SetSearchPath**到第一个呼叫，必须使用后的面对**SetSearchPath**修改**GetSearchPath**返回的搜索路径。</span><span class="sxs-lookup"><span data-stu-id="ef94f-132">After the first call to **SetSearchPath**, subsequent calls to **SetSearchPath** must be used to modify the search path returned by **GetSearchPath**.</span></span> <span data-ttu-id="ef94f-133">换句话说，该呼叫的客户端或提供程序不会收到默认的搜索路径后**SetSearchPath**到第一个呼叫。</span><span class="sxs-lookup"><span data-stu-id="ef94f-133">In other words, the calling client or provider does not receive the default search path after the first call to **SetSearchPath**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ef94f-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ef94f-134">See also</span></span>



[<span data-ttu-id="ef94f-135">IAddrBook::SetSearchPath</span><span class="sxs-lookup"><span data-stu-id="ef94f-135">IAddrBook::SetSearchPath</span></span>](iaddrbook-setsearchpath.md)
  
[<span data-ttu-id="ef94f-136">SRowSet</span><span class="sxs-lookup"><span data-stu-id="ef94f-136">SRowSet</span></span>](srowset.md)
  
[<span data-ttu-id="ef94f-137">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="ef94f-137">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)

