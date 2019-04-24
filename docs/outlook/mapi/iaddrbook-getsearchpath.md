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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341389"
---
# <a name="iaddrbookgetsearchpath"></a><span data-ttu-id="0c863-103">IAddrBook::GetSearchPath</span><span class="sxs-lookup"><span data-stu-id="0c863-103">IAddrBook::GetSearchPath</span></span>

  
  
<span data-ttu-id="0c863-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0c863-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0c863-105">返回要包含在由[IAddrBook:: ResolveName](iaddrbook-resolvename.md)方法启动的名称解析进程中的容器的条目标识符的已排序列表。</span><span class="sxs-lookup"><span data-stu-id="0c863-105">Returns an ordered list of entry identifiers of the containers to be included in the name resolution process initiated by the [IAddrBook::ResolveName](iaddrbook-resolvename.md) method.</span></span> 
  
```cpp
HRESULT GetSearchPath(
  ULONG ulFlags,
  LPSRowSet FAR * lppSearchPath
);
```

## <a name="parameters"></a><span data-ttu-id="0c863-106">参数</span><span class="sxs-lookup"><span data-stu-id="0c863-106">Parameters</span></span>

 <span data-ttu-id="0c863-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="0c863-107">_ulFlags_</span></span>
  
> <span data-ttu-id="0c863-108">实时标志的位掩码, 用于控制在搜索路径中返回的字符串的类型。</span><span class="sxs-lookup"><span data-stu-id="0c863-108">[in] A bitmask of flags that controls the type of the strings returned in the search path.</span></span> <span data-ttu-id="0c863-109">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="0c863-109">The following flag can be set:</span></span>
    
<span data-ttu-id="0c863-110">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="0c863-110">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="0c863-111">返回的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="0c863-111">The returned strings are in Unicode format.</span></span> <span data-ttu-id="0c863-112">如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="0c863-112">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="0c863-113">_lppSearchPath_</span><span class="sxs-lookup"><span data-stu-id="0c863-113">_lppSearchPath_</span></span>
  
> <span data-ttu-id="0c863-114">排除指向指向容器条目标识符的有序列表的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="0c863-114">[out] A pointer to a pointer to an ordered list of container entry identifiers.</span></span> <span data-ttu-id="0c863-115">**GetSearchPath**将排序列表存储在[SRowSet](srowset.md)结构中。</span><span class="sxs-lookup"><span data-stu-id="0c863-115">**GetSearchPath** stores the ordered list in an [SRowSet](srowset.md) structure.</span></span> <span data-ttu-id="0c863-116">如果通讯簿层次结构中没有容器, 则在**SRowSet**结构中返回零。</span><span class="sxs-lookup"><span data-stu-id="0c863-116">If there are no containers in the address book hierarchy, zero is returned in the **SRowSet** structure.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="0c863-117">返回值</span><span class="sxs-lookup"><span data-stu-id="0c863-117">Return value</span></span>

<span data-ttu-id="0c863-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="0c863-118">S_OK</span></span> 
  
> <span data-ttu-id="0c863-119">已成功检索搜索路径。</span><span class="sxs-lookup"><span data-stu-id="0c863-119">The search path was successfully retrieved.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="0c863-120">注解</span><span class="sxs-lookup"><span data-stu-id="0c863-120">Remarks</span></span>

<span data-ttu-id="0c863-121">客户端和服务提供程序调用**GetSearchPath**方法, 以获取用于使用**ResolveName**方法解析名称的搜索路径。</span><span class="sxs-lookup"><span data-stu-id="0c863-121">Clients and service providers call the **GetSearchPath** method to get the search path that is used to resolve names with the **ResolveName** method.</span></span> <span data-ttu-id="0c863-122">通常情况下, 客户端调用[IAddrBook:: SetSearchPath](iaddrbook-setsearchpath.md)方法在配置文件中建立容器搜索路径, 然后再调用**GetSearchPath**检索该路径。</span><span class="sxs-lookup"><span data-stu-id="0c863-122">Typically, clients call the [IAddrBook::SetSearchPath](iaddrbook-setsearchpath.md) method to establish a container search path in the profile before they call **GetSearchPath** to retrieve it.</span></span> <span data-ttu-id="0c863-123">但是, 调用**SetSearchPath**是可选的。</span><span class="sxs-lookup"><span data-stu-id="0c863-123">However, calling **SetSearchPath** is optional.</span></span> 
  
<span data-ttu-id="0c863-124">如果从未调用过**SetSearchPath** , 则**GetSearchPath**通过通讯簿的层次结构表来生成路径。</span><span class="sxs-lookup"><span data-stu-id="0c863-124">If **SetSearchPath** has never been called, **GetSearchPath** builds a path by working through the address book's hierarchy tables.</span></span> <span data-ttu-id="0c863-125">由**GetSearchPath**建立的默认搜索路径由以下容器组成, 顺序如下:</span><span class="sxs-lookup"><span data-stu-id="0c863-125">The default search path established by **GetSearchPath** consists of the following containers in the following order:</span></span> 
  
1. <span data-ttu-id="0c863-126">第一个具有读/写权限的容器, 通常是个人通讯簿 (PAB)。</span><span class="sxs-lookup"><span data-stu-id="0c863-126">The first container with read/write permission, usually the personal address book (PAB).</span></span>
    
2. <span data-ttu-id="0c863-127">将其**PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) 属性设置为 DT_GLOBAL 的每个容器。</span><span class="sxs-lookup"><span data-stu-id="0c863-127">Every container that has its **PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) property set to DT_GLOBAL.</span></span> <span data-ttu-id="0c863-128">此设置指示容器保留收件人。</span><span class="sxs-lookup"><span data-stu-id="0c863-128">This setting indicates that the container holds recipients.</span></span> 
    
3. <span data-ttu-id="0c863-129">如果没有在其**PR_DISPLAY_TYPE**属性中设置 DT_GLOBAL 标志且默认容器不同于具有读/写权限的第一个容器的容器, 则指定为默认容器。</span><span class="sxs-lookup"><span data-stu-id="0c863-129">The container designated as the default, if there are no containers that have the DT_GLOBAL flag set in their **PR_DISPLAY_TYPE** property and the default container differs from the first container with read/write permission.</span></span> 
    
<span data-ttu-id="0c863-130">如果已调用**SetSearchPath** , 则**GetSearchPath**将使用存储在配置文件中的通讯簿容器生成路径。</span><span class="sxs-lookup"><span data-stu-id="0c863-130">If **SetSearchPath** has been called, **GetSearchPath** builds a path by using the address book containers that have been stored in the profile.</span></span> <span data-ttu-id="0c863-131">**GetSearchPath**在将此路径返回给调用方之前对其进行验证。</span><span class="sxs-lookup"><span data-stu-id="0c863-131">**GetSearchPath** validates this path before it returns it to the caller.</span></span> 
  
<span data-ttu-id="0c863-132">在首次调用**SetSearchPath**后, 必须使用对**SetSearchPath**的后续调用来修改**GetSearchPath**返回的搜索路径。</span><span class="sxs-lookup"><span data-stu-id="0c863-132">After the first call to **SetSearchPath**, subsequent calls to **SetSearchPath** must be used to modify the search path returned by **GetSearchPath**.</span></span> <span data-ttu-id="0c863-133">换言之, 在首次调用**SetSearchPath**之后, 调用客户端或提供程序不会收到默认搜索路径。</span><span class="sxs-lookup"><span data-stu-id="0c863-133">In other words, the calling client or provider does not receive the default search path after the first call to **SetSearchPath**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0c863-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0c863-134">See also</span></span>



[<span data-ttu-id="0c863-135">IAddrBook::SetSearchPath</span><span class="sxs-lookup"><span data-stu-id="0c863-135">IAddrBook::SetSearchPath</span></span>](iaddrbook-setsearchpath.md)
  
[<span data-ttu-id="0c863-136">SRowSet</span><span class="sxs-lookup"><span data-stu-id="0c863-136">SRowSet</span></span>](srowset.md)
  
[<span data-ttu-id="0c863-137">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="0c863-137">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)

